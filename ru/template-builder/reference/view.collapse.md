# view.collapse

Разворачивающийся блок.

Позволяет размещать «под кат» содержимое, которое не обязательно показывать изначально или которое занимает большое пространство.

Заголовок блока виден всегда.

Если свойству `defaultOpened` установить значение `true`, блок сразу будет развернут, при этом останется возможность его свернуть.

## Свойства компонента {#properties}

| Название                                    | Тип                                                                                    | Описание                                                                                                        |
| ------------------------------------------- | -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>    | "view.collapse"                                                                        | <p>Задает тип компонента.</p>                                                                                   |
| `label`<span style="color: red">\*</span>   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Заголовок блока.</p>                                                                                         |
| `content`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>Содержимое, скрываемое в блоке.</p>                                                                          |
| `defaultOpened`                             | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Если `true`, блок будет сразу показан в развернутом виде. Значение по умолчанию: `false` (блок свернут).</p> |
| `hint`                                      | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                                                                         |
| `validation`                                | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>                                                        |
