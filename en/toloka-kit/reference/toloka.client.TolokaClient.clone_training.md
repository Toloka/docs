# clone_training
`toloka.client.TolokaClient.clone_training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/__init__.py#L1802)

```python
clone_training(self, training_id: str)
```

Clones an existing training.


An empty training with the same parameters is created.
The new training is attached to the same project.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>The ID of the training to be cloned.</p>

* **Returns:**

  The new training.

* **Return type:**

  [Training](toloka.client.training.Training.md)

**Examples:**


```python
toloka_client.clone_training(training_id='1')
```
