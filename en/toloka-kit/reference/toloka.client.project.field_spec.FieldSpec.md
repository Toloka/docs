# FieldSpec
`toloka.client.project.field_spec.FieldSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/field_spec.py#L48)

```python
FieldSpec(
    self,
    *,
    required: Optional[bool] = True,
    hidden: Optional[bool] = False
)
```

A base class for field specifications used in project's `input_spec` and `output_spec` for input and response data validation.


Use subclasses of this class to define the data type and set constraints such as maximum string length.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`required`|**Optional\[bool\]**|<p>Whether a field is required. </p><p>Default value: `True`.</p>
`hidden`|**Optional\[bool\]**|<p>Whether to hide an input field from Tolokers. Output fields can&#x27;t be hidden. </p><p>Default value: `False`.</p>
