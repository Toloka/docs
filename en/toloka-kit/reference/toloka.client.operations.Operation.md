# Operation
`toloka.client.operations.Operation` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/operations.py#L51)

```python
Operation(
    self,
    *,
    id: Optional[str] = None,
    status: Union[Status, str, None] = None,
    submitted: Optional[datetime] = None,
    parameters: Optional[Parameters] = None,
    started: Optional[datetime] = None,
    finished: Optional[datetime] = None,
    progress: Optional[int] = None,
    details: Optional[Any] = None
)
```

A base class for Toloka operations.


Some API requests start asynchronous operations in Toloka. Classes derived from `Operation` are used to track them.
The examples of asynchronous operations are opening a pool, archiving a project, loading multiple tasks.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the operation.</p>
`status`|**Optional\[[Status](toloka.client.operations.Operation.Status.md)\]**|<p>The status of the operation.</p>
`submitted`|**Optional\[datetime\]**|<p>The UTC date and time when the operation was requested.</p>
`parameters`|**Optional\[[Parameters](toloka.client.operations.Operation.Parameters.md)\]**|<p>Parameters of the request that started the operation.</p>
`started`|**Optional\[datetime\]**|<p>The UTC date and time when the operation started.</p>
`finished`|**Optional\[datetime\]**|<p>The UTC date and time when the operation finished.</p>
`progress`|**Optional\[int\]**|<p>The operation progress as a percentage.</p>
`details`|**Optional\[Any\]**|<p>Details of the operation completion.</p>
## Methods Summary

| Method | Description |
| :------| :-----------|
[is_completed](toloka.client.operations.Operation.is_completed.md)| Checks whether the operation is completed either successfully or not.
[raise_on_fail](toloka.client.operations.Operation.raise_on_fail.md)| Raises the `FailedOperation` exception if the operation status is `FAIL`. Otherwise does nothing.
