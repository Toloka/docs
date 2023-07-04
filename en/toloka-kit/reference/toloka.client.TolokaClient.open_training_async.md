# open_training_async
`toloka.client.TolokaClient.open_training_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L2096)

```python
open_training_async(self, training_id: str)
```

Opens a training. Sends an asynchronous request to Toloka.


Tasks from opened trainings can be assigned to Tolokers.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>The ID of the training.</p>

* **Returns:**

  An object to track the progress of the operation.
If the training is already opened then `None` is returned.

* **Return type:**

  Optional\[[TrainingOpenOperation](toloka.client.operations.TrainingOpenOperation.md)\]

**Examples:**

Opening a training.

```python
open_op = toloka_client.open_training_async(training_id='1')
toloka_client.wait_operation(open_op)
```
