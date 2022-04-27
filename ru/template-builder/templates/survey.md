# Опрос

В Толоке есть шаблон  (). В нем уже настроена валидация и внешний вид задания.

#### Из каких компонентов состоит этот пример

- [field.radio-group](../reference/field.radio-group.md) — позволяет выбрать один из вариантов ответа;
- [field.checkbox-group](../reference/field.checkbox-group.md) — позволяет выбрать один или несколько вариантов ответа;
- [field.text](../reference/field.text.md) — позволяет ввести однострочный текст;
- [condition.required](../reference/condition.required.md) — проверяет, что выбран хотя бы один вариант;
- [plugin.toloka](../reference/plugin.toloka.md) — настраивает внешний вид задания.


## Что еще можно настроить {#examples}

- Если от пользователя требуется вводить длинный текст, то добавьте поле для многострочного текста [field.textarea](../reference/field.textarea.md) вместо [field.text](../reference/field.text.md).

- Добавьте компонент [field.button-radio-group](../reference/field.button-radio-group.md) в виде кнопок. Кнопки лучше подходят, когда в вопросе 2-4 варианта с короткими названиями. Если вариантов много, то лучше использовать переключатель [field.radio-group](../reference/field.radio-group.md).


Если вам не подходит этот шаблон, посмотрите другие примеры в этом разделе.


## Выделить блоки вопросов {#add-group-divider}

Способы выделения блоков вопросов:

#### Рамка

Используйте компонент [view.group](../reference/view.group.md) — выделение с помощью рамки.

#### Горизонтальный разделитель

Используйте компонент [view.divider](../reference/view.divider.md) — горизонтальный разделитель.


## Добавить кнопки и зависимые от них варианты ответа {#add-buttons-radio}

С помощью [helper.switch](../reference/helper.switch.md) можно показывать элемент интерфейса только при выборе определенного ответа. В примере после нажатия одной из двух кнопок пользователю предлагается соответствующий список вариантов.


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
