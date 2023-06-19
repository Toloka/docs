# NotConditionV1
`toloka.client.project.template_builder.conditions.NotConditionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/conditions.py#L156)

```python
NotConditionV1(
    self,
    condition: Optional[BaseComponent] = None,
    *,
    hint: Optional[Any] = None,
    version: Optional[str] = '1.0.0'
)
```

Inverts a condition.


For more information, see [condition.not](https://toloka.ai/docs/template-builder/reference/condition.not).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`condition`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>The condition to invert.</p>
`hint`|**Optional\[Any\]**|<p>A hint that is shown if the condition is not met.</p>
