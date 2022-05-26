# helper.concat-arrays

Merging multiple arrays into a single array.

For example, let's say you have multiple arrays:

```json
([1, 2, 3], [4, 5, 6], [7, 8, 9])
```

Their elements can be combined into a single array to show simultaneously:

```json
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

[View example in the sandbox](https://clck.ru/Rnruy).

## Component properties {#properties}

| Name                                     | Type                   | Description               |
| ---------------------------------------- | ---------------------- | ------------------------- |
| `type`<span style="color: red">\*</span> | "helper.concat-arrays" | <p>Set component type</p> |
| `items`                                  | _array_                | <p>Arrays to combine.</p> |
| `items[]`                                | _any_                  | <p>Array element.</p>     |
