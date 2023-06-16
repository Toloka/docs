{% cut "How do I pass the value of the input variable to the “Button with click validation”?" %}

Specify the name of the input field where you pass the link, without the brackets:

```html
{{field type="button-clicked" name="ads" label="Click me" href=name_escape action=true}}
```

{% endcut %}