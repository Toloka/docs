# Класс Task

{% include [toloka-requester-source-html-editor-tb](../../_includes/toloka-requester-source/id-toloka-requester-source/html-editor-tb.md) %}

Базовый класс `Task` отвечает за [интерфейс задания](../../../glossary.md#task-interface-ru). Класс доступен в глобальной переменной `window.TolokaTask`.

Методы:

#### blur()

Реализует логику снятия фокуса с задания, вызывает метод [`onBlur()`](#onBlur).

#### constructor(options)

Конструктор [интерфейса задания](../spec.md).

Параметры:

- `options.task` — модель задания [Task](../spec-advanced.md#obj-task).
- `options.specs` — параметры [входных и выходных данных](../../../glossary.md#input-output-data-ru), интерфейса заданий.
- `options.workspaceOptions` — параметры инициализации рабочего пространства исполнителя.

#### destroy()

Освобождает занятые в глобальном пространстве ресурсы, сервисы, обработчики событий. Вызывает [`onDestroy()`](#onDestroy).

#### focus()

Реализует логику установки фокуса на задание, вызывает метод `[onFocus()](#onFocus)`.

#### getAssignment()

Возвращает ссылку на экземпляр класса `TolokaAssignment`. После этого можно обращаться ко всем его свойствам и методам.

#### Пример

```javascript
// skip current assignment
this.getAssignment().skip()
```

#### getDOMElement()

Возвращает DOM-элемент задания.

#### getOptions()

Возвращает объект с набором параметров, переданных методу `[constructor()](#constructor)` при инициализации.

#### Пример

```javascript
// getting specifications for all required fields:
let outputSpec = this.getOptions().specs.output_spec,
     requiredFields = Object.keys(outputSpec)
                            .filter(key => outputSpec[key].required)
                            .reduce((item, key) => (item[key] = outputSpec[key], item), {});
```

#### getSavedState()

Возвращает сохраненное состояние задания (объект).

Получает из локального хранилища браузера сохраненное состояние задания по ключу `TASK_STATE:{assignmentId}:{taskId}`.

#### getSolution()

Возвращает ответы задания [`Solution`](../spec-advanced.md#obj-solution).

#### getStyleDOMElement()

Возвращает DOM-элемент для стилей задания, который добавляется в `document.head` при отрисовке.

#### getTask()

Возвращает модель задания [`Task`](../spec-advanced.md#obj-task).

#### getTemplateData()

Возвращает объект, который получит шаблонизатор перед компиляцией шаблона задания.

Метод доступен в toloka-handlebars-templates. Он возвращает набор полей и их значений, переданный на вход задания: `return this.getTask().input_values`.

Метод позволяет обрабатывать существующие значения или передавать в шаблонизатор новые кастомные параметры. Например, можно передать строки для локализации шаблона и использовать один и тот же проект для русскоязычных и англоязычных исполнителей.

#### Пример

```javascript
// if the user completes the assignment under iOS, we show additional layout
getTemplateData: function() {
    let data = TolokaHandlebarsTask.prototype.getTemplateData.call(this),
        userAgent = navigator.userAgent || navigator.vendor || window.opera;


    if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
        data.ios = true;
    }

    return data;
}
```

#### getWorkspaceOptions()

Возвращает параметры инициализации рабочего пространства исполнителя, переданные методу `constructor()`.

#### hideTaskError()

Cкрывает глобальную ошибку (только если подключена библиотека toloka-handlebars-templates).

#### id

Содержит `id` текущего задания.

#### Пример

```javascript
let myId = this.getTask().id
```

#### onBlur()

Вызывается после удаления фокуса.

#### onDestroy()

Вызывается после уничтожения задания (`[destroy()](#destroy)`). Наиболее подходящий метод для очистки занятой памяти, удаления глобальных обработчиков событий, DOM-элементов и т. п.

#### onFocus()

Вызывается после установки фокуса.

#### onKey(key)
Передает нажатую клавишу. Параметр:

- `key` — буквенно-числовой символ, нажатый на клавиатуре. Может быть использован как горячая клавиша.

#### onPause()

Вызывается после приостановки выполнения задания.

#### onRender()

Вызывается после отрисовки задания (`[render()](#render)`). Все манипуляции с DOM-элементом задания следует производить здесь.

#### onResume(savedState)

Вызывается после возобновления выполнения задания.

#### onValidationFail(errors)

Вызывается после неудачной валидации ответа исполнителя. Параметр:

- `errors` — ошибки валидации ответа исполнителя `[SolutionValidationError](../spec-advanced.md#obj-solutionvalidationerror)`.

#### pause()

Приостанавливает выполнение задания. Сохраняет промежуточное состояние в локальном хранилище браузера (`saveState`) и вызывает метод `onPause`.

#### render()

Формирует DOM-представление интерфейса задания. Вызывает `[onRender()](#onRender)`. Возвращает `this`.

#### resume()

Возобновляет выполнение задания. Получает из локального хранилища браузера сохраненное состояние. Восстанавливает из него набор ответов и заново выполняет незавершенные в прошлом сеансе запросы в сервисах file и webview. Вызывает `onResume`.

#### saveState()

Проверяет `assignmentId`, чтобы убедиться, что задание работает в режиме исполнителя, а не в превью. Получает набор ответов, а также необработанные запросы в сервисах file и webview. Используя сервис storage, сохраняет их в локальное хранилище браузера c ключом `TASK_STATE:{assignmentId}:{taskId}`.

#### setSolution(solution)

Устанавливает ответы. Параметр:

- `solution` — ответ исполнителя на задание (`[Solution](../spec-advanced.md#obj-solution)`).

#### setSolutionOutputValue(fieldName, value)

Записывает требуемое значение в указанное поле. Параметры:

- `fieldName` — поле (строка) в выходной спецификации, в которое будет передано значение.
- `value` — значение заданного для `fieldName` типа в спецификации проекта.

#### setSolutionOutputValues(outputValues)

Обновляет выходную спецификацию, записывая в нее переданный объект с ответами. Вызывает `saveState` для сохранения промежуточных результатов в локальном хранилище браузера. Параметр:

- `outputValues` — объект с ответами.

#### showTaskError(message)

Принудительно показывает глобальную ошибку в задании (только если подключена библиотека toloka-handlebars-templates). Параметры:

- `message` — текст ошибки (строка).

#### template(data)

Шаблонизатор задания. В [HTML-интерфейсе](../spec.md) задания заменяет вхождения типа `${fieldX}` на соответствующее значение с ключем `fieldX` из параметра `data`. Возвращает HTML-интерфейс задания в виде строки. Параметр:

- `data` — объект с данными для подстановки в шаблон.

#### validate(solution)

Валидирует ответы согласно параметрам выходных данных. Возращает [`SolutionValidationError`](../spec-advanced.md#obj-solutionvalidationerror), если ответы не корректные, или `null`. Параметр:

- `solution` — ответ исполнителя на задание. Если не передан, то используется текущее ([`getSolution()`](#getSolution)).

{% include [contact-support](../../_includes/contact-support-help.md) %}