# close_training
`toloka.async_client.client.AsyncTolokaClient.close_training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/async_client/client.py#L0)

```python
async close_training(self, training_id: str)
```

Closes a training.


Tasks from closed trainings are not assigned to Tolokers.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>The ID of the training to be closed.</p>

* **Returns:**

  The training with updated status.

* **Return type:**

  [Training](toloka.client.training.Training.md)

**Examples:**


```python
opened_training = next(toloka_client.get_trainings(status='OPEN'))
toloka_client.close_training(training_id=opened_training.id)
```
