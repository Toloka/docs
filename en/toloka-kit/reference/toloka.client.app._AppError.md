# _AppError
`toloka.client.app._AppError` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/app/__init__.py#L20)

```python
_AppError(
    self,
    *,
    code: Optional[str] = None,
    message: Optional[str] = None,
    payload: Optional[Any] = None
)
```

A structure for describing errors which may appear while working with App projects.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`code`|**Optional\[str\]**|<p>The short name of the error.</p>
`message`|**Optional\[str\]**|<p>The detailed description of the error.</p>
`payload`|**Optional\[Any\]**|<p>Additional data provided with the error.</p>
