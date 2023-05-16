{% cut "In the “Side-by-side image comparison” template, where do I specify a proxy for the task interface to create a task with three image options?" %}

The “Side-by-side image comparison” template uses a component rather than an HTML tag. This means that you should enclose your proxy in curly brackets like this [example](../../../../guide/concepts/t-components/img.md): `{{img src=(proxy image)}}`.

{% endcut %}