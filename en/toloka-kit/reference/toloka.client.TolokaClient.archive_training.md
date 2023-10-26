# archive_training
`toloka.client.TolokaClient.archive_training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L1877)

```python
archive_training(self, training_id: str)
```

Archives a training.


Only closed trainings can be archived.

You can access archived trainings later.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>The ID of the training to be archived.</p>

* **Returns:**

  The training with updated status.

* **Return type:**

  [Training](toloka.client.training.Training.md)

**Examples:**


```python
closed_training = next(toloka_client.get_trainings(status='CLOSED'))
toloka_client.archive_training(training_id=closed_training.id)
```
