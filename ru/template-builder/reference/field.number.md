# field.number

Компонент, позволяющий ввести число.

В поле можно вводить только цифры и разделители дробной части числа. Пользователь сможет использовать в качестве разделителя и точку, и запятую, однако в выходных данных всегда будет точка.

В процессе ввода числа разделитель автоматически меняется на указанный в региональных настройках. Для России разделитель — запятая.

Вы также можете настроить валидацию, например, запретить отрицательные или дробные числа. [Подробнее](../operations/components-for-numbers.dita).

## Свойства компонента {#properties}

| Название                                 | Тип                                                                                    | Описание                                                       |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "field.number"                                                                         | <p>Задает тип компонента.</p>                                  |
| `data`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Данные, значения которых будут обработаны или изменены.</p> |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                                |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                        |
| `maximum`                                | <a class="xref popup-link" href="../concepts/types.dita#types/integer">integer</a>     | <p>Максимальное число, которое можно ввести.</p>               |
| `minimum`                                | <a class="xref popup-link" href="../concepts/types.dita#types/integer">integer</a>     | <p>Минимальное число, которое можно ввести.</p>                |
| `placeholder`                            | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Полупрозрачная надпись, отображающаяся в пустом поле.</p>   |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>       |
