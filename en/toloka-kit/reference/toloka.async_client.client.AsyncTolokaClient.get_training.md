# get_training
`toloka.async_client.client.AsyncTolokaClient.get_training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/async_client/client.py#L0)

```python
async get_training(self, training_id: str)
```

Gets information about a training from Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>The ID of the training.</p>

* **Returns:**

  The training.

* **Return type:**

  [Training](toloka.client.training.Training.md)

**Examples:**


```python
t = toloka_client.get_training(training_id='1')
```
