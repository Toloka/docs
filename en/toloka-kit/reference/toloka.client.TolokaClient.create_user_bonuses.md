# create_user_bonuses
`toloka.client.TolokaClient.create_user_bonuses` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L3129)

Issues several bonus payments to Tolokers.


You can send a maximum of 10,000 requests of this kind per day.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_bonuses`|**List\[[UserBonus](toloka.client.user_bonus.UserBonus.md)\]**|<p>A list of bonuses.</p>
`operation_id`|**Optional\[UUID\]**|<p>The UUID of the operation that conforms to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). The UUID is used if `async_mode` is `True`.</p> <p>Specify UUID to avoid accidental errors like Toloka operation duplication caused by network problems. If you send several requests with the same `operation_id`, Toloka performs the operation only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p>Default value: `True`.</p>
`skip_invalid_items`|**Optional\[bool\]**|<p>Bonus validation option:</p> <ul> <li>`True` — All valid bonuses are issued. If a bonus doesn't pass validation, then it isn't issued to a Toloker. All such bonuses are listed in the response.</li> <li>`False` — If any bonus doesn't pass validation, then the operation is cancelled and no bonuses are issued to Tolokers.</li> </ul> <p>Default value: `False`.</p>

* **Returns:**

  The result of the operation.

* **Return type:**

  [UserBonusBatchCreateResult](toloka.client.batch_create_results.UserBonusBatchCreateResult.md)

**Examples:**


```python
from decimal import Decimal
new_bonuses=[
    toloka.client.UserBonus(
        user_id='fac97860c7929add8048ed2ef63b66fd',
        amount=Decimal('1.00'),
        public_title={'EN': 'Perfect job!'},
        public_message={'EN': 'You are the best!'},
        assignment_id='00001092da--61ef030400c684132d0da0de'
    ),
    toloka.client.UserBonus(
        user_id='a1b0b42923c429daa2c764d7ccfc364d',
        amount=Decimal('0.80'),
        public_title={'EN': 'Excellent work!'},
        public_message={'EN': 'You have completed all tasks!'},
        assignment_id='000015fccc--63bfc4c358d7a46c32a7b233'
    )
]
result = toloka_client.create_user_bonuses(new_bonuses)
```
