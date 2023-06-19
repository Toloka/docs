# IntegerSpec
`toloka.client.project.field_spec.IntegerSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/field_spec.py#L84)

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

An integer field specification.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`required`|**Optional\[bool\]**|<p>Whether a field is required. </p><p>Default value: `True`.</p>
`hidden`|**Optional\[bool\]**|<p>Whether to hide an input field from Tolokers. Output fields can&#x27;t be hidden. </p><p>Default value: `False`.</p>
`min_value`|**Optional\[int\]**|<p>The minimum value.</p>
`max_value`|**Optional\[int\]**|<p>The maximum value.</p>
`allowed_values`|**Optional\[List\[int\]\]**|<p>A list of allowed values.</p>
