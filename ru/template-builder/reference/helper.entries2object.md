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

[![](../_images/buttons/view-example.svg)](https://clck.ru/QRnzQ)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "helper.entries2object" | Задает тип компонента. ||
|| `entries` | _array_ | Исходный массив пар вида ключ-значение. ||
|| `entries[]` | _object_ | Параметры объекта. ||
|| `entries[].key`<span style="color: red">\*</span> | _string_ | Ключ. ||
|| `entries[].value`<span style="color: red">\*</span> | _any_ | Значение. ||
|#
