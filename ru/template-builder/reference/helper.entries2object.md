# helper.entries2object

{% include [deprecate](../../_includes/deprecate.md) %}

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

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/BbI6p-3Z3twkmP)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "helper.entries2object" | Задает тип компонента. ||
|| `entries` | _array_ | Исходный массив пар вида ключ-значение. ||
|| `entries[]` | _object_ | Параметры объекта. ||
|| `entries[].key`<span style="color: red">\*</span> | _string_ | Ключ. ||
|| `entries[].value`<span style="color: red">\*</span> | _any_ | Значение. ||
|#
