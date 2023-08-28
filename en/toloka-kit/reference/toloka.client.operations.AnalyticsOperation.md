# AnalyticsOperation
`toloka.client.operations.AnalyticsOperation` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/operations.py#L120)

```python
AnalyticsOperation(
    self,
    *,
    id: Optional[str] = None,
    status: Union[Operation.Status, str, None] = None,
    submitted: Optional[datetime] = None,
    parameters: Optional[Operation.Parameters] = None,
    started: Optional[datetime] = None,
    finished: Optional[datetime] = None,
    progress: Optional[int] = None,
    details: Optional[Any] = None
)
```

Analytics operation.


The operation is returned by the [get_analytics](toloka.client.TolokaClient.get_analytics.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the operation.</p>
`status`|**Optional\[[Operation.Status](toloka.client.operations.Operation.Status.md)\]**|<p>The status of the operation.</p>
`submitted`|**Optional\[datetime\]**|<p>The UTC date and time when the operation was requested.</p>
`parameters`|**Optional\[[Operation.Parameters](toloka.client.operations.Operation.Parameters.md)\]**|<p>Parameters of the request that started the operation.</p>
`started`|**Optional\[datetime\]**|<p>The UTC date and time when the operation started.</p>
`finished`|**Optional\[datetime\]**|<p>The UTC date and time when the operation finished.</p>
`progress`|**Optional\[int\]**|<p>The operation progress as a percentage.</p>
`details`|**Optional\[Any\]**|<p>Details of the operation completion.</p>
