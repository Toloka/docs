# close_training_async
`toloka.async_client.client.AsyncTolokaClient.close_training_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/async_client/client.py#L0)

```python
async close_training_async(self, training_id: str)
```

Closes a training. Sends an asynchronous request to Toloka.


Tasks from closed trainings are not assigned to Tolokers.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>The ID of the training to be closed.</p>

* **Returns:**

  An object to track the progress of the operation. If the training is already closed then `None` is returned.

* **Return type:**

  Optional\[[TrainingCloseOperation](toloka.client.operations.TrainingCloseOperation.md)\]

**Examples:**


```python
opened_training = next(toloka_client.get_trainings(status='OPEN'))
close_op = toloka_client.close_training_async(training_id=opened_training.id)
toloka_client.wait_operation(close_op)
```
