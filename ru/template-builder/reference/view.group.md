# view.group

Объединяет любые компоненты в визуальные группы — блоки с рамкой.

[Посмотреть пример в песочнице](https://clck.ru/QRZF6).

## Свойства компонента {#properties}

| Название                                 | Тип                                                                                    | Описание                                                                           |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "view.group"                                                                           | <p>Задает тип компонента.</p>                                                      |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Заголовок группы.</p>                                                           |
| `content`                                | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>Содержимое блока-группы.</p>                                                    |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Пояснение к заголовку группы. Для вставки переноса строки используйте `\n`.</p> |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>                           |
