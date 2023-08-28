# create_user_bonus
`toloka.async_client.client.AsyncTolokaClient.create_user_bonus` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L0)

Issues a bonus payment to a Toloker.


You can send a maximum of 10,000 requests of this kind per day.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_bonus`|**[UserBonus](toloka.client.user_bonus.UserBonus.md)**|<p>The bonus.</p>
`operation_id`|**Optional\[UUID\]**|<p>The UUID of the operation that conforms to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). The UUID is used if `async_mode` is `True`.</p> <p>Specify UUID to avoid accidental errors like Toloka operation duplication caused by network problems. If you send several requests with the same `operation_id`, Toloka performs the operation only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p></p><p>Default value: `True`.</p>

* **Returns:**

  Created bonus.

* **Return type:**

  [UserBonus](toloka.client.user_bonus.UserBonus.md)

**Examples:**

Issuing a bonus to a Toloker with a message in 2 languages.

```python
from decimal import Decimal
new_bonus = toloka_client.create_user_bonus(
    toloka.client.UserBonus(
        user_id='fac97860c7929add8048ed2ef63b66fd',
        amount=Decimal('0.50'),
        public_title={
            'EN': 'Perfect job!',
            'RU': 'Прекрасная работа!',
        },
        public_message={
            'EN': 'You are the best!',
            'RU': 'Молодец!',
        },
        assignment_id='00001092da--61ef030400c684132d0da0de'
    )
)
```
