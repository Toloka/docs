# close_training_async
`toloka.async_client.client.AsyncTolokaClient.close_training_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/async_client/client.py#L0)

```python
async close_training_async(self, training_id: str)
```

Stops distributing tasks from the training, asynchronous version

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>ID of the training that will be closed.</p>

* **Returns:**

  An operation upon completion of which you can get the training with updated status.
If training is already closed then None is returned.

* **Return type:**

  Optional\[[TrainingCloseOperation](toloka.client.operations.TrainingCloseOperation.md)\]

**Examples:**


```python
open_training = next(toloka_client.get_trainings(status='OPEN'))
close_training = toloka_client.close_training_async(training_id=open_training.id)
toloka_client.wait_operation(close_training)
```
