# view.link-group

{% include [deprecate](../../_includes/deprecate.md) %}

Объединяет ссылки в группы.

Самую важную ссылку из группы можно визуально выделить рамкой: для этой ссылки в свойстве `theme` установите значение `primary`.

В отличие от [view.group](view.group.md) объединяет только ссылки.

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/l6Y5VpjQ3vvKhM)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "view.link-group" | Задает тип компонента. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `links`<span style="color: red">\*</span> | _array_ | Массив ссылок, составляющих группу. ||
|| `links[]` | _object_ | Параметры ссылки. ||
|| `links[].content`<span style="color: red">\*</span> | _string_ | Текст, которым отображается ссылка для исполнителя. Изначально текст отображается синим и подчеркнутым, а после перехода по ссылке становится фиолетовым. ||
|| `links[].theme` | _string_ | Определяет внешний вид ссылки. Если указать `"theme": "primary"`, то будет кнопка, иначе — текстовая ссылка. ||
|| `links[].url`<span style="color: red">\*</span> | _string_ | Адрес ссылки. При использовании [helper.search-query](helper.search-query.md) подставляет ссылку с поисковым запросом. ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
