# CloneResults
`toloka.client.clone_results.CloneResults` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/clone_results.py#L8)

The result of a project deep cloning.


`CloneResults` is returned by the [clone_project](toloka.client.TolokaClient.clone_project.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`project`|**[Project](toloka.client.project.Project.md)**|<p>The cloned project.</p>
`pools`|**List\[[Pool](toloka.client.pool.Pool.md)\]**|<p>A list of cloned pools.</p>
`trainings`|**List\[[Training](toloka.client.training.Training.md)\]**|<p>A list of cloned trainings.</p>

**Examples:**


```python
result = toloka_client.clone_project(project_id='92694')
print('Project ID:', result.project.id)
print('Pools:', len(result.pools))
print('Trainings:', len(result.trainings))
```
