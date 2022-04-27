# condition.sub-array

Проверяет, что массив в `data` является подмассивом для `parent`.

[Посмотреть пример в песочнице](https://clck.ru/T9a4k).

## Свойства компонента {#properties}

| Название                                 | Тип                                                                              | Описание                                                          |
| ---------------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "condition.sub-array"                                                            | <p>Задает тип компонента.</p>                                     |
| `data`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>       | <p>Подмассив, наличие которого проверяется в `parent`</p>         |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Сообщение об ошибке валидации, которое увидит пользователь</p> |
| `parent`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>       | <p>Массив, в котором осуществляется поиск `data`</p>              |
