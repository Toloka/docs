# Специальные компоненты и хелперы

{% include [deprecate](../../_includes/deprecate.md) %}

{% note info %}

Справочник по настройке интерфейса описывает работу редактора HTML/JS/CSS. Вы также можете попробовать создать интерфейс задания в [Конструкторе шаблонов](../../template-builder/reference/index.md).

{% endnote %}

Для создания [интерфейса задания](../../glossary.md#task-interface) в [блоке **HTML**](spec.md) на странице [проекта](../../glossary.md#project) можно использовать:

- [Выражения и хелперы Handlebars](t-components/handlebars.md) (см. [описание на сайте шаблонизатора](https://handlebarsjs.com/)).

- Дополнительные хелперы:

    - [Конкатенация](t-components/helpers.md#concat)
    - [Операции с объектом](t-components/helpers.md#object)
    - [Логические операции и сравнения](t-components/helpers.md#equal)
    - [Запись значений в JSON поля выходных данных](t-components/helpers.md#js_fields)

- Компоненты для решения популярных задач:

    - [Поле для ввода строки](t-components/string.md)
    - [Поле для ввода текста](t-components/text.md)
    - [Поле для ввода строки с саджестом](t-components/suggest.md)
    - [Переключатель](t-components/radiobuttons.md)
    - [Флажок](t-components/checkboxes.md)
    - [Выпадающий список](t-components/list.md)
    - [Кнопка для загрузки файла](t-components/upload-file.md)
    - [Кнопка для загрузки картинки](t-components/upload-picture.md)
    - [Кнопка для записи и загрузки аудио](t-components/upload-audio.md)
    - [Кнопка с проверкой перехода по ссылке](t-components/button-link.md)
    - [Картинка с возможностью выделения областей](t-components/image-annotation.md)
    - [Редактор для сегментации текста](t-components/segmentation-editor.md)
    - [Картинка](t-components/img.md)
    - [Кнопка](t-components/button.md)
    - [Встроенный фрейм](t-components/iframe.md)
    - [Отформатированный текст в HTML](t-components/html.md)

Библиотеки для использования Handlebars и специальных компонентов подключены по умолчанию при создании проекта.

{% include [contact-support](../_includes/contact-support.md) %}