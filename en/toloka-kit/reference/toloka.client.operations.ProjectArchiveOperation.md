# ProjectArchiveOperation
`toloka.client.operations.ProjectArchiveOperation` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/operations.py#L277)

```python
ProjectArchiveOperation(
    self,
    *,
    id: Optional[str] = None,
    status: Union[Operation.Status, str, None] = None,
    submitted: Optional[datetime] = None,
    started: Optional[datetime] = None,
    finished: Optional[datetime] = None,
    progress: Optional[int] = None,
    details: Optional[Any] = None,
    parameters: Optional[Parameters] = None
)
```

Project archiving operation.


The operation is returned by the [archive_project_async](toloka.client.TolokaClient.archive_project_async.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the operation.</p>
`status`|**Optional\[[Operation.Status](toloka.client.operations.Operation.Status.md)\]**|<p>The status of the operation.</p>
`submitted`|**Optional\[datetime\]**|<p>The UTC date and time when the operation was requested.</p>
`started`|**Optional\[datetime\]**|<p>The UTC date and time when the operation started.</p>
`finished`|**Optional\[datetime\]**|<p>The UTC date and time when the operation finished.</p>
`progress`|**Optional\[int\]**|<p>The operation progress as a percentage.</p>
`details`|**Optional\[Any\]**|<p>Details of the operation completion.</p>
`parameters`|**Optional\[[Parameters](toloka.client.operations.ProjectArchiveOperation.Parameters.md)\]**|<p>Parameters with the ID of the project.</p>
