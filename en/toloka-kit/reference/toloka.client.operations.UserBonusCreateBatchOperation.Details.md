# Details
`toloka.client.operations.UserBonusCreateBatchOperation.Details` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/operations.py#L399)

```python
Details(
    self,
    *,
    pool_id: Optional[str] = None,
    total_count: Optional[int] = None,
    valid_count: Optional[int] = None,
    not_valid_count: Optional[int] = None,
    success_count: Optional[int] = None,
    failed_count: Optional[int] = None
)
```

The details of the `UserBonusCreateBatchOperation` operation.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`total_count`|**Optional\[int\]**|<p>The total number of `UserBonus` objects in the request.</p>
`valid_count`|**Optional\[int\]**|<p>The number of `UserBonus` objects that passed validation.</p>
`not_valid_count`|**Optional\[int\]**|<p>The number of `UserBonus` objects that didn't pass validation.</p>
`success_count`|**Optional\[int\]**|<p>The number of `UserBonus` that were issued to Tolokers.</p>
`failed_count`|**Optional\[int\]**|<p>The number of `UserBonus` that were not issued to Tolokers.</p>
