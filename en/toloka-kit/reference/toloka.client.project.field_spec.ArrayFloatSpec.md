# ArrayFloatSpec
`toloka.client.project.field_spec.ArrayFloatSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/field_spec.py#L179)

```python
ArrayFloatSpec(
    self,
    *,
    required: Optional[bool] = True,
    hidden: Optional[bool] = False,
    min_value: Optional[float] = None,
    max_value: Optional[float] = None,
    min_size: Optional[int] = None,
    max_size: Optional[int] = None
)
```

A floating-point array field specification.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`required`|**Optional\[bool\]**|<p>Whether a field is required. </p><p>Default value: `True`.</p>
`hidden`|**Optional\[bool\]**|<p>Whether to hide an input field from Tolokers. Output fields can&#x27;t be hidden. </p><p>Default value: `False`.</p>
`min_value`|**Optional\[float\]**|<p>The minimum value.</p>
`max_value`|**Optional\[float\]**|<p>The maximum value.</p>
`min_size`|**Optional\[int\]**|<p>The minimum number of elements in the array.</p>
`max_size`|**Optional\[int\]**|<p>The maximum number of elements in the array.</p>
