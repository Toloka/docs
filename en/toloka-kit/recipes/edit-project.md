# Edit project

_Change the project public description using Toloka-Kit._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Get project {#step-three}

[Find out](get-projects.md) the ID of the project which you want to modify. Then create a local copy of the project object calling the `get_project()` method.

```python
project = toloka_client.[get_project](*get_project)('118252')
```

{% note alert "Important" %}

All the code manipulations at steps 3–4 occur in your device memory. The data will only be sent to the server after calling the `update_project()` method at [step 5](#step-five).

{% endnote %}

### 4. Set project new name {#step-four}

Specify a new public name that the Tolokers will see. You can choose to change some other project data. Refer to the [Project](../reference/toloka.client.project.Project.md) class to see what other attributes it has.

```python
project.public_name = "Elephant color (advanced)"
```

### 5. Modify project on platform {#step-five}

This actually updates the project data in Toloka.

```python
updated_project = toloka_client.[update_project](*update_project)(project.id, project)
```

### 6. Display modifications {#step-six}

The `update_project()` request will return the [Project](../reference/toloka.client.project.Project.md) class object. You can use its attributes to print the information you need.

```python
print(updated_project.public_name)
```

You should get an output with the updated project name which looks like this.

```bash
Elephant color (advanced)
```

## Complete code: Edit project {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

project = toloka_client.get_project('118252')
project.public_name = "Elephant color (advanced)"
updated_project = toloka_client.update_project(project.id, project)
print(updated_project.public_name)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_project()](../reference/toloka.client.TolokaClient.get_project.md) method_
- _[update_project()](../reference/toloka.client.TolokaClient.update_project.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](get-projects.md)
- [Toloka-Kit: Project class](../reference/toloka.client.project.Project.md)
- [Toloka API: Update project](https://toloka.ai/docs/api/api-reference/#put-/projects/-id-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_project]: [get_project()](../reference/toloka.client.TolokaClient.get_project.md) method
[*update_project]: [update_project()](../reference/toloka.client.TolokaClient.update_project.md) method