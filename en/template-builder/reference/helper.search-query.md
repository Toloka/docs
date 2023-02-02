# helper.search-query

Component for creating a string with a search query reference.

The list of available search engines is specified in the `engine` property.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/W5KExwg_3vwB57)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "helper.search-query" | Set component type ||
|| `engine` | _string_ or _object_ or _object_ or _object_ | Search engine. Use the corresponding value to specify the search engine:

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
  || `query`<span style="color: red">\*</span> | _string_ | Search query. ||
  |#
