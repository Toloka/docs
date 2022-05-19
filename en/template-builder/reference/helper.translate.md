# helper.translate

Component for translating interface elements to other languages. More details in [Translating the task interface](https://toloka.ai/docs/guide/concepts/project-languages.html#project-languages__interface-translate).

In the properties that should be displayed in different languages, add:

```
{
  "type": "helper.translate",
  "key": "<key name>"
{
```

Adding the `key` property displays a field for entering the key text. Enter the text in the source language. In the "Translations" step, add translations for the keys in the desired languages.

Usage example:

```
{
  "view": {
    "type": "view.image",
    "url": "https://yastat.net/s3/tb/static/file-examples/image/small.png",
    "label": {
      "type": "helper.translate",
      "key": "label-image"
    }
  }
}
```

## Component properties {#properties}

| Name                                     | Type                                                                             | Description                                                                    |
| ---------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "helper.translate"                                                               | <p>Set component type</p>                                                      |
| `key`<span style="color: red">\*</span>  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>The key for a text property that you will translate to other languages.</p> |
