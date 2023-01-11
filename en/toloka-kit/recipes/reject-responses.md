# Reject responses from Tolokers

_Reject Toloker responses with the IDs specified in the request._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Reject Toloker response {#step-three}

[Find out](./get-responses.md) the ID of the Toloker response that your want to reject and use the [reject_assignment()](../reference/toloka.client.TolokaClient.reject_assignment.md) method to reject the response and leave a comment.

```python
rejected_assignment = toloka_client.[reject_assignment](*reject_assignment)('0001d38f5b--61c8be2074fdb82592f97887', 'The answer is not clear')
```

The Toloker response will be marked as rejected with the `The answer is not clear` comment added to it.

### 4. Print Toloker response status and public comment {#step-four}

The `reject_assignment()` request will return the [Assignment](../reference/toloka.client.assignment.Assignment.md) class object. You can use its attributes to print the information you need.

```python
print(rejected_assignment.status, rejected_assignment.public_comment)
```

You should get an output with the updated Toloker response status and public comment which looks like this.

```bash
Status.REJECTED The answer is not clear
```

## Complete code: Reject responses from Tolokers {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

rejected_assignment = toloka_client.reject_assignment('0001d38f5b--61c8be2074fdb82592f97887', 'The answer is not clear')
print(rejected_assignment.status, rejected_assignment.public_comment)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[reject_assignment()](../reference/toloka.client.TolokaClient.reject_assignment.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka-Kit: Assignment class](../reference/toloka.client.assignment.Assignment.md)
- [Toloka API: Update response](https://toloka.ai/docs/api/api-reference/#patch-/assignments/-id-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*reject_assignment]: [reject_assignment()](../reference/toloka.client.TolokaClient.reject_assignment.md) method