# FloatSpec
`toloka.client.project.field_spec.FloatSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/field_spec.py#L98)

```python
FloatSpec(
    self,
    *,
    required: Optional[bool] = True,
    hidden: Optional[bool] = False,
    min_value: Optional[float] = None,
    max_value: Optional[float] = None
)
```

A floating-point number field specification.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`required`|**Optional\[bool\]**|<p>Whether a field is required. </p><p>Default value: `True`.</p>
`hidden`|**Optional\[bool\]**|<p>Whether to hide an input field from Tolokers. Output fields can&#x27;t be hidden. </p><p>Default value: `False`.</p>
`min_value`|**Optional\[float\]**|<p>The minimum value.</p>
`max_value`|**Optional\[float\]**|<p>The maximum value.</p>
