# SwitchHelperV1
`toloka.client.project.template_builder.helpers.SwitchHelperV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/helpers.py#L162)

```python
SwitchHelperV1(
    self,
    cases: Optional[Union[BaseComponent, List[Union[BaseComponent, Case]]]] = None,
    default: Optional[Any] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

Chooses one variant from multiple cases.


For more information, see [helper.switch](https://toloka.ai/docs/template-builder/reference/helper.switch).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`cases`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Case](toloka.client.project.template_builder.helpers.SwitchHelperV1.Case.md)\]\]\]\]**|<p>A list of cases. A case consists of a condition and a resulting component.</p>
`default`|**Optional\[Any\]**|<p>A component that is returned if none of the conditions is `True`.</p>
