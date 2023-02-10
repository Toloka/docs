# Task class

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in [Template Builder](../../../template-builder/index.md).

{% endnote %}

The `Task` base class is responsible for the [task interface](../../../glossary.md#task-interface). This class is available in the global variable `window.TolokaTask`.

Methods:

### blur() {#blur}

Implements the logic for removing the focus from the task and calls the [onBlur()](#onblur) method.

### constructor(options) {#constructor}

The [task UI](../spec.md) constructor.

Parameters:

- `options.task` — The [Task](../spec-advanced.md#obj-task) model.

- `options.specs` — Parameters for [input and output data](../../../glossary.md#input-output-data) and the task interface.

- `options.workspaceOptions` — Toloker's workspace initialization parameters.

### destroy() {#destroy}

Releases resources, services, and event handlers used in the global space. Calls [onDestroy()](#ondestroy).

### focus() {#focus}

Implements the logic for setting the focus on the task by calling the [onFocus()](#onfocus) method.

### getAssignment() {#getassignment}

Returns a link to an instance of the `TolokaAssignment` class. After that, you can access all its properties and methods.

{% cut "Example" %}

```javascript
// skip current assignment
this.getAssignment().skip()
```

{% endcut %}

### getDOMElement() {#getdomeelement}

Returns the DOM element of the task.

### getOptions() {#getoptions}

Returns an object with a set of parameters passed to the [constructor()](#constructor) method during initialization.

{% cut "Example" %}

```javascript
// getting specifications for all required fields:
let outputSpec = this.getOptions().specs.output_spec,
     requiredFields = Object.keys(outputSpec)
                            .filter(key => outputSpec[key].required)
                            .reduce((item, key) => (item[key] = outputSpec[key], item), {});
```

{% endcut %}

### getProxyUrl(path) {#getproxyurl}

Returns a complete URL to access the data on the proxy server. Parameter:

- `path` — the relative path to the file.

### getSavedState() {#getsavedstate}

Returns the saved state of the task (object).

Retrieves the saved state of the task from the browser's local storage using the `TASK_STATE:{assignmentId}:{taskId}` key.

### getSolution() {#getsolution}

Returns the [Solution](../spec-advanced.md#obj-solution) task responses.

### getStyleDOMElement() {#getstyledomeelement}

Returns a DOM element for task styles that is added to `document.head` when rendering.

### getTask() {#gettask}

Returns the [Task](../spec-advanced.md#obj-task) task model.

### getTemplateData() {#gettemplatedata}

Returns the object received by the template engine before compiling the task template.

The method is available in toloka-handlebars-templates. It returns a set of fields and their values passed to the task input: `return this.getTask().input_values`.

The method allows you to process the existing values or pass new custom parameters to the template engine. For example, you can pass strings for localizing a template and use the same project for English-speaking and Spanish-speaking Tolokers.

{% cut "Example" %}

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

{% endcut %}

### getWorkspaceOptions() {#getworkspaceoptions}

Returns the Toloker's workspace initialization parameters passed to the `constructor()` method.

### hideTaskError() {#hidetaskerror}

Hides a global error (only if the toloka-handlebars-templates library is connected).

### id {#id}

Contains the current task's `id`.

{% cut "Example" %}

```javascript
let myId = this.getTask().id
```

{% endcut %}

### onBlur() {#onblur}

Called after removing the focus.

### onDestroy() {#ondestroy}

Called after the task is destroyed ([destroy()](#destroy)). The best method for releasing memory, deleting global event handlers and DOM elements, and so on.

### onFocus() {#onfocus}

Called after setting the focus.

### onKey(key) {#onkey}

Passes the pressed key. Parameter:

- `key` — Alphanumeric character pressed on the keyboard. Can be used as a shortcut.

### onPause() {#onpause}

Called after the task is put on pause.

### onRender() {#onrender}

Called after the task is rendered ([render()](#render)). All manipulations with the DOM element of a task should be performed here.

### onResume(savedState) {#onresume}

Called after the task is resumed.

### onValidationFail(errors) {#onvalidationfail}

Called when the Toloker's response validation fails. Parameter:

- `errors` — Validation errors in the Toloker's response [SolutionValidationError](../spec-advanced.md#obj-solutionvalidationerror).

### pause() {#pause}

Pauses task completion. Saves the intermediate state of the task in the browser's local storage (`saveState`) and calls the `onPause` method.

### proxy(path, options) {#proxy}

Makes a GET or POST request through a proxy.

Parameters:

- `path` — the path for the request (string).

- `options` — the request parameters (object). More information in the [Jquery Ajax](https://api.jquery.com/jquery.ajax/#jquery-ajax-settings) parameter description.

Returns the `promise` object.

{% note alert %}

Some features are not supported (for example, timeouts and custom headers).

{% endnote %}

{% cut "Example" %}

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

{% endcut %}

### render() {#render}

Forms the DOM representation of the task interface. Calls [onRender()](#onrender). Returns `this`.

### resume() {#resume}

Resumes task completion. Retrieves the saved state of the task from the browser's local storage. Restores responses from it and re-executes the requests in the file and webview services that were not completed before. Calls `onResume`.

### saveState() {#savestate}

Checks `assignmentId`to make sure that the task is working in Toloker mode and not in preview mode. Receives a set of responses and unprocessed requests in the file and webview services. Saves them in the browser's local storage with the `TASK_STATE:{assignmentId}:{taskId}` key using the storage service.

### setSolution(solution) {#setsolution}

Sets the responses. Parameter:

- `solution` — The Toloker's response to the task ([Solution](../spec-advanced.md#obj-solution)).

### setSolutionOutputValue(fieldName, value) {#setsolutionoutputvalue}

Writes the required value in the specified field. Parameters:

- `fieldName` — A field (string) in the output specification, to which the value is passed.

- `value` — The value of the type set for `fieldName` in the project specification.

### setSolutionOutputValues(outputValues) {#setsolutionoutputvalues}

Updates the output specification by writing the passed object with responses in it. Calls `saveState` to save intermediate results in the browser's local storage. Parameter:

- `outputValues` — Object with responses.

### showTaskError(message) {#showtaskerror}

Forcibly shows a global error in the task (only if the toloka-handlebars-templates library is connected). Parameters:

- `message` — Error text (string).

### template(data) {#template}

Template engine for the task. In the task's [HTML interface](../spec.md), it replaces occurrences such as `${fieldX}` with the corresponding value and the `fieldX` key from the `data` parameter. Returns the task's HTML interface as a string. Parameter:

- `data` — Object with data to insert in the template.

### validate(solution) {#validate}

Validates responses according to output data parameters. Returns [SolutionValidationError](../spec-advanced.md#obj-solutionvalidationerror) if the responses are invalid, otherwise `null`. Parameter:

- `solution` — The Toloker's response to the task. If omitted, the current one is used ([getSolution()](#getsolution)).

{% include [contact-support](../../_includes/contact-support.md) %}