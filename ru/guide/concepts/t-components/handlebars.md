# Выражения и хелперы

{% include [deprecate](../../../_includes/deprecate.md) %}

{% note info %}

Справочник по настройке интерфейса описывает работу редактора HTML/JS/CSS. Вы также можете попробовать создать интерфейс задания в {% if locale == "ru-ru" %}[Конструкторе шаблонов](../../../template-builder/reference/index.md){% endif %}{% if locale == "en-com" %}[Template Builder](../../../../en/docs/template-builder/reference/index.md){% endif %}.

{% endnote %}

Handlebars — это шаблонизатор, который упрощает создание HTML за счет использования шаблонов.

Шаблоны выглядят как обычный HTML-код, в который добавлены [выражения Handlebars](#expressions). Когда шаблон выполняется, выражения заменяются значениями входных параметров.

По умолчанию в проект подключается библиотека `toloka-handlebars-templates`. Она содержит набор удобных компонентов и предоставляет классы `TolokaHandlebarsTask` и `TolokaHandlebarsTaskSuite`, которые дополняют и расширяют базовые классы `[TolokaTask](../js/task.md)` и `[TolokaTaskSuite](../js/tasksuite.md)`.

## Выражения {#expressions}

Выражения заключены в двойные фигурные скобки. В этом случае их значение автоматически экранируется.

```html
<input type="text" placeholder="not_var{{i18n.hint}}" name="{{concat "field_" name}}" value="not_var{{value}}">
```

Если нужно вывести неэкранированное значение вы можете:

- Указать его в тройных скобках: `{not_var{{raw}}}`

- Написать свой хелпер, который будет возвращать значение в неэкранированном виде: `return new Handlebars.SafeString(value)`

    {% note alert %}

    Учтите, что это небезопасно! Всегда проверяйте все входные данные, которые вы отображаете в шаблоне. Экранировать данные в хелпере можно с помощью метода `Handlebars.Utils.escapeExpression` .

    {% endnote %}

Чтобы в выражении Handlebars получить значение вложенного параметра, используйте точку в качестве разделителя между именами параметров.

Например, чтобы из кода в формате JSON

```json
{
    "id": 123,
    "link": {
        "title": "<b>Toloka</b>",
        "url": "https://toloka.ai"
    }
}
```

подтянуть значения вложенных в `link` параметров `title` и `url`, укажите путь к ним через точку:

```html
id: not_var{{id}}<a href="not_var{{link.url}}">not_var{{link.title}}</a>
```

Комментарии тоже являются выражениями Handlebars: `{{!комментарий}}` или `{{!-- комментарий --}}`.

## Хелперы {#helpers}

Хелперы — это функции, которым можно передать любое количество выражений. После обработки результата они возвращают HTML-код.

Свой хелпер можно зарегистрировать с помощью метода `Handlebars.registerHelper`. Например:

Хелпер для экранирования параметра `title` из приведенного выше [кода в формате JSON](#expressions):

```html
Handlebars.registerHelper('escape', (title, url) => new Handlebars.SafeString(`<a href="${Handlebars.escapeExpression(url)}">${Handlebars.escapeExpression(title)}</a>`));
```

Вызов хелпера:

```html
not_var{{escape link.title link.url}}
```

Результат — HTML-код верстки, в которой будет экранирован параметр `title`, а добавленный в хелпере тег останется без изменений:

```html
<a href="https://toloka.ai">&lt;b&gt;Toloka&lt;/b&gt;</a>
```

Хелперам можно передавать на вход другие хелперы, для этого их нужно заключить в круглые скобки:

```html
{{or (equal title "Toloka") (equal title "Google")}}
```

{% note info %}

Прежде чем создавать собственный хелпер Handlebars, поищите нужный:

- в списке [доступных компонентов и хелперов Толоки](../t-components.md);

- в [репозитории хелперов Handlebars](https://github.com/helpers/handlebars-helpers).

{% endnote %}

## Блочные хелперы {#block-helpers}

Блочные хелперы позволяют определить функционал, с помощью которого можно вызвать переданный блок в новом контексте.

Чтобы указать, что вы вызываете блочный хелпер, добавьте в его имя решетку: `{{#if}}`. В отличие от обычного хелпера, блочный хелпер нужно закрыть. Закрывается блочный хелпер так же, как и обычный тег: `{{/if}}`.

В Handlebars уже есть встроенные блочные хелперы: [If](#if), [Unless](#unless), [Each](#each), [With](#with).

[Подробнее про блочные хелперы](https://handlebarsjs.com/guide/block-helpers.html#the-with-helper)

### If {#if}

Вывод блока по условию. Если аргумент этого хелпера вернет значение false, то блок внутри хелпера не будет выполнен:

```html
{{#if (equal id "123")}}
    ... {{!Блок кода только для id 123}}
not_var{{else}}
    ... {{!Блок кода для всех остальных значений}}
{{/if}}
```

### Unless {#unless}

Хелпер обратный хелперу `if`. Блок будет выведен, если аргумент вернет значение false.

```html
{{#unless (equal id "123")}}
    ... {{!Блок кода для всех значений id, отличных от 123}}
not_var{{else}}
    ... {{!Блок кода только для id 123}}
{{/unless}}
```

### Each {#each}

Хелпер для перебора списков. Чтобы обратиться к текущему элементу внутри списка, используйте `this`.

{% note info %}

Для обращения к элементу не из текущего блочного контекста необходимо перейти на вышестоящий уровень, используя `../`

{% endnote %}

Например, для списка

```json
{
    "id": 123,
    "links": [
        { "url": "https://toloka.ai", "title": "Toloka" },
        { "url": "https://google.com", "title": "Google" }
    ]
}
```

хелпер, выводящий значения каждого элемента списка (в данном случае ссылки), будет выглядеть так:

```html
{{#each links}}
    ID: {{../id}}
    <a href="not_var{{this.url}}">not_var{{this.title}}</a>
{{/each}}
```

Внутри блока `Each` доступны вспомогательные выражения:

- `{{@key}}` — название текущего ключа;
- `{{@index}}` — текущий индекс;
- `{{@first}}` — true, если это первый элемент массива;
- `{{@last}}` — true, если это последний элемент массива.

Для приведенного в предыдущем примере [списка](#each) хелпер

```html
{{#each links}}
    Глобальный ID: {{../id}}
    {{@index}}: <a href="not_var{{this.url}}">not_var{{this.title}}</a>
    {{#unless @last}}<hr>{{/unless}}
{{/each}}
```

выведет ссылки, при этом:

- ссылки будут пронумерованы;
- после каждой ссылки, кроме последней, будет добавлен горизонтальный разделитель.

### With {#with}

Позволяет перепривязать контекст.

Например, для кода

```json
{
    "id": 123,
    "link": {
        "title": "<b>Toloka</b>",
        "url": "https://toloka.ai"
    }
}
```

хелпер, который отображает блок в другом контексте, помогая при этом избежать употребления имени родительского параметра, будет выглядеть так:

```html
ID: not_var{{id}}
{{#with link}}
    <a href="not_var{{url}}">not_var{{title}}</a>
{{/with}}
```

## Повторное использование шаблонов (partials) {#partials}

Partials позволяют переиспользовать целые секции кода. Это обычные шаблоны, которые могут вызываться другими шаблонами. Например:

Необходимо в нескольких местах вывести однотипную верстку:

```html
<h3>Поле</h3>
{{field type="input" name="field_name"}}
```

Чтобы избежать копирования кода, можно зарегистрировать новый partial:

```html
Handlebars.registerPartial('formInput', '<h3>not_var{{fieldTitle}}</h3>{{field type="input" name=fieldName}}');
```

Вызов шаблона для вставки верстки в форму:

```html
{{> formInput fieldTitle="Поле 1" fieldName="my_field"}}
<p>Параграф с текстом</p>
{{> formInput fieldTitle="Поле 2" fieldName="some_other_field"}}
```

Результат:

```html
<h3>Поле 1</h3>
{{field type="input" name="my_field"}}
<p>Параграф с текстом</p>
<h3>Поле 2</h3>
{{field type="input" name="some_other_field"}}
```

{% include [contact-support](../../_includes/contact-support.md) %}