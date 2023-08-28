# SchemaConditionV1
`toloka.client.project.template_builder.conditions.SchemaConditionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/conditions.py#L230)

```python
SchemaConditionV1(
    self,
    data: Optional[Any] = None,
    schema: Optional[Dict] = None,
    *,
    hint: Optional[Any] = None,
    version: Optional[str] = '1.0.0'
)
```

Validates data using the [JSON Schema](https://json-schema.org/learn/getting-started-step-by-step.html).


For more information, see [condition.schema](https://toloka.ai/docs/template-builder/reference/condition.schema).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[Any\]**|<p>Data to be validated.</p>
`schema`|**Optional\[Dict\]**|<p>The schema for validating data.</p>
`hint`|**Optional\[Any\]**|<p>A hint that is shown if the condition is not met.</p>
