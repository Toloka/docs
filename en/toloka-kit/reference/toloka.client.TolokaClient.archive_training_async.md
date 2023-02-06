# archive_training_async
`toloka.client.TolokaClient.archive_training_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/__init__.py#L1729)

```python
archive_training_async(self, training_id: str)
```

Archives a training. Sends an asynchronous request to Toloka.


Only closed trainings can be archived.

You can access archived trainings later.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>The ID of the training to be archived.</p>

* **Returns:**

  An object to track the progress of the operation. If the training is already archived then `None` is returned.

* **Return type:**

  Optional\[[TrainingArchiveOperation](toloka.client.operations.TrainingArchiveOperation.md)\]

**Examples:**


```python
closed_training = next(toloka_client.find_trainings(status='CLOSED'))
archive_op = toloka_client.archive_training_async(training_id=closed_training.id)
toloka_client.wait_operation(archive_op)
```
