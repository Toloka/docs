# field.phone-number

Создает поле для ввода номера телефона.

Вводить можно цифры, пробел и символы `+`, `( )`, `-`. В данных останутся только цифры и символ `+` в начале. Например, если ввести номер `+7 (012) 345-67-89`, данные получат значение `+70123456789`.

[Посмотреть пример в песочнице](https://clck.ru/RYZqt).

## Свойства компонента {#properties}

| Название                                 | Тип                                                                                    | Описание                                                           |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "field.phone-number"                                                                   | <p>Задает тип компонента.</p>                                      |
| `data`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Данные, значения которых будут обработаны или изменены.</p>     |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                                    |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                            |
| `placeholder`                            | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Полупрозрачная надпись, которая отображается в пустом поле.</p> |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>           |
