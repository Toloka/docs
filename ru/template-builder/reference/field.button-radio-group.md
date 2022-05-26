# field.button-radio-group

Добавляет кнопки для выбора варианта ответа. Пригодится, если у вас несколько вариантов. Можно добавить только одну кнопку, но это легче сделать с [field.button-radio](field.button-radio.md).

Размер кнопки зависит от длины надписи.

[Посмотреть пример в песочнице](https://clck.ru/T6Ugh).

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.button-radio-group" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `disabled` | _boolean_ | Свойство запрещает нажимать кнопки. Если значение — `true`, пользователю будет недоступно нажатие. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `options`<span style="color: red">\*</span> | _array_ | Массив кнопок. ||
|| `options[]` | _object_ | Кнопка. ||
|| `options[].hint` | _string_ | Дополнительная информация. ||
|| `options[].label`<span style="color: red">\*</span> | _string_ | Текст на кнопке. ||
|| `options[].value`<span style="color: red">\*</span> | _any_ | Возвращаемое значение. ||
|| `rtl` | _object_ | Тексты на арабском, иврите и некоторых других языках принято писать слева направо. Используйте это свойство, чтобы задать правильный режим отображения для компонента.

[Посмотреть пример в песочнице](https://clck.ru/amHBJ).

[Подробнее про RTL-языки](https://www.w3.org/International/questions/qa-scripts).
||
|| `rtl.mode` | _string_ | Режим отображения:

- `ltr` — слева направо;
- `rtl` — справа налево.

Выбранное значение подставится в атрибут `dir` в HTML-коде компонента. [Подробнее про свойство dir](https://www.w3.org/International/questions/qa-html-dir). ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
