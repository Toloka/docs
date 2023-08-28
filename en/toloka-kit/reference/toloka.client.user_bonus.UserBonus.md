# UserBonus
`toloka.client.user_bonus.UserBonus` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/user_bonus.py#L17)

```python
UserBonus(
    self,
    *,
    user_id: Optional[str] = None,
    amount: Optional[Decimal] = None,
    private_comment: Optional[str] = None,
    public_title: Optional[Dict[str, str]] = None,
    public_message: Optional[Dict[str, str]] = None,
    without_message: Optional[bool] = None,
    assignment_id: Optional[str] = None,
    id: Optional[str] = None,
    created: Optional[datetime] = None
)
```

A bonus payment to a Toloker.


Learn more about [Bonuses](https://toloka.ai/docs/guide/bonus/).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the bonus.</p>
`user_id`|**Optional\[str\]**|<p>The ID of the Toloker.</p>
`amount`|**Optional\[Decimal\]**|<p>The amount of the bonus in US dollars.</p>
`assignment_id`|**Optional\[str\]**|<p>The ID of the assignment the bonus is issued for.</p>
`private_comment`|**Optional\[str\]**|<p>A comment visible to the requester only.</p>
`without_message`|**Optional\[bool\]**|<ul> <li>`False` — A message is sent to the Toloker when the bonus is issued.</li> <li>`True` — There is no message sent to the Toloker.</li> </ul> <p></p><p>Default value: `False`.</p>
`public_title`|**Optional\[Dict\[str, str\]\]**|<p>A message title. The title can be provided in several languages.</p>
`public_message`|**Optional\[Dict\[str, str\]\]**|<p>A message text. It can be provided in several languages.</p>
`created`|**Optional\[datetime\]**|<p>The UTC date and time when the bonus was issued. Read-only field.</p>

**Examples:**

An example of issuing a bonus. A message to a Toloker is prepared in two languages.

```python
from decimal import Decimal
new_bonus = toloka_client.create_user_bonus(
    toloka.client.UserBonus(
        user_id='a1b0b42923c429daa2c764d7ccfc364d',
        amount=Decimal('0.50'),
        public_title={
            'EN': 'Good Job!',
            'RU': 'Молодец!',
        },
        public_message={
            'EN': 'Ten tasks were completed',
            'RU': 'Выполнено 10 заданий',
        },
        assignment_id='000015fccc--63bfc4c358d7a46c32a7b233'
    )
)
```
