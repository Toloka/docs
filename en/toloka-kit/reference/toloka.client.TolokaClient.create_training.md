# create_training
`toloka.client.TolokaClient.create_training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L1947)

```python
create_training(self, training: Training)
```

Creates a new training in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training`|**[Training](toloka.client.training.Training.md)**|<p>A training to be created.</p>

* **Returns:**

  Created training with initialized read-only fields.

* **Return type:**

  [Training](toloka.client.training.Training.md)

**Examples:**

Creating a new training.

```python
new_training = toloka.client.Training(
    project_id='1',
    private_name='Some training in my project',
    may_contain_adult_content=True,
    assignment_max_duration_seconds=60*5,
    mix_tasks_in_creation_order=True,
    shuffle_tasks_in_task_suite=True,
    training_tasks_in_task_suite_count=3,
    task_suites_required_to_pass=1,
    retry_training_after_days=7,
    inherited_instructions=True,
    public_instructions='',
)
new_training = toloka_client.create_training(new_training)
print(new_training.id)
```
