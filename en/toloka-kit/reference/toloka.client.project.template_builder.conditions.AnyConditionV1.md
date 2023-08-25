# AnyConditionV1
`toloka.client.project.template_builder.conditions.AnyConditionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/conditions.py#L74)

```python
AnyConditionV1(
    self,
    conditions: Optional[Union[BaseComponent, List[BaseComponent]]] = None,
    *,
    hint: Optional[Any] = None,
    version: Optional[str] = '1.0.0'
)
```

Checks that at least one nested condition is met.


For more information, see [condition.any](https://toloka.ai/docs/template-builder/reference/condition.any).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`conditions`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]\]\]**|<p>A list of conditions.</p>
`hint`|**Optional\[Any\]**|<p>A hint that is shown if the condition is not met.</p>
