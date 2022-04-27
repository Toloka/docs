# action.notify

Компонент создает сообщение в левом нижнем углу экрана.

Можно задать: длительность активности сообщения, длительность задержки появления и цвет фона.

## Свойства компонента {#properties}

| Название                                            | Тип                                                                              | Описание                                                                                                                                                                                                                        |
| --------------------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>            | "action.notify"                                                                  | <p>Задает тип компонента.</p>                                                                                                                                                                                                   |
| `payload`<span style="color: red">\*</span>         | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a> | <p>Параметры для сообщения.</p>                                                                                                                                                                                                 |
| `payload.content`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Текст сообщения.</p>                                                                                                                                                                                                         |
| `payload.delay`                                     | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a> | <p>Длительность задержки (в миллисекундах) до появления сообщения.</p>                                                                                                                                                          |
| `payload.duration`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a> | <p>Длительность активности сообщения (в миллисекундах), которое включает длительность задержки его показа.</p><p>Например, если `duration` — 1000, а `delay` — 400, то длительность показа сообщения будет 600 миллисекунд.</p> |
| `payload.theme`<span style="color: red">\*</span>   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Цвет фона сообщения: </p><ul><li>`info` — синий.</li><li>`success` — зеленый.</li><li>`warning` — желтый.</li><li>`danger` — красный.</li></ul>                                                                              |
