# field.quiz

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент викторины, который учитывает только значения, на которые были даны первые ответы.

Возвращает объект key value с любым типом данных в качестве значения.

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.quiz" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `instruction` | _string_ | – ||
|| `options`<span style="color: red">\*</span> | _array_ | Массив вопросов. ||
|| `options[]` | _object_ | – ||
|| `options[].border` | _boolean_ | – ||
|| `options[].disabled` | _boolean_ | – ||
|| `options[].key`<span style="color: red">\*</span> | _string_ | – ||
|| `options[].label` | _string_ | Заголовок вопроса. Поддерживает markdown. ||
|| `options[].options`<span style="color: red">\*</span> | _array_ | Массив ответов. ||
|| `options[].options[]` | _object_ | – ||
|| `options[].options[].correct` | _boolean_ | Это правильное значение? ||
|| `options[].options[].hint` | _string_ | Текст который появляется, когда данный ответ выбран. Поддерживает markdown. ||
|| `options[].options[].label`<span style="color: red">\*</span> | _string_ | Текст ответа. Поддерживает markdown. ||
|| `options[].options[].value`<span style="color: red">\*</span> | _any_ | Возвращаемое значние. ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
