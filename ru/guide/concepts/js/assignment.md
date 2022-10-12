# Класс Assignment

{% include [toloka-requester-source-html-editor-tb](../../_includes/toloka-requester-source/id-toloka-requester-source/html-editor-tb.md) %}

Этот класс управляет ходом выполнения задания, обрабатывает команды страницы заданий на отправку ответов, пропуск, приостановку задания и т. п. Также он создает экземпляр класса [TaskSuite](tasksuite.md).

Базовый класс `Assignment` доступен в глобальной переменной `window.TolokaAssignment`.

Методы:

#### constructor(options)

Конструктор базового класса списка заданий.

Параметры:

- `options.assignment` — модель списка задания `Assignment`.

- `options.specs` — параметры [входных и выходных данных](../../../glossary.md#input-output-data), интерфейса заданий.

- `options.workspaceOptions` — параметры инициализации рабочего пространства исполнителя.

#### destroy()

Вызывает [`TaskSuite.destroy()`](tasksuite.md#destroy), удаляет из DOM все элементы шаблона, закрывает канал обмена сообщениями, останавливает опрос горячих клавиш и геолокацию, вызывает `onDestroy`.

#### initHotkeys()

Инициализатор обработчиков горячих клавиш:

- Сбрасывает все горячие клавиши ([`hotkeys.reset`](services.md#reset)).

- При нажатии клавиши Enter вызывает метод [`submit()`](#Submit).

#### getId()

Возвращает `assignmentId` в виде строки или `undefined`, если вы отлаживаете задание в режиме превью или открыли предпросмотр пула.

#### getOptions()

Возвращает объект с набором параметров, переданных методу `constructor()` при инициализации.

{% cut "Пример" %}

```javascript
// getting specifications for all required fields:
let outputSpec = this.getOptions().specs.output_spec,
     requiredFields = Object.keys(outputSpec)
                            .filter(key => outputSpec[key].required)
                            .reduce((item, key) => (item[key] = outputSpec[key], item), {});
```

{% endcut %}

#### getSandboxChannel()

Возвращает ссылку на активный канал для обмена сообщениями между родительской страницей и фреймом задания. Если канала нет, создает его.

{% cut "Пример" %}

```javascript
// subscribe to all messages and show them
this.getSandboxChannel().on('*', (name, message) => console.log(message));

// ask the parent page to show task instructions
// there is also a separate service for this TaskInterface
this.getSandboxChannel().triggerOut('task:interface:show:instruction');
```

{% endcut %}

#### getTaskSuite()

Возвращает ссылку на экземпляр [TaskSuite](tasksuite.md).

#### getTaskSuiteContainer()

Возвращает `document.body` рабочего пространства исполнителя.

#### getWorkspaceOptions()

Возвращает объект с настройками рабочего пространства исполнителя.

Наиболее важные настройки:

- `agent` — для заданий в полной версии принимает значение `FRONTEND`, в мобильном приложении для Android — `ANDROID` и т. д.

- `isReadOnly` — флаг режима «только для чтения» (например, просмотр истории выполненных заданий).

- `isReviewMode` — флаг режима ревью (например, приемка выполненных заданий). Этой настройкой и `isReadOnly` удобно пользоваться, если вы, например, захотите изменить компоновку шаблона в режиме просмотра истории.

- `language` — двухбуквенный код языка, выбранного исполнителем в настройках Толоки. Им удобно пользоваться для создания многоязычных шаблонов.

- `origin` — FQDN родительской страницы.

#### pause()

Приостанавливает выполнение задания (например, по команде `request:assignment:pause` от головной страницы), вызывает `onPause`.

#### provideSolutions(strategy)

Собирает ответы на все задания ([`TolokaTaskSuite.getSolutions()`](tasksuite.md#getSolutions)), валидирует их ([`TolokaTaskSuite.validate()`](tasksuite.md#validate)). При успешной валидации вызывает `strategy`, при неуспешной — отправляет запрос `assignment:validation:fail` и объект со списком ошибок, который вернул валидатор. Параметр:

- `strategy`: функция, которая отправляет в родительскую страницу сообщение об отправке результатов (`assignment:submit`), массив ответов и `assignmentId`.

{% cut "Пример" %}

```javascript
provideSolutions(strategy = function(solutions) {
        this.getSandboxChannel().triggerOut('assignment:submit', { solutions, assignmentId: this.getId() });
    }, errorCallback = function(errors) {
        //do nothing by default
    }) {
        const solutions = this.getTaskSuite().getSolutions();

        Promise.resolve(this.getTaskSuite().validate(solutions))
            .then((errors) => {
                if (!errors) {
                    strategy.call(this, solutions);
                } else {
                    this.getSandboxChannel().triggerOut('assignment:validation:fail', errors);
                    errorCallback.call(this, errors);
                }
            });
    }
```

{% endcut %}

#### resume()

Продолжает выполнение задания, вызывает `onResume` и [`start`](#Start).

#### skip()

Позволяет пропустить текущее задание, эквивалентно нажатию кнопки **Пропустить**.

#### start()

Выполняет все необходимые действия при запуске набора заданий — добавляет в `document.body` отрендеренный интерфейс заданий, инициализирует горячие клавиши для всего интерфейса исполнителя ([`InitHotkeys`](#InitHotkeys)), вызывает `onStart`.

#### submit

Собирает, валидирует и отправляет выполненные задания, для этого вызывается [`provideSolutions`](#ProvideSolutions).

#### Пример

```javascript
// in some scenarios, you might need to set delayed sending
// in that case, you can programmatically hide the send button in the project settings
// for example, from TolokaTask
this.getDOMElement().querySelector('.my_submit_button').addEventListener('click', (event) => this.getAssignment().submit());
```

{% include [contact-support](../../_includes/contact-support-help.md) %}