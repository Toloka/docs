# view.link

{% include [deprecate](../../_includes/deprecate.md) %}

Универсальный способ добавить ссылку.

Такая ссылка изменит цвет после перехода по ней.

Рекомендуем использовать этот компонент, если вам нужно вставить ссылку без дополнительного форматирования.

Если вы хотите вставить кнопку, по которой будет открываться ссылка, используйте компоненты [view.action-button](view.action-button.md) и [action.open-link](action.open-link.md).

[![](../_images/buttons/view-example.svg)](https://clck.ru/QLEtD)

Чтобы вставить ссылку с поисковым запросом, используйте [helper.search-query](helper.search-query.md). [Посмотреть пример в песочнице](https://clck.ru/QLF3o).

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "view.link" | Задает тип компонента. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `content` | _string_ | Текст ссылки, который видит исполнитель. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `url`<span style="color: red">\*</span> | _string_ | Адрес ссылки. ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
