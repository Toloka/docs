# UserBonusCreateBatchOperation
`toloka.client.operations.UserBonusCreateBatchOperation` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/operations.py#L385)

```python
UserBonusCreateBatchOperation(
    self,
    *,
    id: Optional[str] = None,
    status: Union[Operation.Status, str, None] = None,
    submitted: Optional[datetime] = None,
    started: Optional[datetime] = None,
    finished: Optional[datetime] = None,
    progress: Optional[int] = None,
    parameters: Optional[Parameters] = None,
    details: Optional[Details] = None
)
```

Issuing payments operation.


The operation is returned by the [create_user_bonuses_async](toloka.client.TolokaClient.create_user_bonuses_async.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the operation.</p>
`status`|**Optional\[[Operation.Status](toloka.client.operations.Operation.Status.md)\]**|<p>The status of the operation.</p>
`submitted`|**Optional\[datetime\]**|<p>The UTC date and time when the operation was requested.</p>
`started`|**Optional\[datetime\]**|<p>The UTC date and time when the operation started.</p>
`finished`|**Optional\[datetime\]**|<p>The UTC date and time when the operation finished.</p>
`progress`|**Optional\[int\]**|<p>The operation progress as a percentage.</p>
`parameters`|**Optional\[[Parameters](toloka.client.operations.UserBonusCreateBatchOperation.Parameters.md)\]**|<p>Parameters of the `create_user_bonuses_async` request that started the operation.</p>
`details`|**Optional\[[Details](toloka.client.operations.UserBonusCreateBatchOperation.Details.md)\]**|<p>The details of the operation.</p>
