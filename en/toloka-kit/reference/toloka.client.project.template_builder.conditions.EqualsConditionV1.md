# EqualsConditionV1
`toloka.client.project.template_builder.conditions.EqualsConditionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/conditions.py#L130)

```python
EqualsConditionV1(
    self,
    to: Optional[Any] = None,
    data: Optional[Any] = None,
    *,
    hint: Optional[Any] = None,
    version: Optional[str] = '1.0.0'
)
```

Checks whether two values are equal.


For more information, see [condition.equals](https://toloka.ai/docs/template-builder/reference/condition.equals).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`to`|**Optional\[Any\]**|<p>The value to compare with.</p>
`data`|**Optional\[Any\]**|<p>The first value. If it is not specified, then the value returned by the parent component is used.</p>
`hint`|**Optional\[Any\]**|<p>A hint that is shown if the condition is not met.</p>
