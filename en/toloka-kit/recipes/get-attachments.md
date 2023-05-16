# Get list of files in responses

_List all the files attached to the Toloker responses in a pool._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. List attachments {#step-three}

[Find out](./get-pools.md) the ID of the pools for which you want to get all the files attached to the Toloker responses. Then iterate through all the attachments calling the `get_attachments()` method.

```python
for attachment in toloka_client.[get_attachments](*get_attachments)(pool_id='1085757'):
    print(attachment.id, attachment.name)
```

You should get an output that contains the IDs of the attachments and file names. It will look like this.

```bash
fr.5867be74-249b-4264-9ed0-aa5d4c201846 gx6864-almost-blue-1.jpg
fr.c548ebeb-dd92-4b2b-8113-4a69af1471ba nike_104090949.png
fr.cd9cdda5-4af6-4be9-b351-678b2b4e189f 37540601-sneaker-search.jpg
```

## Complete code: Get list of files in responses {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

for attachment in toloka_client.get_attachments(pool_id='1085757'):
    print(attachment.id, attachment.name)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_attachments()](../reference/toloka.client.TolokaClient.get_attachments.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [{#T}](./get-pools.md)
- [Toloka API: Get list of files](https://toloka.ai/docs/api/api-reference/#get-/attachments)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_attachments]: [get_attachments()](../reference/toloka.client.TolokaClient.get_attachments.md) method