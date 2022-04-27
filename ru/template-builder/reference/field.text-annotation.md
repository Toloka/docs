# field.text-annotation

Компонент для сегментации текста.

Позволяет выбрать несколько слов, отдельные слова или буквы в тексте и разметить их нужным значением. Можно создать несколько категорий и разметить по ним части текста, например, разметить все существительные и прилагательные.

[Посмотреть пример в песочнице](https://clck.ru/TaBDD).

С помощью плагина [plugin.field.text-annotation.hotkeys](plugin.field.text-annotation.hotkeys.md) можно задавать горячие клавиши для выбора категорий.

## Свойства компонента {#properties}

| Название                                           | Тип                                                                                    | Описание                                                                                                                                              |
| -------------------------------------------------- | -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>           | "field.text-annotation"                                                                | <p>Задает тип компонента.</p>                                                                                                                         |
| `data`<span style="color: red">\*</span>           | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Данные, значения которых будут обработаны или изменены.</p>                                                                                        |
| `label`                                            | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                                                                                                                       |
| `adjust`                                           | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Если для свойства указано значение `words`, в тексте можно выбирать только слова. Без использования свойства можно выбрать любую часть строки.</p> |
| `content`<span style="color: red">\*</span>        | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст, в котором нужно выбрать часть строки.</p>                                                                                                   |
| `disabled`                                         | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Свойство блокирует компонент. Если указать значение `true`, компонент будет недоступен исполнителю. Значение по умолчанию — `false`.</p>           |
| `hint`                                             | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                                                                                                               |
| `labels`<span style="color: red">\*</span>         | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>Массив с категориями, по которым исполнитель будет распределять части текста.</p>                                                                  |
| `labels[]`                                         | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a>       | <p>Категория.</p>                                                                                                                                     |
| `labels[].label`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>В свойстве `label` укажите название категории.</p>                                                                                                 |
| `labels[].value`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>В свойстве `value` укажите значение категории.</p>                                                                                                 |
| `validation`                                       | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>                                                                                              |
