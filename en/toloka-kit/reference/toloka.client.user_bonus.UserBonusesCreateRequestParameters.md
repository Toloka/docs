# UserBonusesCreateRequestParameters
`toloka.client.user_bonus.UserBonusesCreateRequestParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/user_bonus.py#L82)

```python
UserBonusesCreateRequestParameters(
    self,
    *,
    operation_id: Optional[UUID] = ...,
    async_mode: Optional[bool] = True,
    skip_invalid_items: Optional[bool] = None
)
```

Parameters for issuing bonus payments to Tolokers.


The [create_user_bonuses](toloka.client.TolokaClient.create_user_bonuses.md) and [create_user_bonuses_async](toloka.client.TolokaClient.create_user_bonuses_async.md) methods use these parameters.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**Optional\[UUID\]**|<p>The UUID of the operation that conforms to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). The UUID is used if `async_mode` is `True`.</p> <p>Specify UUID to avoid accidental errors like Toloka operation duplication caused by network problems. If you send several requests with the same `operation_id`, Toloka performs the operation only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p></p><p>Default value: `True`.</p>
`skip_invalid_items`|**Optional\[bool\]**|<p>Bonus validation option:</p> <ul> <li>`True` — All valid bonuses are issued. If a bonus doesn&#x27;t pass validation, then it isn&#x27;t issued to a Toloker. All such bonuses are listed in the response.</li> <li>`False` — If any bonus doesn&#x27;t pass validation, then the operation is cancelled and no bonuses are issued to Tolokers.</li> </ul> <p></p><p>Default value: `False`.</p>
