# Поле для ввода чисел

{% include [deprecate](../../_includes/deprecate.md) %}

Чтобы добавить поле для ввода числа, используйте компонент [field.number](../reference/field.number.md).


## Валидация на целое число {#number-integer-only}

По умолчанию в это поле можно вводить дробные числа. Для ввода целых чисел используйте валидацию:

```
"validation": {
  "type": "condition.schema",
  "schema": {
    "type": "integer"
  },
  "hint": "Введите целое число"
}
```

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/szui98Mc3tvrjL)

## Запретить отрицательные числа {#number-positive-only}

По умолчанию в это поле можно вводить положительные и отрицательные числа. Для запрета отрицательных чисел используйте свойство `minimum`:

```
"minimum": 0
```

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/DZ8TpX8S3tvruz)

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
