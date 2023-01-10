{% cut "How do I add the text from an input variable to a checkbox label?" %}

To pass a `label` in the input data, enter the input field name into the label.

For example, if you have the `asd` input field with the string type, the component would look like: `{{field type="checkbox" name="like" label=asd hotkey="q"}}`.

If you want to pass different label values in different tasks or the number of checkboxes may differ, use [concatenation](../../../../guide/concepts/t-components/helpers.md#concat).

{% endcut %}