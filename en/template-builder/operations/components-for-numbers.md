# Number input field

To add a number input field, use the [field.number](../reference/field.number.md) component.


## Integer validation {#number-integer-only}

By default, this field can contain decimal numbers. To enter integers, use validation:

```
"validation": {
  "type": "condition.schema",
  "schema": {
    "type": "integer"
  },
  "hint": "Enter an integer"
}
```


[View example in the sandbox](https://clck.ru/U3CAu).


## Prohibit negative numbers {#number-positive-only}

By default, you can enter both positive and negative numbers in this field. To prohibit negative numbers, use the `minimum` property:

```
"minimum": 0
```


[View example in the sandbox](https://clck.ru/U7NNo).


[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
