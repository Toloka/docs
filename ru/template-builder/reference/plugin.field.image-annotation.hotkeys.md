# plugin.field.image-annotation.hotkeys

Позволяет задавать горячие клавиши для компонента [field.image-annotation](field.image-annotation.md).

Можно задать горячие клавиши для выбора типов областей, выбора режимов разметки и подтверждения или отмены создания области. Добавить их можно на стрелки вверх и вниз (`up`,`down`), цифры и латинские буквы.

[Посмотреть пример в песочнице](https://clck.ru/TSC6f).

## Свойства компонента {#properties}

| Название                                 | Тип                                                                              | Описание                                                                                                                                                          |
| ---------------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "plugin.field.image-annotation.hotkeys"                                          | <p>Задает тип компонента.</p>                                                                                                                                     |
| `cancel`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Горячая клавиша для отмены создания области.</p>                                                                                                               |
| `confirm`                                | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Горячая клавиша для подтверждения создания области.</p>                                                                                                        |
| `labels`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>   | <p>Горячие клавиши для выбора типов областей. Добавляются на кнопки в порядке их отображения, если вы добавили возможность выделить несколько типов областей.</p> |
| `labels[]`                               | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Горячая клавиша.</p>                                                                                                                                           |
| `modes`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a> | <p>Горячие клавиши для выбора режимов разметки.</p>                                                                                                               |
| `modes.point`                            | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Горячая клавиша для режима разметки точками.</p>                                                                                                               |
| `modes.polygon`                          | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Горячая клавиша для режима разметки многоугольниками.</p>                                                                                                      |
| `modes.rectangle`                        | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Горячая клавиша для режима разметки прямоугольниками.</p>                                                                                                      |
| `modes.select`                           | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Горячая клавиша для режима выбора фигур и точек.</p>                                                                                                           |
