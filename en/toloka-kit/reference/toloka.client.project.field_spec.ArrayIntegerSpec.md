# ArrayIntegerSpec
`toloka.client.project.field_spec.ArrayIntegerSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/field_spec.py#L167)

```python
ArrayIntegerSpec(
    self,
    *,
    required: Optional[bool] = True,
    hidden: Optional[bool] = False,
    min_value: Optional[int] = None,
    max_value: Optional[int] = None,
    allowed_values: Optional[List[int]] = None,
    min_size: Optional[int] = None,
    max_size: Optional[int] = None
)
```

An integer array field specification.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`required`|**Optional\[bool\]**|<p>Whether a field is required. </p><p>Default value: `True`.</p>
`hidden`|**Optional\[bool\]**|<p>Whether to hide an input field from Tolokers. Output fields can&#x27;t be hidden. </p><p>Default value: `False`.</p>
`min_value`|**Optional\[int\]**|<p>The minimum value.</p>
`max_value`|**Optional\[int\]**|<p>The maximum value.</p>
`allowed_values`|**Optional\[List\[int\]\]**|<p>A list of allowed values.</p>
`min_size`|**Optional\[int\]**|<p>The minimum number of elements in the array.</p>
`max_size`|**Optional\[int\]**|<p>The maximum number of elements in the array.</p>
