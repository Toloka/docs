# field.text

{% include [deprecate](../../_includes/deprecate.md) %}

Поле для ввода короткого текста, не больше одной строки. Чтобы добавить поле, где можно ввести много строк текста, используйте [field.textarea](field.textarea.md).

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/xJlqYE033twmeg)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.text" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `disabled` | _boolean_ | Если `true`, редактирование недоступно. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `placeholder` | _string_ | Полупрозрачная надпись, отображающаяся в пустом поле. ||
|| `requiredMark` | _boolean_ | Показывать "\*" рядом с надписью над компонентом ||
|| `rtl` | _object_ | Тексты на арабском, иврите и некоторых других языках принято писать слева направо. Используйте это свойство, чтобы задать правильный режим отображения для компонента.

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/UExGq8IQ3tz4Yo).

[Подробнее про RTL-языки](https://www.w3.org/International/questions/qa-scripts).
||
|| `rtl.mode` | _string_ | Режим отображения:

- `ltr` — слева направо;
- `rtl` — справа налево.

Выбранное значение подставится в атрибут `dir` в HTML-коде компонента. [Подробнее про свойство dir](https://www.w3.org/International/questions/qa-html-dir). ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
