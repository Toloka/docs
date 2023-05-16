{% cut "How do I display the text in the input field as in the source (with the HTML tags)?" %}

To display the text in the input field with HTML tags, use the `<pre>` tag. For example:`<pre>not_var{{text}}</pre>`.

In this case, the text is rendered as is, in one scrollable line. To remove the scroll and avoid stretching the task card, add the following CSS to the block:

```css
.task {
  max-width: 800px;
}

pre {
  white-space: pre-wrap;
}
```

{% endcut %}