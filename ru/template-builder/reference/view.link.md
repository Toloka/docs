# view.link

Универсальный способ добавить ссылку.

Такая ссылка изменит цвет после перехода по ней.

Рекомендуем использовать этот компонент, если вам нужно вставить ссылку без дополнительного форматирования.

Если вы хотите вставить кнопку, по которой будет открываться ссылка, используйте компоненты [view.action-button](view.action-button.md) и [action.open-link](action.open-link.md). [Посмотреть пример в песочнице](https://clck.ru/QLEtD).

Чтобы вставить ссылку с поисковым запросом, используйте [helper.search-query](helper.search-query.md). [Посмотреть пример в песочнице](https://clck.ru/QLF3o).

## Свойства компонента {#properties}

| Название                                 | Тип                                                                                    | Описание                                                 |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "view.link"                                                                            | <p>Задает тип компонента.</p>                            |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                          |
| `content`                                | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст ссылки, который видит пользователь.</p>         |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                  |
| `url`<span style="color: red">\*</span>  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Адрес ссылки.</p>                                     |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p> |
