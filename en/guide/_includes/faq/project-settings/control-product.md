{% cut "How do I create a task where products with similar descriptions are selected for the control product?" %}

Create an additional field in the [input specification](../../../concepts/incoming.md), for example, `my_val` and assign it the string array type to pass the desired list of values to it.

The loop inside the template will look like this:

```html
{{#field type="select" name="result"}}
{{#each ../my_val}}
{{select_item value=this text=this}}
{{/each}}
{{/field}}
```

More information about [specifications](../../../concepts/spec.md).

{% endcut %}