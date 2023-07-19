# Get list of responses

_Get all the Toloker responses present in the pool with the ID specified in the request._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Print responses IDs and statuses {#step-three}

Iterate through all the Toloker responses present in the pool with the ID specified in the request calling the `get_assignments()` method.

```python
for assignment in toloka_client.[get_assignments](*get_assignments)(pool_id='1085757'):
    print(assignment.id, assignment.status)
```

You should get an output with the response IDs and statuses which looks like this.

```bash
000015fccc--63bfc4c358d7a46c32a7b233 Status.ACCEPTED
000015fccc--63bfc4e0ed43982367a5ad46 Status.REJECTED
000015fccc--63bfc4ea99e537000bac4015 Status.SUBMITTED
```

## Complete code: Get list of responses {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

for assignment in toloka_client.get_assignments(pool_id='1085757'):
    print(assignment.id, assignment.status)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_assignments()](../reference/toloka.client.TolokaClient.get_assignments.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [Toloka API: Get list of responses](https://toloka.ai/docs/api/api-reference/#get-/assignments)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_assignments]: [get_assignments()](../reference/toloka.client.TolokaClient.get_assignments.md) method