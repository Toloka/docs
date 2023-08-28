# UserBonusCreateRequestParameters
`toloka.client.user_bonus.UserBonusCreateRequestParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/user_bonus.py#L73)

```python
UserBonusCreateRequestParameters(
    self,
    *,
    operation_id: Optional[UUID] = ...,
    async_mode: Optional[bool] = True
)
```

Parameters for issuing a bonus payment to a Toloker.


The [create_user_bonus](toloka.client.TolokaClient.create_user_bonus.md) method uses these parameters.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**Optional\[UUID\]**|<p>The UUID of the operation that conforms to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). The UUID is used if `async_mode` is `True`.</p> <p>Specify UUID to avoid accidental errors like Toloka operation duplication caused by network problems. If you send several requests with the same `operation_id`, Toloka performs the operation only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p></p><p>Default value: `True`.</p>
