# view.group

{% include [deprecate](../../_includes/deprecate.md) %}

Объединяет любые компоненты в визуальные группы — блоки с рамкой.

[![](../_images/buttons/view-example.svg)](https://clck.ru/QRZF6)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "view.group" | Задает тип компонента. ||
|| `label` | _string_ | Заголовок группы. ||
|| `content` | _view_ | Содержимое блока-группы. ||
|| `hint` | _string_ | Пояснение к заголовку группы. Для вставки переноса строки используйте `\n`. ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
