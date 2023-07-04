# UserBonusCreateRequestParameters
`toloka.client.user_bonus.UserBonusCreateRequestParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/user_bonus.py#L89)

```python
UserBonusCreateRequestParameters(
    self,
    *,
    operation_id: Optional[UUID] = ...,
    async_mode: Optional[bool] = True
)
```

Parameters for creating bonus for Toloker.


Used in methods 'create_user_bonus' of the class TolokaClient.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**Optional\[UUID\]**|<p>The ID of the operation conforming to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). We recommended sending the operation ID in the `POST` requests to avoid accidental errors: when you send several requests with the same `operation_id`, the operation will be performed only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p>Default value: `True`.</p>
