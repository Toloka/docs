# TrainingCloneOperation
`toloka.client.operations.TrainingCloneOperation` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/operations.py#L231)

```python
TrainingCloneOperation(
    self,
    *,
    id: Optional[str] = None,
    status: Union[Operation.Status, str, None] = None,
    submitted: Optional[datetime] = None,
    started: Optional[datetime] = None,
    finished: Optional[datetime] = None,
    progress: Optional[int] = None,
    parameters: Optional[TrainingOperation.Parameters] = None,
    details: Optional[Details] = None
)
```

Training cloning operation.


The operation is returned by the [clone_training_async](toloka.client.TolokaClient.clone_training_async.md) method.

Note, that `parameters.training_id` contains the ID of the training that is cloned.
While `details.training_id` contains the ID of the new training created after cloning.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the operation.</p>
`status`|**Optional\[[Operation.Status](toloka.client.operations.Operation.Status.md)\]**|<p>The status of the operation.</p>
`submitted`|**Optional\[datetime\]**|<p>The UTC date and time when the operation was requested.</p>
`started`|**Optional\[datetime\]**|<p>The UTC date and time when the operation started.</p>
`finished`|**Optional\[datetime\]**|<p>The UTC date and time when the operation finished.</p>
`progress`|**Optional\[int\]**|<p>The operation progress as a percentage.</p>
`parameters`|**Optional\[[TrainingOperation.Parameters](toloka.client.operations.TrainingOperation.Parameters.md)\]**|<p>Parameters containing the ID of the training.</p>
`details`|**Optional\[[Details](toloka.client.operations.TrainingCloneOperation.Details.md)\]**|<p>The details of the operation.</p>
