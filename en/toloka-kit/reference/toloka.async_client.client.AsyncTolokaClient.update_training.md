# update_training
`toloka.async_client.client.AsyncTolokaClient.update_training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/async_client/client.py#L0)

```python
async update_training(
    self,
    training_id: str,
    training: Training
)
```

Makes changes to the training

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>ID of the training that will be changed.</p>
`training`|**[Training](toloka.client.training.Training.md)**|<p>A training object with all the fields: those that will be updated and those that will not.</p>

* **Returns:**

  Training object with all fields.

* **Return type:**

  [Training](toloka.client.training.Training.md)

**Examples:**

If you want to update any configurations of the existing training.

```python
updated_training = toloka_client.update_training(training_id=old_training_id, training=new_training_object)
```
