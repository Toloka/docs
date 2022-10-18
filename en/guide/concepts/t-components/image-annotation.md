# Image with area selection

{% note info %}

This section describes how to add an area selection editor to an image using the HTML/JS/CSS tools. You can also try creating an [area selection]({{ tb-select-areas }}) editor in Template Builder.

{% endnote %}

The editor lets you select an area of the image using either a rectangle or an arbitrary polygon:

{% note info %}

Don't add [training or control tasks](../pool.md) to a [project](../../../glossary.md#project) that features an image area selection editor.

{% endnote %}

## Adding the editor {#adding_editor}

#### Picture

If you need to add an image editor without selected objects:

1. Connect the $TOLOKA_ASSETS/js/image-annotation.js library (click ![](../../_images/settings.svg) in the **Task interface** block on the project page).

1. Include the `{{field type="image-annotation"``name="<[output field](../incoming.md) name>"``src=<image URL>}}` component in the HTML code of the interface. For example:

    ```html
    {{field type="image-annotation" name="result" src=image}}
    ```

    For a complete list of parameters, see the [table](#image-annotation).

1. Add a field for entering an image link in the [input data](../incoming.md).

1. Add the `result` field with the **json** type in the output data.

The `result` field will be used for a JSON object with the point coordinates. Example:

```json
[{"data":{"p1":{"x":0.472,"y":0.413},"p2":{"x":0.932,"y":0.877}},"type":"rectangle"},
{"data":[{"x":0.143,"y":0.807},{"x":0.317,"y":0.87},{"x":0.511,"y":0.145},{"x":0.328,"y":0.096},{"x":0.096,"y":0.554}],"type":"polygon"}]
```

The _x_ and _y_ values are numbers from 0 to 1. Length and width of the image are taken as 1, with the center of coordinates in the upper-left corner of the image.

#### Images with selected objects

If you have images with selected objects and you want to upload them to the task:

1. Connect the $TOLOKA_ASSETS/js/image-annotation.js library (click ![](../../_images/settings.svg) in the **Task interface** block on the project page).

1. Include the `{{field type="image-annotation"``name="<[output field](../incoming.md) name>"``src=<image URL>``annotations=<[input field](../incoming.md) name>}}` component in the interface HTML code. Example:

    ```html
    {{field type="image-annotation" name="result" src=image annotations=polygon}}
    ```

1. Add the following in the [input data](../incoming.md):

    - A field for entering an image link.

    - The `polygon` field with the **json** type to pass the coordinates of the selected area.

1. Add the `result` field with the **json** type in the output data. A field for recording results is required for this component. If the Toloker edits the selected area, the updated coordinates are recorded there.

1. [Escape](../pool_csv.md#json) JSON with point coordinates and add it to the [file with tasks](../../../glossary.md#tsv-file-definition).

#### Parameters

#|
||**Parameter**|**Description**|**Required**|**Default value**||
||`src`| Page URL. | yes | no||
||`type`| Field type: `image-annotation`, the image area selection editor. | yes | no||
||`name`| Attribute for the output data field. Contains the output field name. | yes | no||
||`src`| Image URL. Supported values:

- URL from the task input data. For example, from the field with the `url`: `src=image` ID.

- Direct link. The HTTPS protocol is recommended. For example, `src="https://mywebsite.ru/img1.png"`.

- Relative link. | yes | no||
||`annotations`| Attribute for the input data field. Contains the input data field name. Here you can provide the selection coordinates for further editing. The data format is a JSON object. | no | no||
|#

## Shortcuts {#hotkeys}

By default, you can use the following keyboard shortcuts in the task:

- **C** closes a polygon connecting the first and last points with a line.

- **D** deletes the selected point, selected object, or last point when creating a polygon.

- Arrows move the selected point. With **Alt** pressed, they move it slower. With **Alt+Shift** pressed, they move it faster.

- **Tab** moves from the selected point to the next one.

- **Shift+Tab** moves from the selected point to the previous one.

Tell Tolokers about keyboard shortcuts in the [instructions](../../../glossary.md#task-instruction) to speed up task completion.

## Selection tools {#selection_tools}

By default, the polygon tool is added to the [task interface](../../../glossary.md#task-interface).

You can change the tool set:

{% list tabs %}

- Add a rectangle

  To add a rectangle, delete the CSS selector:

  ```css
  .image-annotation-editor__shape-rectangle {
    display: none;
  }
  ```

- Hide a polygon

  To hide a polygon, add the CSS selector:

  ```css
  .image-annotation-editor__shape-polygon {
    display: none;
  }
  ```

- Hide a rectangle

  To hide a rectangle, add the CSS selector:

  ```css
  .image-annotation-editor__shape-rectangle {
    display: none;
  }
  ```

{% endlist %}

## Annotation {#annotation}

To use annotations, insert one of these examples into the JS block:

{% list tabs %}

- Text input field

  {% if locale == "en-com" %}

  ```javascript
  exports.Task = extend(TolokaHandlebarsTask, function (options) {
      TolokaHandlebarsTask.call(this, options);
  }, {
      onRender: function() {
          var field = this.getField('result');
          var editor = field.getEditor();
          editor.annotationInterface = field.createAnnotationInterface({
              createInterfaceElement: function() {
                  this._input = document.createElement('input');
                  this._input.addEventListener('input', function() {
                      this._shape.annotation = this._input.value;
                  }.bind(this));
                  return this._input;
              },
              onShow: function(shape) {
                  this._shape = shape;
                  this._input.value = shape.annotation;
              }
          });
    },
    onDestroy: function() {
      // Task is completed. Global resources can be released (if used)
    }
  });

  function extend(ParentClass, constructorFunction, prototypeHash) {
    constructorFunction = constructorFunction || function () {};
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

  {% endif %}

- Drop-down list

  {% if locale == "en-com" %}

  ```javascript
  var listOption =
  [["Animals","Cat","Dog","Bird"]];
  var listValues =
  [
  ["-","Cat","Dog","Bird"]
  ];
  var bigListValues = [];
  for(var i=0;i<listValues.length;i++){
      for (var j=0;jlistValues[i].length;j++){
          if(j != 0){
              bigListValues[bigListValues.length] = listValues[i][j];
          }
      }
  }

  exports.Task = extend(TolokaHandlebarsTask, function (options) {
      TolokaHandlebarsTask.call(this, options);
  }, {
      onRender: function() {
          var field = this.getField('result');
          var editor = field.getEditor();
          editor.annotationInterface = field.createAnnotationInterface({
              createInterfaceElement: function() {
                  this._select = document.createElement('select');
                  for(var j=0;j<listOption.length;j++){
                      var listGroup = listOption[j];
                      var valuesGroup = listValues[j];
                      var optgroup = document.createElement("optgroup");
                      optgroup.setAttribute('label', listGroup[0]);
                      for (var i = 1; i  listGroup.length; i++) {
                          var option = document.createElement("option");
                          if (i == 0) {
                              option.setAttribute('disabled', 'disabled');
                          }
                          option.value = valuesGroup[i];
                          option.className = "seletOpt";
                          var oText = document.createTextNode(listGroup[i]);
                          option.appendChild(oText);
                          optgroup.appendChild(option);
                      }
                      this._select.appendChild(optgroup);
                  }
                  this._select.addEventListener('change', function() {
                      this._shape.annotation = this._select.value;
                      _.each(bigListValues, function(value) {
                          this._polygonEl.classList.remove(value.toLowerCase());
                      }.bind(this));
                      this._polygonEl.classList.add(this._select.value.toLowerCase());
                  }.bind(this));
                  return this._select;
              },
              onShow: function(shape, el) {
                  console.log("shape: ", shape)
                  console.log("el: ", el)
                  this._shape = shape;
                  this._select.value = shape.annotation;
                  this._polygonEl = el;
              }
          });
    },
    onDestroy: function() {
      // Task is completed. Global resources can be released (if used)
    }
  });

  function extend(ParentClass, constructorFunction, prototypeHash) {
    constructorFunction = constructorFunction || function () {};
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

  {% endif %}

{% endlist %}

{% cut "Explanation of examples" %}

To let the Toloker add an annotation to the selected area or select it from the list, you need to add an interface element to the task (for example, a text field or a drop-down list):

1. Get the object of the `getEditor()` editor and the `getField('result')` annotation interface in the `onRender()` method:

    ```javascript
    var field = this.getField('result');
    var editor = field.getEditor();
    ```

1. Set the annotation interface implementation in methods:

    - `createInterfaceElement()` — Calls the DOM element of the interface (called once during initialization).

    - `onShow(shape, options)` — Shows the annotation interface when the Toloker hovers the mouse over the selected area. Gets JSON with the coordinates of the polygon points as input. In this JSON, you can write the annotation that the Toloker entered.

{% endcut %}

Toloker interactions with the editor cause the following events:

- `shape:start` — Starts area selection.

- `shape:finish` — Completes area selection.

- `shape:cancel` — Deletes a point.

- `shape:remove` — Deletes the selection.

To subscribe to these events:

{% if locale == "en-com" %}

```javascript
editor.on('shape:start', function() {
/* event handling */
});
```

{% endif %}

{% include [contact-support](../../_includes/contact-support-help.md) %}