# helper.object2entries

Creating an array of key-value pairs from the specified object.

For example, let's say you have an object that looks like this:

```json
{
  "foo": "hello",
  "bar": "world"
}
```

It will be converted to an array whose objects will pair data from the source object and their designations:

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

[View example in the sandbox](https://clck.ru/RnsKc).

## Component properties {#properties}

| Name                                     | Type                                                                       | Description                   |
| ---------------------------------------- | -------------------------------------------------------------------------- | ----------------------------- |
| `type`<span style="color: red">\*</span> | "helper.object2entries"                                                    | <p>Set component type</p>     |
| `data`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a> | <p>The object to convert.</p> |
