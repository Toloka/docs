# ArrayFileSpec
`toloka.client.project.field_spec.ArrayFileSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/field_spec.py#L203)

```python
ArrayFileSpec(
    self,
    *,
    required: Optional[bool] = True,
    hidden: Optional[bool] = False,
    min_size: Optional[int] = None,
    max_size: Optional[int] = None
)
```

A file array field specification.


`ArrayFileSpec` is used for output data only.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`required`|**Optional\[bool\]**|<p>Whether a field is required. </p><p>Default value: `True`.</p>
`hidden`|**Optional\[bool\]**|<p>Whether to hide an input field from Tolokers. Output fields can't be hidden. </p><p>Default value: `False`.</p>
`min_size`|**Optional\[int\]**|<p>The minimum number of elements in the array.</p>
`max_size`|**Optional\[int\]**|<p>The maximum number of elements in the array.</p>
