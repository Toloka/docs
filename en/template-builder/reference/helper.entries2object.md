# helper.entries2object

Creating an object from a specified array of key-value pairs.

For example, let's say you have an array like this:

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

It is converted to an object whose elements consist of the values of the original array:

```json
{ "foo": "hello", "bar": "world" }
```

[View example in the sandbox](https://clck.ru/asSbu).

## Component properties {#properties}

| Name                                                | Type                    | Description                             |
| --------------------------------------------------- | ----------------------- | --------------------------------------- |
| `type`<span style="color: red">\*</span>            | "helper.entries2object" | <p>Set component type</p>               |
| `entries`                                           | _array_                 | <p>Source array of key-value pairs.</p> |
| `entries[]`                                         | _object_                | <p>Object parameters.</p>               |
| `entries[].key`<span style="color: red">\*</span>   | _string_                | <p>Key.</p>                             |
| `entries[].value`<span style="color: red">\*</span> | _any_                   | <p>Value.</p>                           |
