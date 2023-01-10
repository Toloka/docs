{% cut "How can I do it in JS so that if the checkbox is selected, the link is not required, but if the link is inserted, the checkbox is cleared?" %}

1. See how this is implemented in the “[Mining business contacts](../../../../guide/tutorials/internet-search.md)” template.

1. To solve the second problem, you can add another validation like this:

    {% if locale == "en-com" %}

    ```javascript
    if (solution.output_values.url && solution.output_values.check) {return {task_id:
    this.getTask().id,errors: {'url': {code: ''Insert a link or check the box if the site doesn't exist'}}}}
    ```

    {% endif %}

{% endcut %}