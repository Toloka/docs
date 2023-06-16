{% cut "How do I enter a list of words line-by-line, display an element for each of them, and save the result to the output array?" %}

Pass an array of strings as the input field. For example, as shown in the screenshot:

![](../../../../guide/_images/troubleshooting/array-each-words.png)

In HTML, use a special [handlebar](../../../concepts/t-components/handlebars.md) to iterate over this field. The code structure will look like this:

```html
{{#each words}}
{{field type="radio" name="result" value=this label=this}}
{{/each}}
```

{% endcut %}