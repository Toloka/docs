# FileSpec
`toloka.client.project.field_spec.FileSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/field_spec.py#L116)

```python
FileSpec(
    self,
    *,
    required: Optional[bool] = True,
    hidden: Optional[bool] = False
)
```

A file field specification.


`FileSpec` is used for output data only.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`required`|**Optional\[bool\]**|<p>Whether a field is required. </p><p>Default value: `True`.</p>
`hidden`|**Optional\[bool\]**|<p>Whether to hide an input field from Tolokers. Output fields can&#x27;t be hidden. </p><p>Default value: `False`.</p>
