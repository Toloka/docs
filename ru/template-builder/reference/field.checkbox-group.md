# field.checkbox-group

{% include [deprecate](../../_includes/deprecate.md) %}

Добавляет группу переключателей с галочками для выбора независимых вариантов ответа. Пригодится, если у вас несколько вариантов. Можно добавить только один переключатель, но это легче сделать с [field.checkbox](field.checkbox.md).

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/iO6fbx9G3twhgg)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.checkbox-group" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `disabled` | _boolean_ | Если `true`, переключатели неактивны. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `options`<span style="color: red">\*</span> | _array_ | Массив переключателей, где `value` — изменяемое значение, а `label` — текст возле переключателя. ||
|| `options[]` | _object_ | Переключатель. ||
|| `options[].hint` | _string_ | Текст с дополнительной информацией об опции. ||
|| `options[].label`<span style="color: red">\*</span> | _string_ | Текст рядом с переключателем. ||
|| `options[].value`<span style="color: red">\*</span> | _string_ | Возвращаемое значение. ||
|| `preserveFalse` | _boolean_ | Свойство указывающее, надо ли возвращать значения `false` в результатах. По умолчанию, если компонент возвращает `false`, то в выходные данные этот результат не будет добавлен. Чтобы в результаты добавлялись значения `false`, укажите `"preserveFalse": true`. ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
