{% cut "Why do I see a syntax error when I upload a task where a user has to view an image and write feedback?" %}

The error might occur if the expected input type is URL, but a string is received.

There may be two reasons:

- The input field has the "link" type.

- The pool was created for an outdated project version. It means that the pool was created before you changed the input field type.

{% endcut %}