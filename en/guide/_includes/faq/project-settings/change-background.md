{% cut "How do I change the task background from the standard white color to a different color?" %}

[Use CSS](../../../concepts/spec.md#css) to specify the color for the `.task` or `.task-suite` element. For example, to use a black background:

```css
.task-suite {
    background-color: #000000;
}
.task {
    background-color: #000000;
}
```

You can also assign a class to the interface block with the image and set the background for this block only.

{% endcut %}