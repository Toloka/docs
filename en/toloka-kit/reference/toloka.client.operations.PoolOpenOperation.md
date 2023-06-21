# PoolOpenOperation
`toloka.client.operations.PoolOpenOperation` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/operations.py#L180)

```python
PoolOpenOperation(
    self,
    *,
    id: Optional[str] = None,
    status: Union[Operation.Status, str, None] = None,
    submitted: Optional[datetime] = None,
    started: Optional[datetime] = None,
    finished: Optional[datetime] = None,
    progress: Optional[int] = None,
    details: Optional[Any] = None,
    parameters: Optional[PoolOperation.Parameters] = None
)
```

Operation returned by an asynchronous opening pool via TolokaClient.open_pool_async()

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>Operation ID.</p>
`status`|**Optional\[[Operation.Status](toloka.client.operations.Operation.Status.md)\]**|<p>The status of the operation.</p>
`submitted`|**Optional\[datetime\]**|<p>The UTC date and time the request was sent.</p>
`started`|**Optional\[datetime\]**|<p>The UTC date and time the operation started.</p>
`finished`|**Optional\[datetime\]**|<p>The UTC date and time the operation finished.</p>
`progress`|**Optional\[int\]**|<p>The percentage of the operation completed.</p>
`details`|**Optional\[Any\]**|<p>Details of the operation completion.</p>
`parameters`|**Optional\[[PoolOperation.Parameters](toloka.client.operations.PoolOperation.Parameters.md)\]**|<p>Operation parameters (depending on the operation type).</p>
`pool_id`|**-**|<p>On which pool operation is performed.</p>
