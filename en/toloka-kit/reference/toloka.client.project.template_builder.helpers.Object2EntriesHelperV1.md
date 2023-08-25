# Object2EntriesHelperV1
`toloka.client.project.template_builder.helpers.Object2EntriesHelperV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/helpers.py#L102)

```python
Object2EntriesHelperV1(
    self,
    data: Optional[Any] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

Creates an array of key-value pairs from an object.


For example,
`{ "foo": "hello", "bar": "world" }` is converted to
`[ {"key":"foo", "value":"hello"}, {"key":"bar","value":"world"} ]`.

For more information, see [helper.object2entries](https://toloka.ai/docs/template-builder/reference/helper.object2entries).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[Any\]**|<p>An object to convert.</p>
