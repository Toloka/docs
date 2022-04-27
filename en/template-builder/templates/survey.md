# Survey

For this type of project, you can use the  template (). It has pre-configured validation and task layout.

#### Components used in the example

- [field.radio-group](../reference/field.radio-group.md): For selecting one answer option.
- [field.checkbox-group](../reference/field.checkbox-group.md): For selecting one or more answer options.
- [field.text](../reference/field.text.md): For entering a single line of text.
- [condition.required](../reference/condition.required.md): Checks if at least one option is selected.
- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task layout.


## What else can be configured {#examples}

- To let users enter long texts, replace the [field.textarea](../reference/field.textarea.md) component with [field.text](../reference/field.text.md).

- The [field.button-radio-group](../reference/field.button-radio-group.md) component adds buttons for selecting answers. It's better to use buttons if the question has 2-4 short answer options. If there are more answer options, it's better to use [field.radio-group](../reference/field.radio-group.md).


If this  template doesn't meet your needs, see other examples in this section.


## Group questions together {#add-group-divider}

Ways to group questions:

#### Frame

Use the [view.group](../reference/view.group.md) component to put a frame around a group of questions.

#### Horizontal separator

Use the [view.divider](../reference/view.divider.md) component to add a horizontal separator.


## Add buttons and dependent answer options {#add-buttons-radio}

The [helper.switch](../reference/helper.switch.md) component displays an interface element after a  specific response is selected. In the example, clicking one of the buttons opens a list of options.


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
