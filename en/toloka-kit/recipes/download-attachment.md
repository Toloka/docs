# Download attachments

_Download the files attached to the Toloker responses._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Download attachment {#step-three}

[Find out](./get-attachments.md) the ID and the extension of the file attached to the Toloker response which you want to download. Then download this file calling the `download_attachment()` method.

```python
# Use the standard 'with open()' Python method with the 'wb' (write + binary) parameters specified
with open(attachment_id + '.jpg', 'wb') as attachment_file:
    toloka_client.[download_attachment](*download_attachment)('fr.5867be74-249b-4264-9ed0-aa5d4c201846', out=attachment_file)
```

The attachment will be saved to the specified `out` destination.

## Complete code: Download attachments {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

with open(attachment_id + '.jpg', 'wb') as attachment_file:
    toloka_client.download_attachment('fr.5867be74-249b-4264-9ed0-aa5d4c201846', out=attachment_file)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[download_attachment()](../reference/toloka.client.TolokaClient.download_attachment.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [{#T}](./get-attachments.md)
- [Toloka API: Download file](https://toloka.ai/docs/api/api-reference/#get-/attachments/-id-/download)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*download_attachment]: [download_attachment()](../reference/toloka.client.TolokaClient.download_attachment.md) method