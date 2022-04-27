# layout.side-by-side

Позволяет расставить элементы интерфейса так, чтобы сравнивать их между собой и скрывать лишние. Например, можно сравнить несколько фото.

Под сравниваемыми элементами можно добавить кнопки выбора или поле для ввода комментария.

[Посмотреть пример в песочнице](https://clck.ru/TQwkd).

Отличия от [layout.compare](layout.compare.md):

- Есть кнопки, позволяющие скрывать элементы. Удобно, если надо сравнить сразу 5 фотографий и тяжело сделать выбор между какими-то двумя.
- Можно настроить только общие элементы управления. Отдельные кнопки под каждым сравниваемым элементом добавить нельзя.

## Свойства компонента {#properties}

| Название                                     | Тип                                                                                    | Описание                                                                                                                                                                                                                                  |
| -------------------------------------------- | -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>     | "layout.side-by-side"                                                                  | <p>Задает тип компонента.</p>                                                                                                                                                                                                             |
| `controls`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>Компоненты, которые позволят пользователю совершить требуемые от него действия.</p><p>Например: <a href="field.checkbox-group.md">field.checkbox-group</a> или <a href="field.button-radio-group.md">field.button-radio-group</a>.</p> |
| `items`<span style="color: red">\*</span>    | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>Массив блоков информации.</p>                                                                                                                                                                                                          |
| `items[]`                                    | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>Компонент вывода или ввода информации. Например — <a href="view.image.md">view.image</a>.</p>                                                                                                                                          |
| `minItemWidth`                               | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>Минимальная ширина блока информации, не менее 400 пикселей.</p>                                                                                                                                                                        |
| `validation`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>                                                                                                                                                                                  |
