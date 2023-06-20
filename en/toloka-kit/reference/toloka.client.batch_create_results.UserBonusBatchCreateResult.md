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
