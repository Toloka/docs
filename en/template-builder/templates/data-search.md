# Searching for product characteristics

For this type of project, you can use the **Mining business contacts** preset. It has pre-configured validation and task layout. In this preset, a Toloker needs to enter the organization's contact information found online.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/Q2O6DQ2L3vvtkR)

{% cut "Components used in the example" %}

- [view.text](../reference/view.text.md): To add text to the task.
- [view.link-group](../reference/view.link-group.md): To group links together.
- [helper.search-query](../reference/helper.search-query.md): To create a search query.
- A combination of [helper.if](../reference/helper.if.md) and [condition.equals](../reference/condition.equals.md): Hides the contact input fields if “No contacts” is selected.
- [field.checkbox](../reference/field.checkbox.md): To add a checkbox.
- [field.phone-number](../reference/field.phone-number.md): To add a phone number input field.
- [field.email](../reference/field.email.md): To add an email input field.
- A combination of [condition.any](../reference/condition.any.md), [condition.required](../reference/condition.required.md), and [condition.equals](../reference/condition.equals.md): For checking that either the “Phone” or “Email” field is filled in, or the “No contacts” option is selected.
- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task layout.

{% endcut %}

## What else can be configured {#examples}

- To let Tolokers enter long texts, add the [field.textarea](../reference/field.textarea.md) field.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/5aKHQEXE3vvu7U)

- To let Tolokers enter numbers, add the [field.number](../reference/field.number.md) field.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/BFMRXUUS3xDkbn)

- To let Tolokers search for files online, add the file selection field [field.file](../reference/field.file.md). For example, use this if they need to upload a photo with a certain object in it.

    In task verification mode, the uploaded images will appear automatically. You can view, rotate, and switch between images.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/2q9TFDoh3xE9PR)

- If a Toloker needs to find and submit a link to a specific page from the website, add the [condition.same-domain](../reference/condition.same-domain.md) component. The component checks that the link is from the required domain.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/sBbrym1_3xE9iw)

If this preset doesn't meet your needs, see other examples in this section.

## Add a field for selecting response options {#add-radio-group}

If a Toloker needs to click on the search link and answer a question, add the [field.radio-group](../reference/field.radio-group.md) field for selecting one of the response options.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/gzohfiIE3vvzbL)

## Add an image and a date input field {#add-image-date}

For example, use this to search for information about an actor by their name and photo.

In this example, the following fields are added:

- [view.image](../reference/view.image.md): Image.
- [field.text](../reference/field.text.md): For entering a short text.
- [field.date](../reference/field.date.md): For entering the date of birth.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/k9H6qX0v3vw22r)

## Divide the task interface into columns {#add-layout-columns}

Another version of the task, in which a Toloker needs to find information about the organization.

In this example, the following fields are added:

- The [layout.columns](../reference/layout.columns.md) component, which allows you to place the task description and the site page inside the [view.iframe](../reference/view.iframe.md) component in two columns.
- [view.text](../reference/view.text.md): The task text.
- [view.link](../reference/view.link.md): A link to the site.
- [field.button-radio-group](../reference/field.button-radio-group.md): Buttons for response options.
- The [condition.schema](../reference/condition.schema.md) component: Checks the format of the entered data (in this case, the INN and OGRN code formats).

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/s5vP6HDb3ttFVB)

## See also {#see-also}

- [Tutorials — searching for product characteristics](../../guide/tutorials/internet-search.md)

{% include [contact-support](../_includes/contact-support.md) %}