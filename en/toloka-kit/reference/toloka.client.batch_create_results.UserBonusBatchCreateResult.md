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

The results of the creating rewards for Tolokers.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[Dict\[str, [UserBonus](toloka.client.user_bonus.UserBonus.md)\]\]**|<p>A list of created rewards.</p>
`validation_errors`|**Optional\[Dict\[str, Dict\[str, [FieldValidationError](toloka.client.batch_create_results.FieldValidationError.md)\]\]\]**|<p>A list with validation errors. The list is filled if the request parameter `skip_invalid_items` is `True`.</p>
