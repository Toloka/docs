# IdempotentOperationParameters
`toloka.client.primitives.parameter.IdempotentOperationParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/primitives/parameter.py#L16)

```python
IdempotentOperationParameters(
    self,
    *,
    operation_id: Optional[UUID] = ...,
    async_mode: Optional[bool] = True
)
```

Parameters for idempotent operations such as tasks, task suites and user bonuses creation.


Works only with async_mode = True

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**Optional\[UUID\]**|<p>The ID of the operation conforming to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). We recommended sending the operation ID in the `POST` requests to avoid accidental errors: when you send several requests with the same `operation_id`, the operation will be performed only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p></p><p>Default value: `True`.</p>
