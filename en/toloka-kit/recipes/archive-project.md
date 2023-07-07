# Archive project

_Move the project which you no longer use into archive._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Archive project {#step-three}

[Find out](./get-projects.md) the ID of the project which you want to archive. Then call the `archive_project()` method.

```python
archived_project = toloka_client.[archive_project](*archive_project)('117493')
```

### 4. Print project ID and status {#step-four}

The `archive_project()` request will return the [Project](../reference/toloka.client.project.Project.md) class object. You can use its attributes to print the information you need.

```python
print(archived_project.id, archived_project.status)
```

You should get an output with the project ID and the updated status which looks like this.

```bash
117493 ProjectStatus.ARCHIVED
```

## Complete code: Archive project {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

archived_project = toloka_client.archive_project('117493')
print(archived_project.id, archived_project.status)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[archive_project()](../reference/toloka.client.TolokaClient.archive_project.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [{#T}](./get-projects.md)
- [Toloka-Kit: Project class](../reference/toloka.client.project.Project.md)
- [Toloka API: Archive project](https://toloka.ai/docs/api/api-reference/#post-/projects/-id-/archive)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*archive_project]: [archive_project()](../reference/toloka.client.TolokaClient.archive_project.md) method