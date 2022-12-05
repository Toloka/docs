# Assignment class

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in [Template Builder](../../../template-builder/index.md).

{% endnote %}

This class manages the task progress, processes the task page commands for sending responses, skipping or pausing tasks, and more. It also creates an instance of the [TaskSuite](tasksuite.md) class.

The `Assignment` base class is available in the `window.TolokaAssignment` global variable

Methods:

#### constructor(options)

Task list base class builder.

Parameters:

- `options.assignment` — `Assignment` task list model.

- `options.specs` — Parameters for [input and output data](../../../glossary.md#input-output-data) and the task interface.

- `options.workspaceOptions` — Toloker's workspace initialization parameters.

#### destroy()

Calls [`TaskSuite.destroy()`](tasksuite.md#destroy), removes all template elements from the DOM, closes the messaging channel, stops hotkey polling and location detection, calls `onDestroy`.

#### initHotkeys()

Hotkey handler initializer:

- Resets all hotkeys ([`hotkeys.reset`](services.md#reset)).

- Calls [`submit()`](#Submit) when the Enter key is pressed.

#### getId()

Returns `assignmentId` as a string or `undefined` if you are debugging the task in preview mode or using pool preview.

#### getOptions()

Returns an object with a set of parameters passed to the `constructor()` method during initialization.

{% cut "Example" %}

```javascript
// getting specifications for all required fields:
let outputSpec = this.getOptions().specs.output_spec,
     requiredFields = Object.keys(outputSpec)
                            .filter(key => outputSpec[key].required)
                            .reduce((item, key) => (item[key] = outputSpec[key], item), {});
```

{% endcut %}

#### getSandboxChannel()

Returns the link to an active messaging channel between the parent page and the task frame. If there is no channel, the method creates it.

{% cut "Example" %}

```javascript
// subscribe to all messages and show them
this.getSandboxChannel().on('*', (name, message) => console.log(message));
// ask the parent page to show task instructions
// there is also a separate service for this TaskInterface
this.getSandboxChannel().triggerOut('task:interface:show:instruction');
```

{% endcut %}

#### getTaskSuite()

Returns a link to a [TaskSuite](tasksuite.md) instance.

#### getTaskSuiteContainer()

Returns `document.body` for the Toloker's workspace.

#### getWorkspaceOptions()

Returns an object with the Toloker's workspace settings.

The most important settings:

- `agent` — The value is `FRONTEND` for full task versions, `ANDROID` for the Android app, and so forth.

- `isReadOnly` — "Read-only" mode flag (for example, for viewing the history of completed tasks).

- `isReviewMode` — Review mode flag (for example, assignment review). This setting and `isReadOnly` are useful if you want to do something like change the template layout in history view mode.

- `language` — A two-letter code of the language selected by the Toloker in Toloka settings. It's useful when you want to create multilingual templates.

- `origin` — Parent page FQDN.

#### pause()

Pauses task execution (for example, upon a `request:assignment:pause` command from the main page), calls `onPause`.

#### provideSolutions(strategy)

Collects answers to all tasks ([`TolokaTaskSuite.getSolutions()`](tasksuite.md#getSolutions)), validates them ([`TolokaTaskSuite.validate()`](tasksuite.md#validate)). If validation is successful, calls `strategy`, otherwise sends an `assignment:validation:fail` request and an object with a list of errors returned by the validator. Parameter:

- `strategy` — A function that sends a message about sending results (`assignment:submit`), a response array, and an `assignmentId` to the parent page.

{% cut "Example" %}

```javascript
provideSolutions(strategy = function(solutions) {
        this.getSandboxChannel().triggerOut('assignment:submit', { solutions, assignmentId: this.getId() });
    }, errorCallback = function(errors) {
        //do nothing by default
    }) {
        const solutions = this.getTaskSuite().getSolutions();

        Promise.resolve(this.getTaskSuite().validate(solutions))
            .then((errors) => {
                if (!errors) {
                    strategy.call(this, solutions);
                } else {
                    this.getSandboxChannel().triggerOut('assignment:validation:fail', errors);
                    errorCallback.call(this, errors);
                }
            });
    }
```

{% endcut %}

#### resume()

Continues task execution, calls `onResume` and [`start`](#Start).

#### skip()

Lets you skip the current task, the same as clicking the **Skip** button.

#### start()

Performs all the necessary actions when starting a task suite — adds the rendered task interface to `document.body`, initializes hotkeys for the entire interface ([`InitHotkeys`](#InitHotkeys)), calls `onStart`.

#### submit

Collects, validates and sends completed tasks by calling [`provideSolutions`](#ProvideSolutions).

{% cut "Example" %}

```javascript
// in some scenarios, you might need to set delayed sending
// in that case, you can programmatically hide the send button in the project settings
// for example, from TolokaTask
this.getDOMElement().querySelector('.my_submit_button').addEventListener('click', (event) => this.getAssignment().submit());
```

{% endcut %}

{% include [contact-support](../../_includes/contact-support.md) %}