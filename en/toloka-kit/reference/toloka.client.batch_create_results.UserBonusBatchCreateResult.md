# UserBonusBatchCreateResult
`toloka.client.batch_create_results.UserBonusBatchCreateResult`

```python
UserBonusBatchCreateResult(
    self,
    *,
    items: Optional[Dict[str, UserBonus]] = None,
    validation_errors: Optional[Dict[str, Dict[str, FieldValidationError]]] = None
)
```

The result of issuing bonuses for Tolokers.


`UserBonusBatchCreateResult` is returned by the [create_user_bonuses](toloka.client.TolokaClient.create_user_bonuses.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[Dict\[str, [UserBonus](toloka.client.user_bonus.UserBonus.md)\]\]**|<p>A dictionary with created bonuses. The indexes of a `create_user_bonuses` input list are used as keys in the dictionary.</p>
`validation_errors`|**Optional\[Dict\[str, Dict\[str, [FieldValidationError](toloka.client.batch_create_results.FieldValidationError.md)\]\]\]**|<p>A dictionary with validation errors. It is filled if the request parameter `skip_invalid_items` is `True`.</p>

**Examples:**


```python
import decimal
bonuses=[
    toloka.client.user_bonus.UserBonus(
        user_id='fac97860c7929add8048ed2ef63b66fd',
        amount=decimal.Decimal('0.50'),
        public_title={'EN': 'Perfect job!'},
        public_message={'EN': 'You are the best!'},
        assignment_id='00001092da--61ef030400c684132d0da0de'
    ),
]
result = toloka_client.create_user_bonuses(user_bonuses=bonuses, skip_invalid_items=True)
print(result.items['0'].created)
```
