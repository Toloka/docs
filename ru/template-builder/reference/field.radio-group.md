# field.radio-group

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент, позволяющий выбрать одно из нескольких значений. Оформляется в виде группы переключателей (кружочков), располагающихся вертикально.

Если вы хотите оформление в виде обычных кнопок, используйте [field.button-radio-group](field.button-radio-group.md).

Минимальное количество кнопок — одна. Тип возвращаемых данных — любой.

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.radio-group" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `disabled` | _boolean_ | Свойство запрещает нажимать кнопки. Если значение — `true`, исполнителю будет недоступно нажатие. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `options`<span style="color: red">\*</span> | _array_ | Массив кнопок. ||
|| `options[]` | _object_ | Кнопка. ||
|| `options[].hint` | _string_ | Текст с дополнительной информацией. ||
|| `options[].label`<span style="color: red">\*</span> | _string_ | Название опции. ||
|| `options[].value`<span style="color: red">\*</span> | _any_ | Возвращаемое значение. ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
