# Components for working with text

In this section, we will tell you how to [display text](#insert-text) and [add a text entry field](#field-text). We'll also tell you which components you can use to [change text](#text-transform).

## Display text {#insert-text}

Use the [view.text](../reference/view.text.md) component to display text in the task interface. In the `content` property, insert the required text or specify a component with the [data.*](work-with-data.md) type that returns the text.

{% list tabs %}

- From input data

  To use the text from the input data, use the `data.input` component.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/si0fBVkD3ttB64)

- From output data

  To use the text from the output data, use the `data.output` component.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/si0fBVkD3ttB64)

{% endlist %}

If you want to insert formatted text, see the instructions and samples in the [Text formatting](text-formatting.md) section.

## Add a text entry field {#field-text}

To add a text entry field, use the [field.text](../reference/field.text.md) component for single-line text and [field.textarea](../reference/field.textarea.md) component for multi-line text.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/NuwVOMK_3ttBAz)

## Change text {#text-transform}

To change the text, such as all uppercase letters or insert a variable value, use the following components:

- [helper.text-transform](../reference/helper.text-transform.md): Changes the text case. To transform the text, use the `transformation` property with the appropriate value:
    - `uppercase`: Convert all letters to uppercase.
    - `lowercase`: Convert all letters to lowercase.
    - `capitalize`: Convert the first letter of the text to uppercase and all the subsequent letters to lowercase.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/JVwFEJc13ttBEk)

- [helper.replace](../reference/helper.replace.md): Lets you replace some parts of the string with other strings. To do this, use the `find` property for the replaced text and the `replace` property for the replacing text.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/1BMgNIpL3ttBGm)

- [helper.join](../reference/helper.join.md): Joins multiple strings into one string, separating them with spaces or commas.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/_h--eV2Y3ttBMm)

{% include [contact-support](../_includes/contact-support.md) %}