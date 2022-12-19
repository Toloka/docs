# open_training
`toloka.async_client.client.AsyncTolokaClient.open_training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/async_client/client.py#L0)

```python
async open_training(self, training_id: str)
```

Starts distributing tasks from the training

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>ID of the training that will be started.</p>

* **Returns:**

  Training object with new status.

* **Return type:**

  [Training](toloka.client.training.Training.md)

**Examples:**

Open the training for Tolokers.

```python
toloka_client.open_training(training_id='1')
```
