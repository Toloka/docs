# helper.entries2object

Создание объекта из заданного массива пар ключей и значений.

Например, у вас есть такой массив:

```json
[
  {
    "key": "foo",
    "value": "hello"
  },
  {
    "key": "bar",
    "value": "world"
  }
]
```

Он преобразуется в объект, элементы которого состоят из значений исходного массива:

```json
{ "foo": "hello", "bar": "world" }
```

[Посмотреть пример в песочнице](https://clck.ru/QRnzQ).

## Свойства компонента {#properties}

| Название                                            | Тип                                                                              | Описание                                       |
| --------------------------------------------------- | -------------------------------------------------------------------------------- | ---------------------------------------------- |
| `type`<span style="color: red">\*</span>            | "helper.entries2object"                                                          | <p>Задает тип компонента.</p>                  |
| `entries`                                           | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>   | <p>Исходный массив пар вида ключ-значение.</p> |
| `entries[]`                                         | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a> | <p>Параметры объекта.</p>                      |
| `entries[].key`<span style="color: red">\*</span>   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Ключ.</p>                                   |
| `entries[].value`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>       | <p>Значение.</p>                               |
