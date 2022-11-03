# List of components

Components are JSON objects that you can use when creating an interface in the template builder. For example, use them to add an image, button, or action.

The name of the component is specified in the `type` property in the format: `<category>.<name>`. Each component has its own set of acceptable properties described in detail on the component's page.

Categories:

- [data](../operations/work-with-data.md): Components used for working with data: input, output, or intermediate.
- [layout](#layouts): Options for positioning elements in the interface, such as in columns or side-by-side. If you have more than one element in the interface, these components will help you arrange them the way you want.
- [view](#views): Elements displayed in the interface, such as text, list, audio player, or image.
- [field](#fields): Fields for entering data, such as a text field or drop-down list.
- [condition](#conditions): Check an expression against a condition. For example, you can check that a text field is filled in.
- [helper](#helpers): Perform various operations, such as if-then-else or switch-case.
- [plugin](#plugins): Plugins that provide expanded functionality. For example, you can use `plugin.hotkeys` to set up shortcuts.
- [action](#actions): Perform various actions, such as showing notifications.

**Note:** Some components are context-specific. For example, you can only use plugins in the root `plugins` element. You can see the available components in the editor tooltips when you press the **Tab** key.

## Element layouts {#layouts}

| Component                                     | Description                                                                                           |
| --------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| [layout.bars](layout.bars.md)                 | A component that adds top and bottom bars to the content.                                             |
| [layout.columns](layout.columns.md)           | A component for placing content in columns.                                                           |
| [layout.compare](layout.compare.md)           | Use it to arrange interface elements for comparing them. For example, you can compare several photos. |
| [layout.side-by-side](layout.side-by-side.md) | The component displays several data blocks of the same width on a single horizontal panel.            |
| [layout.sidebar](layout.sidebar.md)           | Lets you place the main content block and an adjacent panel with controls on a page.                  |

## Displayed elements (views) {#views}

| Component                                   | Description                                                                                                                     |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| [view.action-button](view.action-button.md) | Button that calls an action.                                                                                                    |
| [view.alert](view.alert.md)                 | The component creates a color block to highlight important information.                                                         |
| [view.audio](view.audio.md)                 | The component plays audio.                                                                                                      |
| [view.collapse](view.collapse.md)           | Expandable block.                                                                                                               |
| [view.device-frame](view.device-frame.md)   | Wraps the content of a component in a frame that is similar to a mobile phone. You can place other components inside the frame. |
| [view.divider](view.divider.md)             | Horizontal delimiter.                                                                                                           |
| [view.group](view.group.md)                 | Groups components visually into framed blocks.                                                                                  |
| [view.iframe](view.iframe.md)               | Displays the web page at the URL in an iframe window.                                                                           |
| [view.image](view.image.md)                 | Displays an image.                                                                                                              |
| [view.labeled-list](view.labeled-list.md)   | Displaying components as a list with labels placed on the left.                                                                 |
| [view.link](view.link.md)                   | Universal way to add a link.                                                                                                    |
| [view.link-group](view.link-group.md)       | Puts links into groups.                                                                                                         |
| [view.list](view.list.md)                   | Block for displaying data in a list.                                                                                            |
| [view.map](view.map.md)                     | Adds a map to your task.                                                                                                        |
| [view.markdown](view.markdown.md)           | Block for displaying text in Markdown.                                                                                          |
| [view.text](view.text.md)                   | Block for displaying text.                                                                                                      |
| [view.video](view.video.md)                 | Player for video playback.                                                                                                      |

## Data entry elements (fields) {#fields}

| Component                                               | Description                                                                                                                                                                                                           |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [field.audio](field.audio.md)                           | Component for recording audio. Works in the [Toloka app for mobile devices](https://toloka.ai/tolokers/docs/mobile/?lang=en). In a browser, this component opens a window for uploading an audio file.                |
| [field.button-radio](field.button-radio.md)             | Adds a button. This is useful for creating an optional answer.                                                                                                                                                        |
| [field.button-radio-group](field.button-radio-group.md) | Adds buttons for selecting an answer option. This is useful if there are several options. You can add just one button, but it's easier to use [field.button-radio](field.button-radio.md) for that.                   |
| [field.checkbox](field.checkbox.md)                     | A checkbox.                                                                                                                                                                                                           |
| [field.checkbox-group](field.checkbox-group.md)         | Adds a group of checkboxes for selecting independent answer options. This is useful if there are several options. You can add just one checkbox, but it's easier to use [field.checkbox](field.checkbox.md) for that. |
| [field.date](field.date.md)                             | A component for entering the date and time in the desired format and range.                                                                                                                                           |
| [field.email](field.email.md)                           | Creates a field for entering an email address.                                                                                                                                                                        |
| [field.file](field.file.md)                             | This component can be used for uploading files. It's displayed in the interface as an upload button.                                                                                                                  |
| [field.image-annotation](field.image-annotation.md)     | Component for image labeling.                                                                                                                                                                                         |
| [field.list](field.list.md)                             | A component that allows a Toloker to add and remove list items, such as text fields to fill in. This way you can allow a Toloker to give multiple answers to a question.                                              |
| [field.map](field.map.md)                               | Adds a map to your task and allows Tolokers to set markers on it.                                                                                                                                                     |
| [field.media-file](field.media-file.md)                 | Adds buttons for different types of uploads: uploading photos or videos, selecting files from the file manager or choosing from the gallery.                                                                          |
| [field.number](field.number.md)                         | A component that allows a Toloker to enter a number.                                                                                                                                                                  |
| [field.phone-number](field.phone-number.md)             | Creates a field for entering a phone number.                                                                                                                                                                          |
| [field.radio-group](field.radio-group.md)               | A component for selecting one value out of several options. It is designed as a group of circles arranged vertically.                                                                                                 |
| [field.select](field.select.md)                         | Button for selecting from a drop-down list. Use this component when the list is long and only one option can be chosen.                                                                                               |
| [field.text](field.text.md)                             | A field for entering a short text, not more than a line. To add a field for entering multiple lines of text, use [field.textarea](field.textarea.md).                                                                 |
| [field.text-annotation](field.text-annotation.md)       | A component for text segmentation.                                                                                                                                                                                    |
| [field.textarea](field.textarea.md)                     | Box for entering multi-line text.                                                                                                                                                                                     |

## Helpers {#helpers}

| Component                                         | Description                                                                                                                                                                                                             |
| ------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [helper.concat-arrays](helper.concat-arrays.md)   | Merging multiple arrays into a single array.                                                                                                                                                                            |
| [helper.entries2object](helper.entries2object.md) | Creating an object from a specified array of key-value pairs.                                                                                                                                                           |
| [helper.if](helper.if.md)                         | The If...Then...Else operator. Allows you to execute either one block of code or another, depending on the condition.                                                                                                   |
| [helper.join](helper.join.md)                     | The component combines two or more strings into one. You can add a delimiter to separate the strings, such as a space or comma.                                                                                         |
| [helper.object2entries](helper.object2entries.md) | Creating an array of key-value pairs from the specified object.                                                                                                                                                         |
| [helper.replace](helper.replace.md)               | Allows you to replace some parts of the string with others.                                                                                                                                                             |
| [helper.search-query](helper.search-query.md)     | Component for creating a string with a search query reference.                                                                                                                                                          |
| [helper.switch](helper.switch.md)                 | A switch-case construction: sequentially checks the conditions and executes the code when the condition turns out to be true.                                                                                           |
| [helper.text-transform](helper.text-transform.md) | Allows you to change the case of the text, like make all letters uppercase.                                                                                                                                             |
| [helper.transform](helper.transform.md)           | Creates a new array by transforming each of the elements in the original array.                                                                                                                                         |
| [helper.translate](helper.translate.md)           | Component for translating interface elements to other languages. More details in [Translating the task interface](../../guide/concepts/project-languages.md#project-languages__interface-translate). |
| [helper.proxy](helper.proxy.md)                   | You can use this component to download files from Yandex Disk.                                                                                                                                                          |

## Conditions {#conditions}

| Component                                           | Description                                                                                                                                                                                                                         |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [condition.all](condition.all.md)                   | Checks that **all** child conditions are met. If any of the conditions is not met, the component returns 'false'.                                                                                                                   |
| [condition.any](condition.any.md)                   | Checks that **at least one** of the child conditions is met. If none of the conditions is met, the component returns `false`.                                                                                                       |
| [condition.empty](condition.empty.md)               | Checks that the data didn't get a value. If it did, returns `false`. This is useful if you need to check the optional template data (`data.*`) or make sure that a Toloker didn't interact with the data entry fields (`fields.*`). |
| [condition.equals](condition.equals.md)             | Checks whether the original value is equal to the specified value.                                                                                                                                                                  |
| [condition.link-opened](condition.link-opened.md)   | Checks that a Toloker clicked the link.                                                                                                                                                                                             |
| [condition.not](condition.not.md)                   | Returns the inverse of the specified condition.                                                                                                                                                                                     |
| [condition.played](condition.played.md)             | Checks whether playback has started.                                                                                                                                                                                                |
| [condition.played-fully](condition.played-fully.md) | Checks that playback is complete.                                                                                                                                                                                                   |
| [condition.required](condition.required.md)         | Checks that the data is filled in.                                                                                                                                                                                                  |
| [condition.same-domain](condition.same-domain.md)   | Checks if the link that you entered belongs to a specific site. If it does, returns `true`, otherwise, `false`.                                                                                                                     |
| [condition.schema](condition.schema.md)             | Allows validating data using [JSON Schema](https://json-schema.org/learn/getting-started-step-by-step.html). This is a special format for describing data in JSON format.                                                           |
| [condition.sub-array](condition.sub-array.md)       | Checks whether the array is a subarray of another element.                                                                                                                                                                          |
| [condition.distance](condition.distance.md)         | This component checks whether the sent coordinates match the ones that you specified.                                                                                                                                               |

## Plugins {#plugins}

| Component                                                                         | Description                                                                                             |
| --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [plugin.field.image-annotation.hotkeys](plugin.field.image-annotation.hotkeys.md) | Used to set hotkeys for the [field.image-annotation](field.image-annotation.md) component.              |
| [plugin.field.text-annotation.hotkeys](plugin.field.text-annotation.hotkeys.md)   | Use this to set keyboard shortcuts for the [field.text-annotation](field.text-annotation.md) component. |
| [plugin.hotkeys](plugin.hotkeys.md)                                               | You can use this to set keyboard shortcuts for actions.                                                 |
| [plugin.toloka](plugin.toloka.md)                                                 | A plugin with extra settings for tasks in Toloka.                                                       |
| [plugin.trigger](plugin.trigger.md)                                               | Use this to configure triggers that trigger a specific action when an event occurs.                     |

## Actions {#actions}

| Component                                 | Description                                                                                                |
| ----------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| [action.bulk](action.bulk.md)             | Use this component to call multiple actions at the same time.                                              |
| [action.notify](action.notify.md)         | The component creates a message in the lower-left corner of the screen.                                    |
| [action.open-close](action.open-close.md) | Changes the display mode for another component — opens or closes it.                                       |
| [action.open-link](action.open-link.md)   | Opens a new tab in the browser with the specified web page.                                                |
| [action.play-pause](action.play-pause.md) | This component controls audio or video playback. It stops playback in progress or starts if it is stopped. |
| [action.rotate](action.rotate.md)         | Rotates the specified component by 90 degrees.                                                             |
| [action.set](action.set.md)               | Sets the value from `payload` in the data in the `data` property.                                          |
| [action.toggle](action.toggle.md)         | The component changes the value in the data from `true` to `false` and vice versa.                         |

## Data sources {#datas}

| Component                         | Description                                  |
| --------------------------------- | -------------------------------------------- |
| [data.location](data.location.md) | This component sends the device coordinates. |
