# StringSpec
`toloka.client.project.field_spec.StringSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/field_spec.py#L70)

```python
StringSpec(
    self,
    *,
    required: Optional[bool] = True,
    hidden: Optional[bool] = False,
    min_length: Optional[int] = None,
    max_length: Optional[int] = None,
    allowed_values: Optional[List[str]] = None
)
```

A string field specification.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`required`|**Optional\[bool\]**|<p>Whether a field is required. </p><p>Default value: `True`.</p>
`hidden`|**Optional\[bool\]**|<p>Whether to hide an input field from Tolokers. Output fields can&#x27;t be hidden. </p><p>Default value: `False`.</p>
`min_length`|**Optional\[int\]**|<p>The minimum length of the string.</p>
`max_length`|**Optional\[int\]**|<p>The maximum length of the string.</p>
`allowed_values`|**Optional\[List\[str\]\]**|<p>A list of allowed values.</p>
