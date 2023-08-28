# Entries2ObjectHelperV1
`toloka.client.project.template_builder.helpers.Entries2ObjectHelperV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/helpers.py#L42)

```python
Entries2ObjectHelperV1(
    self,
    entries: Optional[Union[BaseComponent, List[Union[BaseComponent, Entry]]]] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

Creates an object from an array of key-value pairs.


For example,
`[ {"key":"foo", "value":"hello"}, {"key":"bar","value":"world"} ]`
is converted to `{ "foo": "hello", "bar": "world" }`.

For more information, see [helper.entries2object](https://toloka.ai/docs/template-builder/reference/helper.entries2object).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`entries`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Entry](toloka.client.project.template_builder.helpers.Entries2ObjectHelperV1.Entry.md)\]\]\]\]**|<p>A source array of key-value pairs.</p>
