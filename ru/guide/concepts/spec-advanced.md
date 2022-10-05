# Как использовать JavaScript-расширения

{% include [toloka-requester-source-html-editor-tb](../_includes/toloka-requester-source/id-toloka-requester-source/html-editor-tb.md) %}


Все аспекты [жизненного цикла](#lifecycle) заданий контролируются тремя JavaScript-классами:

- [Assignment](js/assignment.md) управляет ходом выполнения задания, обрабатывает команды страницы заданий на отправку ответов, пропуск, приостановку задания и т. п. Также он создает экземпляр класса [TaskSuite](js/tasksuite.md).

- [TaskSuite](js/tasksuite.md) — «класс-обертка» для интерфейса [страницы заданий](../../glossary.md#task-page). Вы можете переопределить этот класс, чтобы, например, отобразить общий элемент на этой странице.

- [Task](js/task.md) отвечает за отрисовку и валидацию отдельного задания. Если от задания требуется нестандартное поведение, как правило, следует расширять именно его.


Для решения специфических задач, таких как подписка на нажатие клавиш или получение GPS-координат исполнителя, можно использовать [сервисы](js/services.md).


## Жизненный цикл задания {#lifecycle}

Когда исполнитель приступает к выполнению заданий, во встроенном фрейме инициализируется его рабочее пространство. Между головной страницей Толоки и фреймом устанавливается канал для обмена сообщениями. Сначала запрашивается список заданий и создается экземпляр класса [`Assignment`](js/assignment.md). Далее полученный список передается классу [`TaskSuite`](js/tasksuite.md). Он создает экземпляр класса [`Task`](js/task.md) для каждого задания.

#### Отрисовка

Для отрисовки страницы заданий вызывается метод [`render()`](js/tasksuite.md#render) класса `TaskSuite`. Этот метод вызывает метод [`render()`](js/task.md#render) класса `Task` для каждого из заданий и собирает созданные компоненты DOM-дерева в единый список.

Здесь вы можете изменять отрисовку задания и страницы заданий.

#### Валидация ответов

Когда исполнитель нажимает на кнопку **Отправить**, вызывается метод [`TaskSuite.validate(solutions)`](js/tasksuite.md#validate) для валидации ответов исполнителя. Он вызывает метод [`Task.validate(solutions)`](js/task.md#validate) для каждого задания и возвращает ошибки.

Здесь вы можете проводить дополнительную проверку ответов исполнителя.

#### Удаление

Когда исполнитель закончил все задания на странице или [пропустил](pool_statistic-pool.md#skipped-tasks) ее, вызывается метод [`destroy()`](js/tasksuite.md#destroy) класса `TaskSuite`. Он вызывает метод [`destroy()`](js/task.md#destroy) класса `Task` для каждого задания. Эти методы освобождают ресурсы и удаляют сервисы и обработчики событий, связанные с заданиями.


## Наследование классов {#inherit}

Чтобы код не выглядел громоздким, для наследования и переопределения классов используйте функцию:

```javascript
function extend(ParentClass, constructorFunction, prototypeHash) {
    constructorFunction = constructorFunction || function() {};
    prototypeHash = prototypeHash || {};
    if (ParentClass) {
        constructorFunction.prototype = Object.create(ParentClass.prototype);
    }
    for (var i in prototypeHash) {
        constructorFunction.prototype[i] = prototypeHash[i];
    }
    return constructorFunction;
}
```

Вызов функции:

```javascript
var ChildClass = extend(ParentClass, function() {
    ParentClass.call(this);
}, {
    method: function() {}
})
```


## Типы данных {#data-spec-adv}

Объект `Task` — задание.
 {% if locale == "ru-ru" %}
```no-highlight
{
    "id": <строка>,
    "input_values": {
        "<id поля с входными данными>": <значение>,
        …
     }
}
```
{% endif %}{% if locale == "en-com" %}
```no-highlight
{
    "id": <string>,
    "input_values": {
        "<ID of the field with input data>": <value>,
        …
     }
}
```
{% endif %}

Ключ
 |
Значение

----- | -----
`id` | Идентификатор задания.
`input_values` | Входные данные задания в формате `"<id поля>":"<значение поля>"`. Пример:```no-highlight "input_values": {   "image": "http://images.com/1.png" } ```


Объект `Solution` — ответ исполнителя на задание.
 {% if locale == "ru-ru" %}
```no-highlight
{
    "task_id": <строка>,
    "output_values": {
        "<id поля ввода>": <значение>,
        …
    }
}
```
{% endif %}{% if locale == "en-com" %}
```no-highlight
{
    "task_id": <string>,
    "output_values": {
        "<input field id>": <value>,
        …
    }
}
```
{% endif %}

Ключ
 |
Значение

----- | -----
`task_id` | Идентификатор задания.
`output_values` | Ответы в формате `"<id поля ввода>":"<значение>"`. Пример: ```no-highlight "outputValues": {   "colour": "white",   "comment": "So white" } ```


Объект `SolutionValidationError` — ошибка валидации ответа исполнителя.
 {% if locale == "ru-ru" %}
```no-highlight
{
    "task_id": string,
    "errors": {
        "<id поля ввода>": {
            "code": "<код ошибки>",
            "message": "<строка>"
        },
        …
    }
}
```
{% endif %}{% if locale == "en-com" %}
```no-highlight
{
    "task_id": string,
    "errors": {
        "<input field ID>": {
            "code": "<error code>",
            "message": "<string>"
        },
        …
    }
}
```
{% endif %}

Ключ
 |
Значение

----- | -----
`task_id` | Идентификатор задания.
`errors` | Ошибки в формате: `"<id поля ввода>": {code: "<код ошибки>", message: "<сообщение об ошибке>"}`. Пример: {% if locale == "ru-ru" %}```no-highlight "errors": {      "colour": {     "code": "REQUIRED",     "message": "Обязательное поле"   } } ```{% endif %} {% if locale == "en-com" %}```no-highlight "errors": {      "colour": {     "code": "REQUIRED",     "message": "Required field"   } } ```{% endif %}

{% include [contact-support](../_includes/contact-support-help.md) %}