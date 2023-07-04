# SpecClassIdentificationError
`toloka.client.exceptions.SpecClassIdentificationError` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/exceptions.py#L28)

```python
SpecClassIdentificationError(
    self,
    *,
    spec_field: Optional[str] = None,
    spec_enum: Optional[str] = None
)
```

An exception that is raised when a specification сlass can't be find for a field specification name.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`spec_field`|**Optional\[str\]**|<p>The field specification name.</p>
`spec_enum`|**Optional\[str\]**|<p>An enumeration with all known specification names.</p>
