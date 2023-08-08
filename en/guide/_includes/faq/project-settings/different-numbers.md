{% cut "How do I use different numbers of task response options for different questions?" %}

Use [concatenation](../../../../guide/concepts/t-components/helpers.md#concat), for example:

```html
{{field type="checkbox" name=(concat "result." @index ) label=(concat "checkbox –
          " @index) size="L"}}
```

{% endcut %}