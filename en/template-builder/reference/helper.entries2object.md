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

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/wf2xSzVO3twkui)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "helper.entries2object" | Set component type ||
|| `entries` | _array_ | Source array of key-value pairs. ||
|| `entries[]` | _object_ | Object parameters. ||
|| `entries[].key`<span style="color: red">\*</span> | _string_ | Key. ||
|| `entries[].value`<span style="color: red">\*</span> | _any_ | Value. ||
|#
