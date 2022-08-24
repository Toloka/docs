# Appendix: Complete code for all projects

## Project 1. Does the image contain a certain object? {#section_ncd_2sv_wlb}

**Specifications:**

**Input:**```html {   "image": {     "type": "url",     "hidden": false,     "required": true   } } ``` | **Output:**```html {   "result": {     "type": "string",     "hidden": false,     "required": true   } } ```


**HTML:**
 {% if locale == "en-com" %}
```html
{{img src=image width="100%" height="400px"}} <div>Is there a  <b>traffic sign</b> in the picture?<div>
<div> {{field type="radio" name="result" value="OK" label="Yes" hotkey="1"}}
{{field type="radio" name="result" value="BAD" label="No" hotkey="2"}}
{{field type="radio" name="result" value="404" label="Loading error" hotkey="3"}}</div>
```
{% endif %}
**JavaScript:**

```javascript
exports.Task = extend(TolokaHandlebarsTask, function(options) {
    TolokaHandlebarsTask.call(this, options);
}, {
    onRender: function() {
        // DOM element for task is formed (available via #getDOMElement())
    },
    onDestroy: function() {
        // Task is completed. Global resources can be released (if used)
    }
});

function extend(ParentClass, constructorFunction, prototypeHash) {
    constructorFunction = constructorFunction || function() {};
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

## Project 2. Select an object in the image {#section_xnw_b4y_tkb}

**Specifications:**

**Input:**<br/>```html {   "image": {     "type": "url",     "hidden": false,     "required": true   } } ``` | **Output:**<br/>```html {   "result": {     "type": "string",     "hidden": false,     "required": true   } } ```


**HTML:**

```html
{{field type="image-annotation" name="result" src=image}}
```

**JavaScript:**

1. Connect the $TOLOKA_ASSETS/js/image-annotation.js library (click ![](t-components/../../_images/settings.svg) in the **Task interface** block on the project page).

1. ```javascript
    exports.Task = extend(TolokaHandlebarsTask, function (options) {
    TolokaHandlebarsTask.call(this, options);
    }, {
    onRender: function() {
    // DOM element for task is formed (available via #getDOMElement())
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


**CSS:**

```
.image-annotation-editor__shape-polygon {
display: none;
}
.image-annotation-editor__annotation-layer {
height: max-content;
}
```

## Project 3. Are the bounding boxes correct? {#section_jyg_n4y_tkb}

**Specifications:**

**Input:**<br/>```html {   "image": {     "type": "url",     "hidden": false,     "required": true   },   "selection": {     "type": "json",     "hidden": false,     "required": false   },   "assignment_id": {     "type": "string",     "hidden": true,     "required": true   } } ``` | **Output:**<br/>```html {   "result": {     "type": "string",     "hidden": false,     "required": true   } } ```


**HTML:**
 {% if locale == "en-com" %}
```html
{{img src=image width="100%" height="400px"}} <div>Is there a  <b>traffic sign</b> in the picture?<div>
<div> {{field type="radio" name="result" value="OK" label="Yes" hotkey="1"}}
{{field type="radio" name="result" value="BAD" label="No" hotkey="2"}}
{{field type="radio" name="result" value="404" label="Loading error" hotkey="3"}}</div>
```
{% endif %}
**JavaScript:**

```javascript
exports.Task = extend(TolokaHandlebarsTask, function(options) {
    TolokaHandlebarsTask.call(this, options);
}, {
    onRender: function() {
        // DOM element for task is formed (available via #getDOMElement())
    },
    onDestroy: function() {
        // Task is completed. Global resources can be released (if used)
    }
});

function extend(ParentClass, constructorFunction, prototypeHash) {
    constructorFunction = constructorFunction || function() {};
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

**CSS:**
```
/* disable polygon-editor controls */
.image-annotation-editor__shape-polygon {
  display: none;
}
.image-annotation-editor__annotation-layer {
  height: max-content;
}
```
