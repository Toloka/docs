# Класс TaskSuite

{% include [deprecate](../../../_includes/deprecate.md) %}

{% include [toloka-requester-source-html-editor-tb](../../_includes/toloka-requester-source/id-toloka-requester-source/html-editor-tb.md) %}

«Класс-обертка» для [страницы заданий](../../../glossary.md#task-suite), создает экземпляры классов заданий. Вы можете переопределить этот класс, например, чтобы отобразить общий элемент на странице с заданиями или получить больший контроль над заданиями (нестандартные горячие клавиши или т.п.).

Основная задача класса `TaskSuite` — отрисовать задания на странице (`[render()](#render)`). Через него также происходит сбор ответов (`[getSolutions()](#getSolutions)`), валидация (`[validate(solutions)](#validate)`) и управление горячими клавишами ([`focusNextTask()`](#focusNextTask), [`onKey(key)`](#onKey) и т. д.).

Базовый класс для `TaskSuite` доступен в глобальной переменной `window.TolokaTaskSuite`.

Методы:

#### constructor(options)

Конструктор базового класса страницы заданий.

Параметры:

- `options.task` — массив моделей задания [Task](../spec-advanced.md#obj-task).

- `options.specs` — параметры [входных и выходных данных](../../../glossary.md#input-output-data), интерфейса заданий.

- `options.assignmentId` — идентификаторы заданий на странице.

- `options.workspaceOptions` — параметры инициализации рабочего пространства исполнителя.

- `options.TaskClass` — массив классов создаваемых заданий.

- `options.solutions` — массив ответов [`Solution`](../spec-advanced.md#obj-solution). Может быть пуст.

#### destroy()

Уничтожает все задания страницы. Освобождает занятые в глобальном пространстве ресурсы, сервисы, обработчики событий. Вызывает [`onDestroy()`](#onDestroy).

#### focusNextTask()

Устанавливает фокус на следующее задание.

#### focusPreviousTask()

Устанавливает фокус на предыдущее задание.

#### focusTask(index)

Устанавливает фокус на задание по индексу. Параметр:

- `index` — индекс задания на странице.

#### getAssignment()

Возвращает ссылку на экземпляр класса [`Assignment`](assignment.md). После этого вы можете использовать все свойства и методы экземпляра класса.

{% cut "Пример" %}

```javascript
// skip current assignment
this.getAssignment().skip();
```

{% endcut %}

#### getDOMElement()

Возвращает DOM-элемент страницы (до отрисовки пустой, после — инициализированный, содержащий интерфейс).

#### getFocusedTask()

Возвращает ссылку на активное задание. Получает индекс активного задания из приватного свойства `_focusedTaskIndex` и возвращает ссылку на это задание с помощью `[getTasks()](#getTasks)`.

{% cut "Пример" %}

```javascript
// remove the class .some_class from all elements of the active task
let elements = Array.from(this.getFocusedTask().getDOMElement().querySelectorAll('.some_class'));
elements.forEach(el => el.classList.remove('some_class'));
```

{% endcut %}

#### getOptions()

Возвращает объект с набором параметров, переданных методу `[constructor()](#constructor)` при инициализации.

{% cut "Пример" %}

```javascript
// getting specifications for all required fields:
let outputSpec = this.getOptions().specs.output_spec,
     requiredFields = Object.keys(outputSpec)
                            .filter(key => outputSpec[key].required)
                            .reduce((item, key) => (item[key] = outputSpec[key], item), {});
```

{% endcut %}

#### getProxyUrl(path)

Возвращает полный URL для доступа к данным на [прокси-сервере](../prepare-data.md). Параметр:

- `path` — относительный путь к файлу.

#### getSolutions()

Возвращает массив ответов [`Solution`](../spec-advanced.md#obj-solution).

#### getStyleDOMElement()

Возвращает DOM-элемент стилей страницы.

#### getTasks()

Возвращает массив инициализированных моделей задания `[Task](../spec-advanced.md#obj-task)`.

#### getTasksDOMElement()

Возвращает DOM-элемент набора заданий (`div.task-suite`). Если DOM-элемент отсутствует, то метод создает его.

#### getTasksIndexed()

Возвращает задания, индексированные по идентификаторам: `"<taskId>": [Task](../spec-advanced.md#obj-task), …`

#### getWorkspaceOptions()

Возвращает объект с настройками рабочего пространства исполнителя.

Наиболее важные настройки:

- `agent` — для заданий в полной версии принимает значение `FRONTEND`, в мобильном приложении для Android — `ANDROID` и т. д.

- `isReadOnly` — флаг режима «только для чтения» (например, просмотр истории выполненных заданий).

- `isReviewMode` — флаг режима ревью (например, приемка выполненных заданий). Этой настройкой и `isReadOnly` удобно пользоваться, если вы, например, захотите изменить компоновку шаблона в режиме просмотра истории.

- `language` — двухбуквенный код языка, выбранного исполнителем в настройках Толоки. Им удобно пользоваться для создания многоязычных шаблонов.

- `origin` — FQDN родительской страницы.

#### initHotkeys()

Инициализатор обработчиков горячих клавиш:

- Устанавливает фокус на предыдущее задание по стрелке влево/вверх.

- Устанавливает фокус на следующее задание по стрелке вправо/вниз.

- Передает нажимаемые клавиши активному заданию.

- Устанавливает фокус на первое задание.

#### onDestroy()

Метод, который вы можете переопределить, чтобы выполнить свой код при уничтожении набора заданий. Вызывается после уничтожения страницы (`[destroy()](#destroy)`). Наиболее подходящий метод для очистки занятой памяти, удаления глобальных обработчиков событий, DOM-элементов и т. п.

#### onKey(key)

Передает нажатую клавишу активному заданию.

#### onPause()

Метод, который вы можете переопределить, чтобы выполнить свой код при остановке работы страницы заданий.

#### onRender()

Метод, который вы можете переопределить, чтобы выполнить свой код при отрисовке страницы заданий. Вызывается после отрисовки страницы (`[render()](#render)`). Все манипуляции с DOM-элементом задания следует производить здесь.

#### onResume()

Метод, который вы можете переопределить, чтобы выполнить свой код при возобновлении работы страницы заданий.

#### onValidationFail(errors)

Вызывается после неудачной валидации с описанием ошибок в параметре. Параметр:

- `errors` — массив ошибок [`SolutionValidationError`](../spec-advanced.md#obj-solutionvalidationerror).

#### pause()

Вызывает метод `pause()` для каждого задания в наборе. Также вызывает метод `[onPause()](#onPause)`.

#### proxy(path, options)

Делает GET/POST запрос через прокси. Возвращает результат запроса в виде объекта. Параметры:

- Строка `path` — путь запроса.

- Объект `options` — параметры запроса, см. [описание параметров](https://api.jquery.com/jquery.ajax/#jQuery-ajax-settings) Jquery Ajax.

{% note alert %}

Некоторые возможности (например, таймауты или кастомные заголовки) не поддерживаются.

{% endnote %}

{% cut "Пример" %}

```javascript
// we need to find usernames starting with 'ivanov' and 'egorov' (no more than 10 of each)
// we make two POST requests to the search service
// then wait for results

let promises = [],
patterns = ['jones*', 'smith*'];

patterns.forEach(pattern => promises.push(Promise.resolve(this.proxy('myproxy/search', {
   type: 'POST',
   contentType: 'application/json',
   dataType: 'json',
   data: JSON.stringify({
      query: pattern,
      limit: 10
   }),
   processData: false
}))));

Promise.all(promises)
.then(results => console.log(results))
.catch(error => console.error(error));
```

{% endcut %}

#### render()

Формирует DOM-представление страницы заданий: отрисовывает все задания на странице — вызывает [`render()` класса `Task`](task.md#render) для каждого задания. Вызывает `[onRender()](#onRender)`. Возвращает `this`.

#### validate(solutions)

Валидирует ответы согласно параметрам выходных данных. Возращает объект `promise` с массивом ошибок [`SolutionValidationError`](../spec-advanced.md#obj-solutionvalidationerror), если ответы некорректные, или `null`. Параметр:

- `solutions` — массив ответ исполнителя на задания. Если не передан, то используются текущие ([`getSolutions()`](#getSolutions)).

{% include [contact-support](../../_includes/contact-support-help.md) %}