# How to use JavaScript extensions

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in [Template Builder](../../template-builder/index.md).

{% endnote %}

All aspects of the task's [lifecycle](#lifecycle) are controlled by three JavaScript classes:

- The [Assignment](js/assignment.md) class manages [task](../../glossary.md#task) progress, processes the [task suite](../../glossary.md#task-suite) commands for sending responses, skipping or pausing tasks, and more. It also creates an instance of the [TaskSuite](js/tasksuite.md) class.

- [TaskSuite](js/tasksuite.md) is a “wrapper class” for the [task suite](../../glossary.md#task-suite) interface. You can redefine this class, like if you need to display a shared element on the page.

- The [Task](js/task.md) class is responsible for rendering and validating an individual task. Typically, you should extend this class if a task needs to have non-standard behavior.

You can use [services](js/services.md) for more nuanced needs like subscribing to keypress events or getting the Toloker's GPS coordinates.

## Lifecycle of a task {#lifecycle}

When a Toloker starts a task, their workspace is initialized in an iframe. A messaging channel is created between the Toloka head page and the iframe. First, a list of tasks is requested and an [`Assignment`](js/assignment.md) instance is created. Then the received list is passed to the [`TaskSuite`](js/tasksuite.md) class. It creates an instance of the [`Task`](js/task.md) class for each task.

### Rendering

To render the task suite, the [`render()`](js/tasksuite.md#render) method of the `TaskSuite` class is called. This method calls the [`render()`](js/task.md#render) method of the `Task` class for each task and collects the created DOM tree components in a single list.

Here you can change the rendering of tasks and task suites.

### Response validation

When the Toloker clicks **Send**, the [`TaskSuite.validate(solutions)`](js/tasksuite.md#validate) method is called to validate ther Toloker's responses. It calls the [`Task.validate (solutions)`](js/task.md#validate) method for each task and returns errors.

Here you can make an additional review of the Toloker's responses.

### Removal

When the Toloker has finished all tasks on the page or [skipped it](pool_statistic-pool.md#skipped-tasks), the [`destroy()`](js/tasksuite.md#destroy) method of the `TaskSuite` class is called. It calls the [`destroy()`](js/task.md#destroy) method of the `Task` class for each task. These methods free up resources and remove the services and event handlers associated with tasks.

## Class inheritance {#inherit}

To keep the code from looking heavy, use the following function for class inheritance and redefinition:

```javascript
function extend(ParentClass, constructorFunction, prototypeHash) {
    constructorFunction = constructorFunction || function() {};
    prototypeHash = prototypeHash || {};
    if (ParentClass) {
        constructorFunction.prototype = Object.create(ParentClass.prototype);
    }
    for (var i in prototypeHash) {
        constructorFunction.prototype[i] = prototypeHash[i];
    }
    return constructorFunction;
}
```

Function call:

```javascript
var ChildClass = extend(ParentClass, function() {
    ParentClass.call(this);
}, {
    method: function() {}
})
```

## Data types {#data-spec-adv}

The `Task` object is the task to perform.

```json
{
    "id": <string>,
    "input_values": {
        "<ID of the field with input data>": <value>,
        …
     }
}
```

#|
||**Key**|**Value**||
||`id` | Task ID.||
||`input_values` | Task input data in the format `"<field ID>":"<field value>"`.

Example:

```json
"input_values": {
    "image": "http://images.com/1.png"
}
```
||
|#

The `Solution` object is the Toloker's response in the task.

```json
{
    "task_id": <string>,
    "output_values": {
        "<input field id>": <value>,
        …
    }
}
```

#|
||**Key**|**Value**||
||`task_id` | Task ID.||
||`output_values` | Responses in the format `"<input field ID>":"<value>"`.

Example:

```json
"outputValues": {
    "colour": "white",
    "comment": "So white"
}
```
||
|#

The `SolutionValidationError` object is a validation error for the Toloker's response.

```json
{
    "task_id": string,
    "errors": {
        "<input field ID>": {
            "code": "<error code>",
            "message": "<string>"
        },
        …
    }
}
```

#|
||**Key**|**Value**||
||`task_id` | Task ID.||
||`errors` | Errors in the format: `"<field ID>": {code: "<error code>", message: "<error message>"}`.

Example:

```json
"errors": {
    "colour": {
        "code": "REQUIRED",
        "message": "Required field"
    }
}
```

||
|#

## See also {#see-also}

- [{#T}](spec.md)

{% include [contact-support](../_includes/contact-support.md) %}