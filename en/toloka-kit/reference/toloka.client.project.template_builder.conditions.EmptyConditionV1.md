# EmptyConditionV1
`toloka.client.project.template_builder.conditions.EmptyConditionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/conditions.py#L117)

```python
EmptyConditionV1(
    self,
    data: Optional[Any] = None,
    *,
    hint: Optional[Any] = None,
    version: Optional[str] = '1.0.0'
)
```

Checks that data is empty or undefined.


For more information, see [condition.empty](https://toloka.ai/docs/template-builder/reference/condition.empty).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[Any\]**|<p>Data to check. If not specified, data of the parent component is checked.</p>
`hint`|**Optional\[Any\]**|<p>A hint that is shown if the condition is not met.</p>
