# ApiError
`toloka.client.exceptions.ApiError` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/exceptions.py#L54)

```python
ApiError(
    self,
    *,
    request_id: Optional[str] = None,
    code: Optional[str] = None,
    message: Optional[str] = None,
    payload: Optional[Any] = None,
    status_code: Optional[int] = None,
    response: Optional[Response] = None
)
```

A base class for exceptions that are raised when API methods return errors.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`status_code`|**Optional\[int\]**|<p>A HTTP response status code.</p>
`request_id`|**Optional\[str\]**|<p>The ID of the request that returns an error.</p>
`code`|**Optional\[str\]**|<p>An error code.</p>
`message`|**Optional\[str\]**|<p>An error description.</p>
`payload`|**Optional\[Any\]**|<p>Additional data describing an error.</p>
