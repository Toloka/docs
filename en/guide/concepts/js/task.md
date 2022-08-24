# Task class

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in [Template Builder]({{ tb-quickstart }}).

{% endnote %}


The `Task` base class is responsible for the [task interface](../../../glossary.md#task-interface-ru). This class is available in the global variable `window.TolokaTask`.

Methods:

#### blur()

Implements the logic for removing the focus from the task and calls the [`onBlur()`](#onBlur) method.

#### constructor(options)

The [task UI](../spec.md) constructor. Parameters:
- `options.task` — The [Task](../spec-advanced.md#obj-task) task model.
- `options.specs` — Parameters for [input and output data](../../../glossary.md#input-output-data-ru) and the task interface. See the [`task_spec`](https://tech.yandex.ru/toloka/doc/concepts/project-docpage/) object format.
- `options.workspaceOptions` — [Sandbox](../../../glossary.md#sandbox-ru) initialization parameters {{isReadOnly: boolean}}

#### destroy()
Releases resources, services, and event handlers used in the global space. Calls [`onDestroy()`](#onDestroy).
#### focus()

Implements the logic for setting the focus on the task by calling the `[onFocus()](#onFocus)` method.

#### getAssignment()

Returns a link to an instance of the `TolokaAssignment` class. After that, you can access all its properties and methods.

#### Example

```javascript
// skip current assignment
this.getAssignment().skip()
```

#### getDOMElement()

Returns the DOM element of the task.

#### getOptions()

Returns the parameters passed to the `constructor()` method.

#### getProxyUrl(path)

Returns the full URL for accessing data on the proxy server. Parameter:
- `path` — Relative file path.

#### getSavedState()

Returns the saved state of the task (object).

Retrieves the saved state of the task from the browser's local storage using the `TASK_STATE:{assignmentId}:{taskId}` key.

#### getSolution()

Returns the [`Solution`](../spec-advanced.md#obj-solution) task responses.

#### getStyleDOMElement()

Returns a DOM element for task styles that is added to `document.head` when rendering.

#### getTask()

Returns the [`Task`](../spec-advanced.md#obj-task) task model.

#### getTemplateData()

Returns the object received by the template engine before compiling the task template.

The method is available in toloka-handlebars-templates. It returns a set of fields and their values passed to the task input: `return this.getTask().input_values`.

The method allows you to process the existing values or pass new custom parameters to the template engine. For example, you can pass strings to localize a template and use the same project for Russian-speaking and English-speaking users.

#### Example

```javascript
// if the Toloker completes the assignment under iOS, we show additional layout
getTemplateData: function() {
    let data = TolokaHandlebarsTask.prototype.getTemplateData.call(this),
        userAgent = navigator.userAgent || navigator.vendor || window.opera;


    if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
        data.ios = true;
    }

    return data;
}
```

#### getWorkspaceOptions()

Returns the sandbox initialization parameters passed to the `constructor()` method.

#### hideTaskError()

Hides a global error (only if the toloka-handlebars-templates library is connected).

#### id

Contains the current task's `id`.

#### Example

```javascript
let myId = this.getTask().id
```

#### onBlur()
Called after removing the focus.
#### onDestroy()
Called after the task is destroyed (`[destroy()](#destroy)`). The best method for releasing memory, deleting global event handlers and DOM elements, and so on.
#### onFocus()
Called after setting the focus.
#### onKey(key)
Passes the pressed key. Parameter:
- `key` — Alphanumeric character pressed on the keyboard. Can be used as a shortcut.

#### onPause()
Called after the task is put on pause.
#### onRender()
Called after the task is rendered (`[render()](#render)`). All manipulations with the DOM element of a task should be performed here.
#### onResume(savedState)
Called after the task is resumed.
#### onValidationFail(errors)
Called when the Toloker's response validation fails. Parameter:
- `errors` — Validation errors in the Toloker's response `[SolutionValidationError](../spec-advanced.md#obj-solutionvalidationerror)`.

#### pause()

Pauses task completion. Saves the intermediate state of the task in the browser's local storage (`saveState`) and calls the `onPause` method.

#### proxy(path, options)

Creates a GET or POST request via proxy.

Parameters:

- `path` — Request path (string).
- `options` — Request parameters (object). Read more in [Jquery Ajax](https://api.jquery.com/jquery.ajax/#jQuery-ajax-settings).

Returns a `promise` object.

{% note info %}

Some features (such as timeouts or custom headers) are not supported.

{% endnote %}


#### Example

```javascript
// need to find user logins which start with 'jones' and 'smith' (not more than 10 of each instance)
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

Forms the DOM representation of the task interface. Calls `[onRender()](#onRender)`. Returns `this`.

#### resume()

Resumes task completion. Retrieves the saved state of the task from the browser's local storage. Restores responses from it and re-executes the requests in the file and webview services that were not completed before. Calls `onResume`.

#### saveState()

Checks `assignmentId`to make sure that the task is working in Toloker mode and not in preview mode. Receives a set of responses and unprocessed requests in the file and webview services. Saves them in the browser's local storage with the `TASK_STATE:{assignmentId}:{taskId}` key using the storage service.

#### setSolution(solution)

Sets the responses. Parameter:
- `solution` — The Toloker's response to the task (`[Solution](../spec-advanced.md#obj-solution)`).

#### setSolutionOutputValue(fieldName, value)

Writes the required value in the specified field. Parameters:

- `fieldName` — A field (string) in the output specification, to which the value is passed.
- `value` — The value of the type set for `fieldName` in the project specification.

#### setSolutionOutputValues(outputValues)

Updates the output specification by writing the passed object with responses in it. Calls `saveState` to save intermediate results in the browser's local storage. Parameter:

- `outputValues` — Object with responses.

#### showTaskError(message)

Forcibly shows a global error in the task (only if the toloka-handlebars-templates library is connected). Parameters:

- `message` — Error text (string).

#### template(data)

Template engine for the task. In the task's [HTML interface](../spec.md), it replaces occurrences such as `${fieldX}` with the corresponding value and the `fieldX` key from the `data` parameter. Returns the task's HTML interface as a string. Parameter:
- `data` — Object with data to insert in the template.

#### validate(solution)

Validates responses according to output data parameters. Returns [`SolutionValidationError`](../spec-advanced.md#obj-solutionvalidationerror) if the responses are invalid, otherwise `null`. Parameter:
- `solution` — The Toloker's response to the task. If omitted, the current one is used ([`getSolution()`](#getSolution)).

{% include [contact-support](../../_includes/contact-support-help.md) %}