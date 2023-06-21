# UserBonusesCreateRequestParameters
`toloka.client.user_bonus.UserBonusesCreateRequestParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/user_bonus.py#L98)

```python
UserBonusesCreateRequestParameters(
    self,
    *,
    operation_id: Optional[UUID] = ...,
    async_mode: Optional[bool] = True,
    skip_invalid_items: Optional[bool] = None
)
```

Parameters for creating bonuses for Tolokers.


Used in methods 'create_user_bonuses' и 'create_user_bonuses_async' of the class TolokaClient,
to clarify the behavior when creating bonuses.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**Optional\[UUID\]**|<p>The ID of the operation conforming to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). We recommended sending the operation ID in the `POST` requests to avoid accidental errors: when you send several requests with the same `operation_id`, the operation will be performed only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p></p><p>Default value: `True`.</p>
`skip_invalid_items`|**Optional\[bool\]**|<p>Validation parameters of objects:</p> <ul> <li>`True` — Award a bonus if the object with bonus information passed validation. Otherwise, skip the bonus.</li> <li>`False` — Default behavior. Stop the operation and don&#x27;t award bonuses if at least one object didn&#x27;t pass validation.</li> </ul>
