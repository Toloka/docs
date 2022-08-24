# TaskSuite class

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in [Template Builder]({{ tb-quickstart }}).

{% endnote %}


<q>Wrapper class</q> for [task suites](../../../glossary.md#task-page-ru) creates instances of task classes. You can redefine this class (for example, if you need to display a shared element on the page with tasks or get more control over tasks, like custom keyboard shortcuts).

The main purpose of the `TaskSuite` class is to render tasks on the page (`[render()](#render)`). It is also used for collecting responses (`[getSolutions()](#getSolutions)`), validating them (`[validate(solutions)](#validate)`) nd managing keyboard shortcuts ([`focusNextTask()`](#focusNextTask), [`onKey(key)`](#onKey), and so on).

The base class for `TaskSuite` is available in the `window.TolokaTaskSuite` global variable.

Methods:

#### constructor(options)

Basic task suite class constructor. Parameters:
- `options.task` — Array of [Task](../spec-advanced.md#obj-task) models.
- `options.specs` — Parameters for [input and output data](../../../glossary.md#input-output-data-ru) and the task interface. See the [`task_spec`](https://tech.yandex.ru/toloka/doc/concepts/project-docpage/) object format.
- `options.assignmentId` — IDs of tasks on the page.
- `options.workspaceOptions` — [Sandbox](../../../glossary.md#sandbox-ru) initialization parameters {{isReadOnly: boolean}}
- `options.TaskClass` — Array of classes for the task you create.
- `options.solutions` — Array of responses [`Solution`](../spec-advanced.md#obj-solution). Can be empty.

#### destroy()
Destroys all tasks on the page. Releases resources, services, and event handlers used in the global space. Calls [`onDestroy()`](#onDestroy).
#### focusNextTask()
Sets the focus on the next task.
#### focusPreviousTask()
Sets the focus on the previous task.
#### focusTask(index)
Sets the focus on the task by the index. Parameter:
- `index` — Task index on the page.

#### getAssignment()

Returns a link to an instance of the `TolokaAssignment` class. After that, you can use all the properties and methods of that class instance.

#### Example

```javascript
// skip current assignment
this.getAssignment().skip();
```

#### getDOMElement()

Returns the DOM element of the page (it is empty before rendering, and after rendering it is initialized and contains the interface).

#### getFocusedTask()

Returns a link to the active task. Gets the index of the active task from a private property `_focusedTaskIndex` and returns a link to that task using `[getTasks()](#getTasks)`.

#### Example

```javascript
// remove the class .some_class from all elements of the active task
let elements = Array.from(this.getFocusedTask().getDOMElement().querySelectorAll('.some_class'));
elements.forEach(el => el.classList.remove('some_class'));
```

#### getOptions()

Returns the parameters passed to the `[constructor()](#constructor)` method.

#### getProxyUrl(path)

Returns the full URL for accessing data on the [proxy server](../prepare-data.md). Parameter:
- `path` — Relative file path.

#### getSolutions()

Returns an array of [`Solution`](../spec-advanced.md#obj-solution) responses.

#### getStyleDOMElement()

Returns the DOM element of the page styles.

#### getTasks()

Returns an array of `[Task](../spec-advanced.md#obj-task)` initialized task models.

#### getTasksDOMElement()

Returns the DOM element of the task suite (`div.task-suite`). If the DOM element is missing, the method creates it.

#### getTasksIndexed()
Returns tasks indexed by their IDs: `"<taskId>": [Task](../spec-advanced.md#obj-task), …`
#### getWorkspaceOptions()

Returns the sandbox initialization parameters passed to the `[constructor()](#constructor)` method.

#### initHotkeys()
Hotkey handler initializer:
- Sets the focus to the previous task when the left arrow or up arrow is pressed.
- Sets the focus to the next task when the right arrow or down arrow is pressed.
- Passes the pressed keys to the active task.
- Sets the focus on the first task.

#### onDestroy()
A method you can redefine to execute your code when a task suite is deleted. Called after the page is destroyed (`[destroy()](#destroy)`). The best method for releasing memory, deleting global event handlers and DOM elements, and so on.
#### onKey(key)
Passes the pressed key to the active task.
#### onPause()
A method you can redefine to execute your code when a task suite stops working.
#### onRender()
A method you can redefine to execute your code when rendering a task suite. Called after page rendering (`[render()](#render)`). All manipulations with the DOM element of a task should be performed here.
#### onResume()
A method you can redefine to execute your code when a task suite resumes working.
#### onValidationFail(errors)
Called if the validation failed. Contains error descriptions in the parameter. Parameter:
- `errors` — Array of errors [`SolutionValidationError`](../spec-advanced.md#obj-solutionvalidationerror).

#### pause()
Calls the `pause()` method for each task in the suite. It also calls the `[onPause()](#onPause)` method.
#### proxy(path, options)

Makes a GET/POST request via proxy. Returns the result of the request as an object. Parameters:
- `Path`: request path.
- `Options`: request parameters (see Jquery Ajax [parameter description](https://api.jquery.com/jquery.ajax/#jQuery-ajax-settings)).

{% note warning %}

Some features (such as timeouts or custom headers) are not supported.

{% endnote %}


#### Example

```javascript
// we need to find usernames starting with 'jones' and 'smith' (no more than 10 of each)
// we make two POST requests to the search service
// then wait for results

let promises = [],
patterns = ['jones*', 'smith*'];

patterns.forEach(pattern => promises.push(Promise.resolve(this.proxy('myproxy/search', {
   type: 'POST',
   contentType: 'application/json',
   dataType: 'json',
   data: JSON.stringify({
      query: pattern,
      limit: 10
   }),
   processData: false
}))));

Promise.all(promises)
.then(results => console.log(results))
.catch(error => console.error(error));
```

#### render()

Creates a DOM representation of the task suite: renders all tasks in the task suite. Calls [`render()` in the `Task`](task.md#render) class for each task. Calls `[onRender()](#onRender)`. Returns `this`.

#### validate(solutions)

Validates responses according to output data parameters. Returns a `promise` object with an array of [`SolutionValidationError`](../spec-advanced.md#obj-solutionvalidationerror) errors if the responses are incorrect, or `null`. Parameter:
- `solutions` — Array of the Toloker's task responses. If omitted, the current values are used ([`getSolutions()`](#getSolutions)).

{% include [contact-support](../../_includes/contact-support-new.md) %}