# ArrayBooleanSpec
`toloka.client.project.field_spec.ArrayBooleanSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/project/field_spec.py#L143)

```python
ArrayBooleanSpec(
    self,
    *,
    required: Optional[bool] = True,
    hidden: Optional[bool] = False,
    allowed_values: Optional[List[bool]] = None,
    min_size: Optional[int] = None,
    max_size: Optional[int] = None
)
```

A boolean array field specification.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`required`|**Optional\[bool\]**|<p>Whether a field is required. </p><p>Default value: `True`.</p>
`hidden`|**Optional\[bool\]**|<p>Whether to hide an input field from Tolokers. Output fields can&#x27;t be hidden. </p><p>Default value: `False`.</p>
`allowed_values`|**Optional\[List\[bool\]\]**|<p>A list of allowed values.</p>
`min_size`|**Optional\[int\]**|<p>The minimum number of elements in the array.</p>
`max_size`|**Optional\[int\]**|<p>The maximum number of elements in the array.</p>
