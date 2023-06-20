# create_user_bonuses
`toloka.async_client.client.AsyncTolokaClient.create_user_bonuses` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L0)

Creates bonuses for Tolokers.


Right now it's safer to use asynchronous version: "create_user_bonuses_async"
You can send a maximum of 10,000 requests of this kind per day.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_bonuses`|**List\[[UserBonus](toloka.client.user_bonus.UserBonus.md)\]**|<p>To whom, how much to pay and for what.</p>
`operation_id`|**Optional\[UUID\]**|<p>The ID of the operation conforming to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). We recommended sending the operation ID in the `POST` requests to avoid accidental errors: when you send several requests with the same `operation_id`, the operation will be performed only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p></p><p>Default value: `True`.</p>
`skip_invalid_items`|**Optional\[bool\]**|<p>Validation parameters of objects:</p> <ul> <li>`True` — Award a bonus if the object with bonus information passed validation. Otherwise, skip the bonus.</li> <li>`False` — Default behavior. Stop the operation and don&#x27;t award bonuses if at least one object didn&#x27;t pass validation.</li> </ul>

* **Returns:**

  Result of creating bonuses. Contains `UserBonus` instances in `items` and
problems in `validation_errors`.

* **Return type:**

  [UserBonusBatchCreateResult](toloka.client.batch_create_results.UserBonusBatchCreateResult.md)

**Examples:**


```python
import decimal
new_bonuses=[
    UserBonus(
        user_id='1',
        amount=decimal.Decimal('0.50'),
        public_title={
            'EN': 'Perfect job!',
            'RU': 'Прекрасная работа!',
        },
        public_message={
            'EN': 'You are the best!',
            'RU': 'Молодец!',
        },
        assignment_id='1'
    ),
    UserBonus(
        user_id='2',
        amount=decimal.Decimal('1.0'),
        public_title={
            'EN': 'Excellent work!',
            'RU': 'Отличная работа!',
        },
        public_message={
            'EN': 'You have completed all tasks!',
            'RU': 'Сделаны все задания!',
        },
        assignment_id='2'
    )
]
toloka_client.create_user_bonuses(new_bonuses)
```
