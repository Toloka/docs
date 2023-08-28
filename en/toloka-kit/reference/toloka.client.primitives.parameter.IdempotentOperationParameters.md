# IdempotentOperationParameters
`toloka.client.primitives.parameter.IdempotentOperationParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/primitives/parameter.py#L16)

```python
IdempotentOperationParameters(
    self,
    *,
    operation_id: Optional[UUID] = ...,
    async_mode: Optional[bool] = True
)
```

Parameters for idempotent operations such as tasks, task suites and user bonuses creation.


Works only with `async_mode = True`.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**Optional\[UUID\]**|<p>The UUID of the operation that conforms to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). The UUID is used if `async_mode` is `True`.</p> <p>Specify UUID to avoid accidental errors like Toloka operation duplication caused by network problems. If you send several requests with the same `operation_id`, Toloka performs the operation only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p>Default value: `True`.</p>
