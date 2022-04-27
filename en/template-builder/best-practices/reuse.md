# Reuse code

If you need to insert the same or similar code snippets many times, reuse them. This helps make your configuration shorter and makes it easier for you to edit duplicate chunks of code.

## $ref to any snippet inside the configuration {#ref}

You can insert a code snippet from another part of the configuration anywhere inside the configuration. To do this, use the structure `{ "$ref": "path.to.element" }`.

This is useful when you need to insert the same snippet at multiple places in your code. For example, if you need to run the same action using multiple buttons, put this action in a variable and call it using `$ref`.

{% note info %}

Store your reused code using variables in `vars`. Otherwise, you may need to change the path in the `$ref` property when you edit the configuration.

{% endnote %}

The path in the `$ref` structure starts from the root. Array elements start from zero. Example:

{% note info %}

Some components have properties with the type
{% cut "ref" %}

A pointer to a visual component using the construction `{ "$ref": "path.to.element" }`.

.

{% note info %}

The list of components you can link to might be limited. For example, [action.play-pause](../reference/action.play-pause.md) works only with the components that support audio or video playback.

{% endnote %}

{% endcut %}

 or something similar, like [action.open-close](../reference/action.open-close.md). In such cases, that property is a pointer to a specific interface element.

{% endnote %}


## helper.transform {#helper-transform}

The [helper.transform](../reference/helper.transform.md) component lets you convert one array into another. This is useful if you don't know the number of elements in the array, or the array is very big.

**Examples:**

- .
- .


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
