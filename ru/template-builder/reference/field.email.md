# field.email

{% include [deprecate](../../_includes/deprecate.md) %}

Создает поле для ввода адреса электронной почты.

Проверяет, что в тексте есть символ `@`. Другие условия [настройте самостоятельно](../best-practices/conditions.md).

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/RoF9DiUG3tz7Zk)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.email" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `placeholder` | _string_ | Полупрозрачная надпись, которая отображается в пустом поле. ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
