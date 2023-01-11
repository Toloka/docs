# condition.not

{% include [deprecate](../../_includes/deprecate.md) %}

Возвращает значение, обратное заданному условию. Например, если заданное условие выполняется (возвращает значение `true`), то
`condition.not` вернет `false`.

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/o9jHykBa3twn9w)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "condition.not" | Задает тип компонента. ||
|| `condition` | _condition_ | Условие, для которого возвращается обратное значение. ||
|| `hint` | _string_ | Сообщение об ошибке валидации, которое увидит исполнитель ||
|#
