# Services for specific purposes

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in [Template Builder](../../../template-builder/index.md).

{% endnote %}

## Geolocation {#geolocation}

Gets the GPS coordinates of the Toloker, if they are available. In the [TaskSuite](tasksuite.md) and [Task](task.md) classes, it is available via `this.geolocation`.

Methods:

### getCurrentPosition(success, error, options) {#getcurrentposition}

Duplicates the [navigator.geolocation.getCurrentPosition()](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition) functionality.

### watchPosition(success, error, options) {#watchposition}

Duplicates the [navigator.geolocation.watchPosition()](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition) functionality.

## Storage {#storage}

Storing data on the client. In the [TaskSuite](tasksuite.md) and [Task](task.md) classes, it is available via `this.storage`.

Methods:

### setItem(key, value, expiration) {#setitem}

Save the value under a specific key. Parameters:

- `key`

- `value` — Can be any type. Serialized by casting to a string.

- `expiration` — Storage date (`Date` or `number`). The default value is 24 hours.

### getItem(key) {#getitem}

Returns the value by key.

### removeItem(key) {#removeitem}

Deletes a value by key.

## TaskInterface {#taskinterface}

[Task interface](../../../glossary.md#task-interface). In the [TaskSuite](tasksuite.md) and [Task](task.md) classes, it is available via `this.taskInterface`.

Methods:

### showInstructionPopup() {#showinstructionpopup}

Opens the [instructions](../instruction.md).

### toggleFullscreen() {#togglefullscreen}

Expands the task to full screen if it is collapsed. Otherwise minimizes the task.

## Hotkey {#hotkey}

Lets you subscribe to pressed keys. In the [TaskSuite](tasksuite.md) and [Task](task.md) classes, it is available via `this.hotkey`.

Method:

### on(event, handler, context) {#on}

Subscribes the passed handler to a specific event. Tracks events from the `event` parameter. Parameters:

- `event`:

    - `enter` — The “enter” key.

    - `esc` — The “escape” key.

    - `arrow-left`, `arrow-right`, `arrow-up`, `arrow-down` — Arrows.

    - `key` — Alphanumeric keys. Handler (the `handler` parameter) gets the pressed key as the first argument.

- `handler` — The event handler.

- `context` — `this` for the handler.

### reset() {#reset}

Cancels all previously made links and reinitializes the service.

## ClientInfo {#clientInfo}

Gets information about the device on which tasks are performed. In the [TaskSuite](tasksuite.md) and [Task](task.md) classes, it is available via `this.clientInfo`.

Method:

### getClientInfo() {#getclientinfo}

Returns information about the device if the Toloker is using the mobile app:

- `deviceModel` — Mobile device model.

{% include [contact-support](../../_includes/contact-support.md) %}