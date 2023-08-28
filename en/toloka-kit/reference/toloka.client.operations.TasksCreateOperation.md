# TasksCreateOperation
`toloka.client.operations.TasksCreateOperation` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/operations.py#L300)

```python
TasksCreateOperation(
    self,
    *,
    id: Optional[str] = None,
    status: Union[Operation.Status, str, None] = None,
    submitted: Optional[datetime] = None,
    started: Optional[datetime] = None,
    progress: Optional[int] = None,
    parameters: Optional[Parameters] = None,
    finished: Optional[datetime] = None,
    details: Optional[Any] = None
)
```

Task creating operation.


The operation is returned by the [create_tasks_async](toloka.client.TolokaClient.create_tasks_async.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the operation.</p>
`status`|**Optional\[[Operation.Status](toloka.client.operations.Operation.Status.md)\]**|<p>The status of the operation.</p>
`submitted`|**Optional\[datetime\]**|<p>The UTC date and time when the operation was requested.</p>
`started`|**Optional\[datetime\]**|<p>The UTC date and time when the operation started.</p>
`progress`|**Optional\[int\]**|<p>The operation progress as a percentage.</p>
`parameters`|**Optional\[[Parameters](toloka.client.operations.TasksCreateOperation.Parameters.md)\]**|<p>Parameters passed to the `create_tasks_async` method.</p>
`finished`|**Optional\[datetime\]**|<p>The UTC date and time when the operation was completed.</p>
`details`|**Optional\[Any\]**|<p>Details of the operation completion.</p>
