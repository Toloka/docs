# view.link-group

Объединяет ссылки в группы.

Самую важную ссылку из группы можно визуально выделить рамкой: для этой ссылки в свойстве `theme` установите значение `primary`.

В отличие от [view.group](view.group.md) объединяет только ссылки.

[Посмотреть пример в песочнице](https://ya.cc/t/YoOueC4dHZHJh).

## Свойства компонента {#properties}

| Название                                            | Тип                                                                                    | Описание                                                                                                                                                          |
| --------------------------------------------------- | -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>            | "view.link-group"                                                                      | <p>Задает тип компонента.</p>                                                                                                                                     |
| `label`                                             | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                                                                                                                                   |
| `hint`                                              | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                                                                                                                           |
| `links`<span style="color: red">\*</span>           | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>Массив ссылок, составляющих группу.</p>                                                                                                                        |
| `links[]`                                           | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a>       | <p>Параметры ссылки.</p>                                                                                                                                          |
| `links[].content`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст, которым отображается ссылка для пользователя. Изначально текст отображается синим и подчеркнутым, а после перехода по ссылке становится фиолетовым.</p> |
| `links[].theme`                                     | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Определяет внешний вид ссылки. Если указать `"theme": "primary"`, то будет кнопка, иначе — текстовая ссылка.</p>                                               |
| `links[].url`<span style="color: red">\*</span>     | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Адрес ссылки. При использовании <a href="helper.search-query.md">helper.search-query</a> подставляет ссылку с поисковым запросом.</p>                          |
| `validation`                                        | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>                                                                                                          |
