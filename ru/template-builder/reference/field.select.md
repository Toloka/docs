# field.select

Кнопка для выбора из выпадающего списка. Используйте, когда список длинный, а выбрать нужно один вариант.

Для коротких списков (2-4 пункта) лучше подходят [field.radio-group](field.radio-group.md) или [field.button-radio-group](field.button-radio-group.md), в которых все варианты ответов видны сразу.

Чтобы дать возможность выбрать несколько вариантов, используйте компонент [field.checkbox-group](field.checkbox-group.md).

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.select" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `options`<span style="color: red">\*</span> | _array_ | Опции, из которых нужно выбирать. ||
|| `options[]` | _object_ | Параметры опции. ||
|| `options[].label`<span style="color: red">\*</span> | _string_ | Название опции, которое будет отображаться в списке. ||
|| `options[].value`<span style="color: red">\*</span> | _any_ | Значение, которое будет записано в данные в свойстве `data`. ||
|| `placeholder` | _string_ | Текст, который будет отображаться, пока не выбран ни один из предложенных вариантов. ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
