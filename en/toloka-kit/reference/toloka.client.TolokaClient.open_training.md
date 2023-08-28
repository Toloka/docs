# open_training
`toloka.client.TolokaClient.open_training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L2119)

```python
open_training(self, training_id: str)
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
toloka_client.open_training(training_id='1239110')
```
