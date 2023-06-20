# SameDomainConditionV1
`toloka.client.project.template_builder.conditions.SameDomainConditionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/conditions.py#L212)

```python
SameDomainConditionV1(
    self,
    data: Optional[Any] = None,
    original: Optional[Any] = None,
    *,
    hint: Optional[Any] = None,
    version: Optional[str] = '1.0.0'
)
```

Checks that domains in two URLs are the same.


For more information, see [condition.same-domain](https://toloka.ai/docs/template-builder/reference/condition.same-domain).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[Any\]**|<p>The first URL. If it is not specified, then the value returned by the parent component is used.</p>
`original`|**Optional\[Any\]**|<p>The second URL.</p>
`hint`|**Optional\[Any\]**|<p>A hint that is shown if the condition is not met.</p>
