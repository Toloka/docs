# PoolCloneOperation
`toloka.client.operations.PoolCloneOperation` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/operations.py#L157)

```python
PoolCloneOperation(
    self,
    *,
    id: Optional[str] = None,
    status: Union[Operation.Status, str, None] = None,
    submitted: Optional[datetime] = None,
    started: Optional[datetime] = None,
    finished: Optional[datetime] = None,
    progress: Optional[int] = None,
    parameters: Optional[PoolOperation.Parameters] = None,
    details: Optional[Details] = None
)
```

Pool cloning operation.


The operation is returned by the [clone_pool_async](toloka.client.TolokaClient.clone_pool_async.md) method.

Note, that `parameters.pool_id` contains the ID of the pool that is cloned.
While `details.pool_id` contains the ID of the new pool created after cloning.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the operation.</p>
`status`|**Optional\[[Operation.Status](toloka.client.operations.Operation.Status.md)\]**|<p>The status of the operation.</p>
`submitted`|**Optional\[datetime\]**|<p>The UTC date and time when the operation was requested.</p>
`started`|**Optional\[datetime\]**|<p>The UTC date and time when the operation started.</p>
`finished`|**Optional\[datetime\]**|<p>The UTC date and time when the operation finished.</p>
`progress`|**Optional\[int\]**|<p>The operation progress as a percentage.</p>
`parameters`|**Optional\[[PoolOperation.Parameters](toloka.client.operations.PoolOperation.Parameters.md)\]**|<p>Parameters containing the ID of the pool.</p>
`details`|**Optional\[[Details](toloka.client.operations.PoolCloneOperation.Details.md)\]**|<p>The details of the operation.</p>
