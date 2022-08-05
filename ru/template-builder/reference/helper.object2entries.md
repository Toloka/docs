# helper.object2entries

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

[![](../_images/buttons/view-example.svg)](https://clck.ru/QRgqs)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "helper.object2entries" | Задает тип компонента. ||
|| `data` | _any_ | Объект, который будет преобразован. ||
|#
