# Accept responses from Tolokers

_Accept Toloker responses with the IDs specified in the request._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Accept Toloker response {#step-three}

[Find out](./get-responses.md) the ID of the Toloker response that your want to accept and use the [accept_assignment()](../reference/toloka.client.TolokaClient.accept_assignment.md) method to accept the response and leave a comment.

```python
accepted_assignment = toloka_client.[accept_assignment](*accept_assignment)('0001d38f5b--61c8be211c3a7842a596ac0a', 'OK')
```

The Toloker response will be marked as accepted with the `OK` comment added to it.

### 4. Print Toloker response status and public comment {#step-four}

The `accept_assignment()` request will return the [Assignment](../reference/toloka.client.assignment.Assignment.md) class object. You can use its attributes to print the information you need.

```python
print(accepted_assignment.status, accepted_assignment.public_comment)
```

You should get an output with the updated Toloker response status and public comment which looks like this.

```bash
Status.ACCEPTED OK
```

## Complete code: Accept responses from Tolokers {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

accepted_assignment = toloka_client.accept_assignment('0001d38f5b--61c8be211c3a7842a596ac0a', 'OK')
print(accepted_assignment.status, accepted_assignment.public_comment)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[accept_assignment()](../reference/toloka.client.TolokaClient.accept_assignment.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka-Kit: Assignment class](../reference/toloka.client.assignment.Assignment.md)
- [Toloka API: Update response](https://toloka.ai/docs/api/api-reference/#patch-/assignments/-id-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*accept_assignment]: [accept_assignment()](../reference/toloka.client.TolokaClient.accept_assignment.md) method