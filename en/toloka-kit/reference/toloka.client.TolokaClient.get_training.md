# get_training
`toloka.client.TolokaClient.get_training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/__init__.py#L1875)

```python
get_training(self, training_id: str)
```

Reads one specific training

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>ID of the training.</p>

* **Returns:**

  The training.

* **Return type:**

  [Training](toloka.client.training.Training.md)

**Examples:**


```python
toloka_client.get_training(training_id='1')
```
