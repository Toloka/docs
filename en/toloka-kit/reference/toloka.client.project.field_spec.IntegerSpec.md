# IntegerSpec
`toloka.client.project.field_spec.IntegerSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/project/field_spec.py#L86)

```python
IntegerSpec(
    self,
    *,
    required: Optional[bool] = True,
    hidden: Optional[bool] = False,
    min_value: Optional[int] = None,
    max_value: Optional[int] = None,
    allowed_values: Optional[List[int]] = None
)
```

An integer field specification

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`required`|**Optional\[bool\]**|<p>Whether the object or input field is required.</p>
`hidden`|**Optional\[bool\]**|<p>Whether to hide the input field from Tolokers.</p>
`min_value`|**Optional\[int\]**|<p>Minimum value of the number</p>
`max_value`|**Optional\[int\]**|<p>Maximum value of the number</p>
`allowed_values`|**Optional\[List\[int\]\]**|<p>Allowed values</p>
