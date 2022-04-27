# field.select

Кнопка для выбора из выпадающего списка. Используйте, когда список длинный, а выбрать нужно один вариант.

Для коротких списков (2-4 пункта) лучше подходят [field.radio-group](field.radio-group.md) или [field.button-radio-group](field.button-radio-group.md), в которых все варианты ответов видны сразу.

Чтобы дать возможность выбрать несколько вариантов, используйте компонент [field.checkbox-group](field.checkbox-group.md).

## Свойства компонента {#properties}

| Название                                            | Тип                                                                                    | Описание                                                                                    |
| --------------------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>            | "field.select"                                                                         | <p>Задает тип компонента.</p>                                                               |
| `data`<span style="color: red">\*</span>            | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Данные, значения которых будут обработаны или изменены.</p>                              |
| `label`                                             | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                                                             |
| `hint`                                              | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                                                     |
| `options`<span style="color: red">\*</span>         | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>Опции, из которых нужно выбирать.</p>                                                    |
| `options[]`                                         | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a>       | <p>Параметры опции.</p>                                                                     |
| `options[].label`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Название опции, которое будет отображаться в списке.</p>                                 |
| `options[].value`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>             | <p>Значение, которое будет записано в данные в свойстве `data`.</p>                         |
| `placeholder`                                       | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст, который будет отображаться, пока не выбран ни один из предложенных вариантов.</p> |
| `validation`                                        | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>                                    |
