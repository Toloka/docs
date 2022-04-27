# field.email

Создает поле для ввода адреса электронной почты.

Проверяет, что в тексте есть символ `@`. Другие условия [настройте самостоятельно](../best-practices/conditions.dita).

[Посмотреть пример в песочнице](https://clck.ru/RYXrb).

## Свойства компонента {#properties}

| Название                                 | Тип                                                                                    | Описание                                                           |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "field.email"                                                                          | <p>Задает тип компонента.</p>                                      |
| `data`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Данные, значения которых будут обработаны или изменены.</p>     |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                                    |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                            |
| `placeholder`                            | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Полупрозрачная надпись, которая отображается в пустом поле.</p> |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>           |
