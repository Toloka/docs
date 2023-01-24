# Survey

For this type of project, you can use the **Customer survey** preset. It has pre-configured validation and task layout.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/ZbXJ-8Hb3ttFey)

{% cut "Components used in the example" %}

- [field.radio-group](../reference/field.radio-group.md): For selecting one answer option.
- [field.checkbox-group](../reference/field.checkbox-group.md): For selecting one or more answer options.
- [field.text](../reference/field.text.md): For entering a single line of text.
- [condition.required](../reference/condition.required.md): Checks if at least one option is selected.
- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task layout.

{% endcut %}

## What else can be configured {#examples}

- To let Tolokers enter long texts, replace the [field.textarea](../reference/field.textarea.md) component with [field.text](../reference/field.text.md).

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/UgcP8H3C3ttFfQ)

- The [field.button-radio-group](../reference/field.button-radio-group.md) component adds buttons for selecting answers. It's better to use buttons if the question has 2–4 short answer options. If there are more answer options, it's better to use [field.radio-group](../reference/field.radio-group.md).

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/uBROpMd23ttFfo)

If this preset doesn't meet your needs, see other examples in this section.

## Group questions together {#add-group-divider}

Ways to group questions:

{% list tabs %}

- Frame

  Use the [view.group](../reference/view.group.md) component to put a frame around a group of questions.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/T7C0zkFC3ttFgR)

- Horizontal separator

  Use the [view.divider](../reference/view.divider.md) component to add a horizontal separator.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/DH1KPwxf3ttFgy)

{% endlist %}

## Add buttons and dependent answer options {#add-buttons-radio}

The [helper.switch](../reference/helper.switch.md) component displays an interface element after a  specific response is selected. In the example, clicking one of the buttons opens a list of options.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/BsloBpMt3ttFhY)

## See also {#see-also}

- [Tutorials — survey with Toloka template](../../guide/tutorials/questionnaire-toloka.md)

{% include [contact-support](../_includes/contact-support.md) %}