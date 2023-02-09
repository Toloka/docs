# helper.search-query

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент создания строки со ссылкой поискового запроса.

Список доступных поисковых систем указан в свойстве `engine`.

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/005Ff3Ul3xDuXL)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "helper.search-query" | Задает тип компонента. ||
|| `engine` | _string_ или _object_ или _object_ или _object_ | Поисковые системы. Для указания поисковой системы используйте соответствующее ей значение:

- `yandex` — https://yandex.ru
- `google` — https://www.google.ru
- `bing` — https://www.bing.com
- `mail.ru` — https://go.mail.ru
- `wikipedia` — https://ru.wikipedia.org
- `yandex/collections` — https://yandex.ru/collections
- `yandex/video` — https://yandex.ru/video
- `yandex/images` — https://yandex.ru/images
- `google/images` — https://google.ru/images
- `yandex/news` — https://news.yandex.ru
- `google/news` — https://news.google.com
  ||
  || `query`<span style="color: red">\*</span> | _string_ | Поисковый запрос. ||
  |#
