# archive_project_async
`toloka.async_client.client.AsyncTolokaClient.archive_project_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/async_client/client.py#L0)

```python
async archive_project_async(self, project_id: str)
```

Archives a project. Sends an asynchronous request to Toloka.


All pools in the project must be archived before archiving the project.

The archived project is not deleted. You can access it if you need.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`project_id`|**str**|<p>The ID of project to be archived.</p>

* **Returns:**

  An object to track the progress of the operation.

* **Return type:**

  [ProjectArchiveOperation](toloka.client.operations.ProjectArchiveOperation.md)

**Examples:**


```python
archive_op = toloka_client.archive_project_async(project_id='117493')
toloka_client.wait_operation(archive_op)
```
