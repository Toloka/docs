# field.text-annotation

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент для сегментации текста.

Позволяет выбрать несколько слов, отдельные слова или буквы в тексте и разметить их нужным значением. Можно создать несколько категорий и разметить по ним части текста, например, разметить все существительные и прилагательные.

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/bTmVb7H-3twmCg)

С помощью плагина [plugin.field.text-annotation.hotkeys](plugin.field.text-annotation.hotkeys.md) можно задавать горячие клавиши для выбора категорий.

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.text-annotation" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `adjust` | _string_ | Если для свойства указано значение `words`, в тексте можно выбирать только слова. Без использования свойства можно выбрать любую часть строки. ||
|| `content`<span style="color: red">\*</span> | _string_ | Текст, в котором нужно выбрать часть строки. ||
|| `disabled` | _boolean_ | Свойство блокирует компонент. Если указать значение `true`, компонент будет недоступен исполнителю. Значение по умолчанию — `false`. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `labels`<span style="color: red">\*</span> | _array_ | Массив с категориями, по которым исполнитель будет распределять части текста. ||
|| `labels[]` | _object_ | Категория. ||
|| `labels[].label`<span style="color: red">\*</span> | _string_ | В свойстве `label` укажите название категории. ||
|| `labels[].value`<span style="color: red">\*</span> | _string_ | В свойстве `value` укажите значение категории. ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
