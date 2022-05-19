# Object selection in an image

This section describes how to add the area selection editor to an image and speed up task completion with shortcuts. If you just need to insert a picture, read the [Inserting images](insert-images.md) section.


## Add the area selection editor {#add-select}

To allow users to select areas in pictures, use the [field.image-annotation](../reference/field.image-annotation.md) component.

```json
{
  "view": {
    "type": "field.image-annotation",
    "data": {
      "type": "data.output",
      "path": "path"
    },
    "image": "url"
  }
}
```

[View example in the sandbox](https://clck.ru/RnZox).


## Configure labeling modes {#shapes}

The component offers three labeling modes: rectangle, polygon, and point markup. All three modes are available by default. You can choose to use just one or two of them.

{% list tabs %}

- Rectangles

  To allow users to select areas only with rectangles, add the `rectangle` key to the `shapes` property and set its value to `true`.

  ```json
  {
    "shapes": {
      "rectangle": true
    }
  }
  ```

  [View example in the sandbox](https://clck.ru/Rna3F).

- Polygons

  To allow users to select areas only with polygons, add the `polygon` key to the `shapes` property and set its value to `true`.

  ```json
  {
    "shapes": {
      "polygon": true
    }
  }
  ```

  [View example in the sandbox](https://clck.ru/RnZtm).

- Points

  To allow users to select areas only with points, add the `point` key to the `shapes` property and set its value to `true`.

  ```json
  {
    "shapes": {
      "point": true
    }
  }
  ```

  [View example in the sandbox](https://clck.ru/RnZyt).

{% endlist %}

## Classify areas {#labels}

You can allow users to select objects by type. For example, you may want all cars selected in the picture to be labeled as one type, and all road signs as another.

```json
{
  "labels": [{
      "label": "Option 1",
      "value": "value1"
    },
    {
      "label": "Option 2",
      "value": "value2"
    }
  ]
}
```

[View example in the sandbox](https://clck.ru/TqvPR).

For each new object of the `labels` property, a button is added to the editor that allows users to select the corresponding area type. Different values of the `value` property let users label areas with different colors.


## Add keyboard shortcuts {#hotkeys}

To help performers work faster, you can add keyboard shortcuts using the [plugin.field.image-annotation.hotkeys](../reference/plugin.field.image-annotation.hotkeys.md) component. Shortcuts can be assigned to the up and down arrows (`up`,`down`), numbers, and Latin letters.

If you install the shortcut plugin without assigning keys, they are assigned automatically (see the [example](https://clck.ru/RnbbS)). You can change them as described below. If you don't need some of the shortcuts, leave their value fields empty.

{% list tabs %}

- Select area types

  If you use at least two types of areas in your task, list the shortcuts for them in the array of the `labels` property, separating them with commas. They will be assigned to the area selection buttons in the order they are displayed.

  ```json
  {
    "type": "plugin.field.image-annotation.hotkeys",
    "labels": [
        "1",
        "2"
    ]
  }
  ```

  [View example in the sandbox](https://clck.ru/TqvWA).

- Select labeling modes

  You can let users switch between different labeling modes using shortcuts. Add the corresponding key to the `modes` property and assign a shortcut to it:
  - `select`: For selecting shapes and points.
  - `point`: For selecting areas using points.
  - `rectangle`: For selecting areas using rectangles.
  - `polygon`: For selecting areas using polygons.

  ```json
  {
    "type": "plugin.field.image-annotation.hotkeys",
    "modes": {
      "select": "q",
      "point": "w",
      "rectangle": "e",
      "polygon": "r"
    }
  }
  ```

  [View example in the sandbox](https://clck.ru/TqvYU).

- Confirm or cancel area creation

  You can set up shortcuts to let users confirm or cancel area creation. Assign shortcuts to properties:
  - `confirm`: Confirm.
  - `cancel`: Cancel.

  ```json
  {
    "type": "plugin.field.image-annotation.hotkeys",
    "confirm": "x",
    "cancel": "z"
  }
  ```

  [View example in the sandbox](https://clck.ru/Tqvai).

{% endlist %}

## Create a task {#create-task}

To create a template for area selection tasks, use the following components:

- [field.image-annotation](../reference/field.image-annotation.md): To add the area selection editor.
- [plugin.field.image-annotation.hotkeys](../reference/plugin.field.image-annotation.hotkeys.md): To add keyboard shortcuts.
- [view.text](../reference/view.text.md): To add a description to the task.
- [condition.required](../reference/condition.required.md): To make sure that the user selected at least one area.
- [plugin.toloka](../reference/plugin.toloka.md): To customize the task layout.

[View example in the sandbox](https://clck.ru/Tqvd5).

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
