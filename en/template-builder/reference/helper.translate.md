# helper.translate

Component for translating interface elements to other languages. More details in [Translating the task interface](../../guide/concepts/project-languages#interface-translate).

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

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "helper.translate" | Set component type ||
|| `key`<span style="color: red">\*</span> | _string_ | The key for a text property that you will translate to other languages. ||
|#
