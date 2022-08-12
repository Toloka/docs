# Configuring task display

Use the `plugin.toloka` plugin to manage the settings for displaying tasks on the suite:
```json
{
  "type": "plugin.toloka",
  "layout": {
    "kind": "scroll",
    "taskWidth": 300
  }
}
```

Display methods are set in the `kind` property:

- `scroll` (default): Displaying multiple tasks on the suite at the same time.
- `pager`: Displaying only one task per suite, but with a button at the bottom to switch between tasks.

Use the `taskWidth` property to set up the task width. By default, the task is displayed in full-screen mode.


## Examples {#concept_gqw_zr5_wlb}

#### Arrange multiple tasks in a row

Let's say you want to display 2 tasks in each row on the screen. To do this, set the value of `taskWidth` so that 2 tasks fit in the screen for most of the Tolokers. For example, specify the value of `500` to display 2 tasks on every screen larger than 1000 pixels wide. In the `kind` property, specify the `scroll` value.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/6YvWe6ym3YbCn7)

#### Show one task out of multiple tasks

You can show just one task out of multiple tasks and add a button for switching tasks at the bottom of the page. To do this, in the `kind` property, specify the `pager` value. If you omit the task width, the task is expanded to full screen.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/6YvWe6ym3YbCn7)

{% include [contact-support](../_includes/contact-support.md) %}