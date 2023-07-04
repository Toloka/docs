# clone_training_async
`toloka.client.TolokaClient.clone_training_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L1926)

```python
clone_training_async(self, training_id: str)
```

Clones an existing training. Sends an asynchronous request to Toloka.


An empty training with the same parameters is created.
The new training is attached to the same project.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_id`|**str**|<p>The ID of the training to be cloned.</p>

* **Returns:**

  An object to track the progress of the operation.

* **Return type:**

  [TrainingCloneOperation](toloka.client.operations.TrainingCloneOperation.md)

**Examples:**


```python
clone_op = toloka_client.clone_training_async(training_id='1')
toloka_client.wait_operation(clone_op)
```
