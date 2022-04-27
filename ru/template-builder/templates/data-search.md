# Поиск данных в сети

В Толоке есть шаблон  (). В нем уже настроена валидация и внешний вид задания. В этом шаблоне исполнителю предлагается ввести контактную информацию об организации на основе поиска данных в сети.

#### Из каких компонентов состоит этот пример

- [view.text](../reference/view.text.md) — позволяет добавить текст к заданию;
- [view.link-group](../reference/view.link-group.md) — объединяет ссылки в группы;
- [helper.search-query](../reference/helper.search-query.md) — позволяет создать поисковой запрос;
- сочетание [helper.if](../reference/helper.if.md) и [condition.equals](../reference/condition.equals.md) — прячет поля для ввода контактов, если нажато <q>Нет контактов</q>;
- [field.checkbox](../reference/field.checkbox.md) — позволяет добавить переключатель в виде галочки;
- [field.phone-number](../reference/field.phone-number.md) — позволяет добавить поле для ввода номера телефона;
- [field.email](../reference/field.email.md) — позволяет добавить поле для ввода адреса электронной почты;
- сочетание [condition.any](../reference/condition.any.md), [condition.required](../reference/condition.required.md) и [condition.equals](../reference/condition.equals.md) — проверяет, что заполнено одно из полей <q>Телефон</q> или <q>Email</q>, либо использован вариант <q>Нет контактов</q>;
- [plugin.toloka](../reference/plugin.toloka.md) — настраивает внешний вид задания.


## Что еще можно настроить {#examples}

- Если от пользователя требуется вводить длинный текст, то добавьте поле для многострочного текста [field.textarea](../reference/field.textarea.md).

- Если от пользователя требуется ввести число, добавьте поле [field.number](../reference/field.number.md).

- Если от пользователя требуется найти в интернете файл, добавьте поле для выбора файла [field.file](../reference/field.file.md). Например, если нужно загрузить фото с определенным предметом на нем.

    В режиме проверки задания загруженные изображения появятся автоматически. Изображения можно просматривать, поворачивать и переключаться между ними.

- Если от пользователя требуется найти и вставить ссылку на определенную страницу с этого сайта, добавьте компонент [condition.same-domain](../reference/condition.same-domain.md). Компонент проверит, что ссылка с того домена, который требуется.


Если вам не подходит этот шаблон, посмотрите другие примеры в этом разделе.


## Добавить поле для выбора вариантов ответа {#add-radio-group}

Если от пользователя требуется перейти по ссылке поиска и ответить на вопрос, добавьте поле [field.radio-group](../reference/field.radio-group.md) для выбора одного из вариантов ответа.


## Добавить картинку и поле для ввода даты {#add-image-date}

Например, для поиска информации об актере по имени и фотографии.

В этом примере добавлены:

- картинка [view.image](../reference/view.image.md);
- поле для ввода короткого текста [field.text](../reference/field.text.md);
- поле для ввода даты рождения [field.date](../reference/field.date.md).


## Разделить интерфейс задания на колонки {#add-layout-columns}

Другой вариант задания, в котором пользователь должен найти информацию об организации.

В этом примере добавлены:

- компонент [layout.columns](../reference/layout.columns.md) позволяет разместить в две колонки описание задания и страницу сайта внутри компонента [view.iframe](../reference/view.iframe.md);
- текст задания [view.text](../reference/view.text.md);
- ссылка на сайт [view.link](../reference/view.link.md);
- кнопки вариантов ответа [field.button-radio-group](../reference/field.button-radio-group.md);
- компонент [condition.schema](../reference/condition.schema.md) проверяет формат введенных данных, в данном случае — форматы ИНН и ОГРН.


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
