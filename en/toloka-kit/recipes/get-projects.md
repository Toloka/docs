# Get list of projects

_Get all the projects with a certain status created after a specified date._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Print project IDs, titles, and creation dates {#step-three}

Iterate through all the projects with the `ACTIVE` status created after October 1, 2022, calling the `get_projects()` method.

```python
for project in toloka_client.[get_projects](*get_projects)(
                  status='ACTIVE',
                    created_gte=datetime(2022, 10, 1)):
    print(project.id, project.public_name, project.created.date())
```

You should get an output with the project IDs, titles, and creation dates which looks like this.

```bash
119232 Image classification 2022-11-11
120798 Cat or Dog? 2022-11-22
123923 Product Search Relevance 2022-12-12
124269 Verify a business in your city 2022-12-14
126881 Elephant color 2022-12-29
```

## Complete code: Get list of projects {#complete-code}

```python
from datetime import datetime
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

for project in toloka_client.get_projects(
                  status='ACTIVE',
                  created_gte=datetime(2022, 10, 1)):
    print(project.id, project.public_name, project.created.date())
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_projects()](../reference/toloka.client.TolokaClient.get_projects.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](get-project-by-id.md)
- [Toloka API: Get list of projects](https://toloka.ai/docs/api/api-reference/#get-/projects)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_projects]: [get_projects()](../reference/toloka.client.TolokaClient.get_projects.md) method