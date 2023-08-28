# TransformHelperV1
`toloka.client.project.template_builder.helpers.TransformHelperV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/helpers.py#L211)

```python
TransformHelperV1(
    self,
    into: Optional[Any] = None,
    items: Optional[Union[BaseComponent, List[Any]]] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

Creates a new array by transforming elements of another array.


For example, you can create an array of `view.image` components from an array of links to images.

For more information, see [helper.transform](https://toloka.ai/docs/template-builder/reference/helper.transform).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`into`|**Optional\[Any\]**|<p>The template of an element of the new array. To insert values from the source array use the [LocalData](toloka.client.project.template_builder.data.LocalData.md) component with the data `path` set to `item`.</p>
`items`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Any\]\]\]**|<p>The source array.</p>
