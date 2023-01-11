# helper.object2entries

{% include [deprecate](../../_includes/deprecate.md) %}

Создание массива пар вида ключ-значение из заданного объекта.

Например, у вас задан объект вида:

```json
{
  "foo": "hello",
  "bar": "world"
}
```

Он будет преобразован в массив, объекты которого составят пары из данных исходного объекта и их обозначений:

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

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/67HCni-d3twj8n)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "helper.object2entries" | Задает тип компонента. ||
|| `data` | _any_ | Объект, который будет преобразован. ||
|#
