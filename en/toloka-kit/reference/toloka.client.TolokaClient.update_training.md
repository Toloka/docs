# update_training
`toloka.client.TolokaClient.update_training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L2202)

```python
update_training(
    self,
    training_id: str,
    training: Training
)
```

Updates parameters of a training in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>The ID of the training to be updated.</p>
`training`|**[Training](toloka.client.training.Training.md)**|<p>A training object with new parameter values.</p>

* **Returns:**

  The updated training.

* **Return type:**

  [Training](toloka.client.training.Training.md)

**Examples:**

The example shows how to set new time limit in a training.

```python
updated_training = toloka_client.get_training(training_id='1239110')
updated_training.assignment_max_duration_seconds = 600
toloka_client.update_training(training_id=updated_training.id, training=updated_training)
```
