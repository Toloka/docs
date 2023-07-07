# Get project details

_Get the detailed information about the project with the ID specified in the request._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Get project information {#step-three}

[Find out](./get-projects.md) the ID of the project for which you want to get the detailed information. Then get this info calling the `get_project()` method.

```python
project = toloka_client.[get_project](*get_project)('83859')
```

### 4. Print project name and status {#step-four}

The `get_project()` request will return the [Project](../reference/toloka.client.project.Project.md) class object. You can use its attributes to print the information you need.

```python
print(project.public_name, project.status)
```

You should get an output with the project name and status which looks like this.

```bash
Image classification ProjectStatus.ACTIVE
```

## Complete code: Get project details {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

project = toloka_client.get_project('83859')
print(project.public_name, project.status)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_project()](../reference/toloka.client.TolokaClient.get_project.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka-Kit: Project class](../reference/toloka.client.project.Project.md)
- [Toloka API: Get project by ID](https://toloka.ai/docs/api/api-reference/#get-/projects/-id-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_project]: [get_project()](../reference/toloka.client.TolokaClient.get_project.md) method