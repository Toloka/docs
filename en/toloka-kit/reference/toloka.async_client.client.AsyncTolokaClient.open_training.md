# open_training
`toloka.async_client.client.AsyncTolokaClient.open_training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/async_client/client.py#L0)

```python
async open_training(self, training_id: str)
```

Opens a training.


Tasks from opened trainings can be assigned to Tolokers.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>The ID of the training.</p>

* **Returns:**

  The training with updated status.

* **Return type:**

  [Training](toloka.client.training.Training.md)

**Examples:**

Opening a training.

```python
toloka_client.open_training(training_id='1')
```
