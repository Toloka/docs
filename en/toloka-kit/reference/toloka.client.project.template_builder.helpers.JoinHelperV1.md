# JoinHelperV1
`toloka.client.project.template_builder.helpers.JoinHelperV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/helpers.py#L87)

```python
JoinHelperV1(
    self,
    items: Optional[Union[BaseComponent, List[Union[BaseComponent, str]]]] = None,
    by: Optional[Any] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

Joins strings into a single string.


For more information, see [helper.join](https://toloka.ai/docs/template-builder/reference/helper.join).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]\]\]**|<p>A list of strings to join.</p>
`by`|**Optional\[Any\]**|<p>A delimiter. You can use any number of characters in the delimiter.</p>
