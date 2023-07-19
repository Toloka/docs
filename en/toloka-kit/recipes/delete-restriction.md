# Remove ban from Toloker

_Remove restriction from Tolokers and restore their access to tasks._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Remove ban from Toloker {#step-three}

[Find out](get-restrictions.md#step-three) the ID of the ban. This ID is unique for each Toloker whom you banned on your projects or pools. Use the `delete_user_restriction()` method to remove the skill from the Toloker.

```python
toloka_client.[delete_user_restriction](*delete_user_restriction)(user_restriction_id='163293423')
```

If everything goes as expected, the request will return an empty response.

## Complete code: Remove ban from Toloker {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

toloka_client.delete_user_restriction(user_restriction_id='163293423')
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[delete_user_restriction()](../reference/toloka.client.TolokaClient.delete_user_restriction.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](get-restrictions.md)
- [Toloka API: Unblock access](https://toloka.ai/docs/api/api-reference/#delete-/user-restrictions/-id-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*delete_user_restriction]: [delete_user_restriction()](../reference/toloka.client.TolokaClient.delete_user_restriction.md) method