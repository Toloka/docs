# ReplaceHelperV1
`toloka.client.project.template_builder.helpers.ReplaceHelperV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/helpers.py#L117)

```python
ReplaceHelperV1(
    self,
    data: Optional[Any] = None,
    find: Optional[Union[BaseComponent, str]] = None,
    replace: Optional[Union[BaseComponent, str]] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

Replaces a substring in a string.


For more information, see [helper.replace](https://toloka.ai/docs/template-builder/reference/helper.replace).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[Any\]**|<p>An input string.</p>
`find`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>A substring to look for.</p>
`replace`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>A substring to replace with.</p>
