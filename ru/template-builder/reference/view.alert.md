# view.alert

Компонент создает цветной блок для выделения важной информации.

Внутрь можно поместить не только обычный текст, но и другие визуальные компоненты.

[Посмотреть пример в песочнице](https://clck.ru/RTzHz).

## Свойства компонента {#properties}

| Название                                 | Тип                                                                                    | Описание                                                                                                                                                                  |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "view.alert"                                                                           | <p>Задает тип компонента.</p>                                                                                                                                             |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                                                                                                                                           |
| `content`                                | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>Содержимое блока с важной информацией.</p>                                                                                                                             |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                                                                                                                                   |
| `theme`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Определяет расцветку блока:</p><ul><li>`info` (по умолчанию) — голубая;</li><li>`success` — зеленая;</li><li>`warning` — желтая;</li><li>`danger` — красная.</li></ul> |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>                                                                                                                  |
