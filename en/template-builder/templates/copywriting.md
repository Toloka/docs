# Copywriting

For this type of project, you can use the **Generating product descriptions** preset. It has pre-configured validation and task layout.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/vgh-fVxH3ttFJY)

{% cut "Components used in the example" %}

- [view.image](../reference/view.image.md): Image.
- [layout.columns](../reference/layout.columns.md): Places the image in a separate column to the left of other interface elements.
- [view.text](../reference/view.text.md): Shows the text from the task input data.
- [field.textarea](../reference/field.textarea.md): Text input field.
- [condition.required](../reference/condition.required.md): Checks if the text field is filled in.
- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task width.

{% endcut %}

## What else can be configured {#add-more}

- To set the desired text length, use the [condition.schema](../reference/condition.schema.md) component instead of [condition.required](../reference/condition.required.md). It won't let a Toloker submit a response if the text they entered is longer or shorter than specified.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/Mnz9jbRH3ttFKh)

- For short single-line text, use the [field.text](../reference/field.text.md) component instead of [field.textarea](../reference/field.textarea.md).

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/oBN6epCs3ttFLK)

- If a Toloker needs to search for information online to complete the task, add the [helper.search-query](../reference/helper.search-query.md) component. The search query can be put together from words taken from the input data.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/YKwsyb2h3ttFMH)

If this preset doesn't meet your needs, see other examples in this section.

## Example without an image {#text-answer-only}

A simplified example without an image or columns It can be used for tasks that don't require visual display, such as translations.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/RYB77BTQ3ttFMj)

## Multiple columns {#several-columns}

To compare two texts, place them in adjacent columns using the [layout.columns](../reference/layout.columns.md) component. It allows you to set the column width and vertical alignment.

The [view.group](../reference/view.group.md) component adds frames around the texts to visually separate them from each other and make them easier to read.

The third column in the example contains two input fields for Tolokers to write their text.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/EtNLEAun3ttFNK)

## Show hidden field {#checkbox-showing-text}

This example is suitable for text search, such as for finding errors in a text. If a Toloker finds mistakes, selecting the relevant option opens the text input field.

Decide how you want to display the options: with radio buttons, regular buttons, or a checkbox.

{% list tabs %}

- Radio buttons

  Use the [field.radio-group](../reference/field.radio-group.md) component.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/cCnptYRg3ttFNe)

- Buttons

  Use the [field.button-radio-group](../reference/field.button-radio-group.md) component.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/qXZ539523ttFPL)

- Checkbox

  Use the [field.checkbox](../reference/field.checkbox.md) component.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/-Zd32wl73ttFQ3)

{% endlist %}

## A Toloker adds input fields {#dynamic-field-add}

This is a complex example that consists of four main parts:
- [view.image](../reference/view.image.md): Image.
- [field.radio-group](../reference/field.radio-group.md): Response selection options.
- [field.text](../reference/field.text.md): The text input field.
- [field.list](../reference/field.list.md): A button that adds new text input fields.

What's unique about this example is that a Toloker can add and remove text input fields.

In addition, the example checks that each line has at least three characters, including letters and spaces. The condition is implemented using [condition.schema](../reference/condition.schema.md).

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/mus2SrsY3ttFQR)

{% include [contact-support](../_includes/contact-support.md) %}