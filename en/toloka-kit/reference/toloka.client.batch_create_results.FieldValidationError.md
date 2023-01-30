# FieldValidationError
`toloka.client.batch_create_results.FieldValidationError` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/batch_create_results.py#L16)

```python
FieldValidationError(
    self,
    *,
    code: Optional[str] = None,
    message: Optional[str] = None,
    params: Optional[List[Any]] = None
)
```

Error that contains information about an invalid field.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`code`|**Optional\[str\]**|<p>An error code.</p>
`message`|**Optional\[str\]**|<p>An error message.</p>
`params`|**Optional\[List\[Any\]\]**|<p>Additional parameters describing the error.</p>
