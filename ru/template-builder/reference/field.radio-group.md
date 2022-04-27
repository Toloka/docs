# field.radio-group

Компонент, позволяющий выбрать одно из нескольких значений. Оформляется в виде группы переключателей (кружочков), располагающихся вертикально.

Если вы хотите оформление в виде обычных кнопок, используйте [field.button-radio-group](field.button-radio-group.md).

Минимальное количество кнопок — одна. Тип возвращаемых данных — любой.

## Свойства компонента {#properties}

| Название                                            | Тип                                                                                    | Описание                                                                                                  |
| --------------------------------------------------- | -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>            | "field.radio-group"                                                                    | <p>Задает тип компонента.</p>                                                                             |
| `data`<span style="color: red">\*</span>            | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Данные, значения которых будут обработаны или изменены.</p>                                            |
| `label`                                             | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                                                                           |
| `disabled`                                          | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Свойство запрещает нажимать кнопки. Если значение - `true`, пользователю будет недоступно нажатие.</p> |
| `hint`                                              | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                                                                   |
| `options`<span style="color: red">\*</span>         | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>Массив кнопок.</p>                                                                                     |
| `options[]`                                         | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a>       | <p>Кнопка.</p>                                                                                            |
| `options[].hint`                                    | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст с дополнительной информацией.</p>                                                                |
| `options[].label`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Название опции.</p>                                                                                    |
| `options[].value`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>             | <p>Возвращаемое значение.</p>                                                                             |
| `validation`                                        | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>                                                  |
