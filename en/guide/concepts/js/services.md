# Services for specific purposes

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in [Template Builder](../../../template-builder/index.md).

{% endnote %}

## Geolocation {#Geolocation}

Gets the GPS coordinates of the Toloker, if they are available. In `TaskSuite` and `Task`, it is available via `this.geolocation`.

Methods:

#### getCurrentPosition(success, error, options)

Duplicates the [navigator.geolocation.getCurrentPosition()](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition) functionality.
#### watchPosition(success, error, options)

Duplicates the [navigator.geolocation.watchPosition()](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition) functionality.

## Storage {#Storage}

Storing data on the client. In `TaskSuite` and `Task`, it is available via `this.storage`.

Methods:

#### setItem(key, value, expiration)

Save the value under a specific key. Parameters:

- `key`

- `value` Can be any type. Serialized by casting to a string.

- `expiration` — Storage date (`Date` or `number`). The default value is 24 hours.

#### getItem(key)

Returns the value by key.

#### removeItem(key)

Deletes a value by key.

## TaskInterface {#TaskInterface}

[Task interface](../../../glossary.md#task-interface). In `TaskSuite` and `Task`, it is available via `this.taskInterface`.

Methods:

#### showInstructionPopup()

Opens the [instructions](../instruction.md).

#### toggleFullscreen()

Expands the task to full screen if it is collapsed. Otherwise minimizes the task.

## Hotkey {#Hotkey}

Lets you subscribe to pressed keys. In `TaskSuite` and `Task`, it is available via `this.hotkey`.

Method:

#### on(event, handler, context)

Subscribes the passed handler to a specific event. Tracks events from the `event` parameter. Parameters:

- `event`:

    - `enter` — The “enter” key.

    - `esc` — The “escape” key.

    - `arrow-left`, `arrow-right`, `arrow-up`, `arrow-down` — Arrows.

    - `key` — Alphanumeric keys. Handler (the `handler` parameter) gets the pressed key as the first argument.

- `handler` — The event handler.

- `context` — `this` for the handler.

#### reset()

Cancels all previously made links and reinitializes the service.

## ClientInfo {#clientInfo}

Gets information about the device on which tasks are performed. In `TaskSuite` and `Task`, it is available via `this.clientInfo`.

Method:

#### getClientInfo()

Returns information about the device if the Toloker is using the mobile app:

- `deviceModel` — Mobile device model.

{% include [contact-support](../../_includes/contact-support.md) %}
