# view.text

{% include [deprecate](../../_includes/deprecate.md) %}

Блок для отображения текста.

Если вам нужен отформатированный текст, используйте компонент [view.markdown](view.markdown.md).

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "view.text" | Задает тип компонента. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `content` | _string_ | Текст, отображаемый в блоке. Для вставки переноса строки используйте `\n`. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `rtl` | _object_ | Тексты на арабском, иврите и некоторых других языках принято писать слева направо. Используйте это свойство, чтобы задать правильный режим отображения для компонента.

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/UExGq8IQ3tz4Yo)

[Подробнее про RTL-языки](https://www.w3.org/International/questions/qa-scripts).
||
|| `rtl.mode` | _string_ | Режим отображения:

- `ltr` — слева направо;
- `rtl` — справа налево.

Выбранное значение подставится в атрибут `dir` в HTML-коде компонента. [Подробнее про свойство dir](https://www.w3.org/International/questions/qa-html-dir). ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
