# Text formatted in HTML

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in [Template Builder](../../../template-builder/index.md).

{% endnote %}

To upload a task with formatted text (HTML tags and styles):

1. Add a field of `string` type into the [input data description](../incoming.md). For example:

    ```json
    {
    "html": {
    "type": "string",
    "required": true
    }
    }
    ```

1. In the [task interface](../spec.md) put the name of the input data field in triple curly brackets. For example: `{not_var{{html}}}`.

Before uploading a task, make sure that all quotation marks in the formatted text are [escaped](../pool_csv.md#string).

{% include [contact-support](../../_includes/contact-support-help.md) %}