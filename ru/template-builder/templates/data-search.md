# Поиск данных в сети

{% include [deprecate](../../_includes/deprecate.md) %}

В Толоке есть пресет  **Сбор контактов организаций**. В нем уже настроена валидация и внешний вид задания. В этом пресете исполнителю предлагается ввести контактную информацию об организации на основе поиска данных в сети.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/4CMD9se23vtHKd)

{% cut "Из каких компонентов состоит этот пример" %}

- [view.text](../reference/view.text.md) — позволяет добавить текст к заданию;
- [view.link-group](../reference/view.link-group.md) — объединяет ссылки в группы;
- [helper.search-query](../reference/helper.search-query.md) — позволяет создать поисковой запрос;
- сочетание [helper.if](../reference/helper.if.md) и [condition.equals](../reference/condition.equals.md) — прячет поля для ввода контактов, если нажато «Нет контактов»;
- [field.checkbox](../reference/field.checkbox.md) — позволяет добавить переключатель в виде галочки;
- [field.phone-number](../reference/field.phone-number.md) — позволяет добавить поле для ввода номера телефона;
- [field.email](../reference/field.email.md) — позволяет добавить поле для ввода адреса электронной почты;
- сочетание [condition.any](../reference/condition.any.md), [condition.required](../reference/condition.required.md) и [condition.equals](../reference/condition.equals.md) — проверяет, что заполнено одно из полей «Телефон» или «Email», либо использован вариант «Нет контактов»;
- [plugin.toloka](../reference/plugin.toloka.md) — настраивает внешний вид задания.

{% endcut %}

## Что еще можно настроить {#examples}

- Если от исполнителя требуется вводить длинный текст, то добавьте поле для многострочного текста [field.textarea](../reference/field.textarea.md).

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/7ZKw-Bsh3vtYQv)

- Если от исполнителя требуется ввести число, добавьте поле [field.number](../reference/field.number.md).

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/yfv1amPQ3xDhDP)

- Если от исполнителя требуется найти в интернете файл, добавьте поле для выбора файла [field.file](../reference/field.file.md). Например, если нужно загрузить фото с определенным предметом на нем.

  В режиме проверки задания загруженные изображения появятся автоматически. Изображения можно просматривать, поворачивать и переключаться между ними.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/b_0fklI-3xDmZf)

- Если от исполнителя требуется найти и вставить ссылку на определенную страницу с этого сайта, добавьте компонент [condition.same-domain](../reference/condition.same-domain.md). Компонент проверит, что ссылка с того домена, который требуется.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/L8s1rNan3xDnAc)

Если вам не подходит этот пресет, посмотрите другие примеры в этом разделе.

## Добавить поле для выбора вариантов ответа {#add-radio-group}

Если от исполнителя требуется перейти по ссылке поиска и ответить на вопрос, добавьте поле [field.radio-group](../reference/field.radio-group.md) для выбора одного из вариантов ответа.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/_4kpBqbj3x6uLQ)

## Добавить картинку и поле для ввода даты {#add-image-date}

Например, для поиска информации об актере по имени и фотографии.

В этом примере добавлены:

- картинка [view.image](../reference/view.image.md);
- поле для ввода короткого текста [field.text](../reference/field.text.md);
- поле для ввода даты рождения [field.date](../reference/field.date.md).

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/eVk1w9AI3vuAGm)

## Разделить интерфейс задания на колонки {#add-layout-columns}

Другой вариант задания, в котором исполнитель должен найти информацию об организации.

В этом примере добавлены:

- компонент [layout.columns](../reference/layout.columns.md) позволяет разместить в две колонки описание задания и страницу сайта внутри компонента [view.iframe](../reference/view.iframe.md);
- текст задания [view.text](../reference/view.text.md);
- ссылка на сайт [view.link](../reference/view.link.md);
- кнопки вариантов ответа [field.button-radio-group](../reference/field.button-radio-group.md);
- компонент [condition.schema](../reference/condition.schema.md) проверяет формат введенных данных, в данном случае — форматы ИНН и ОГРН.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/YIji61V83tw8Ak)

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)