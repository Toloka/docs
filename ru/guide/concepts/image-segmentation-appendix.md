# Приложение: полный код всех проектов

## Проект 1. Содержит ли изображение определенный объект? {#section_ncd_2sv_wlb}

**Спецификации:**

#|
||**Входные данные:**|**Выходные данные:**||
||
```json
{
    "image": {
        "type": "url",
        "hidden": false,
        "required": true
    }
}
```
|
```json {
    "result": {
        "type": "string",
        "hidden": false,
        "required": true
    }
}
```
||
|#

Блок **HTML:**

{% if locale == "ru-ru" %}

```html
{{img src=image width="100%" height="400px"}}
<div>Есть ли на картинке <b>дорожный знак</b>?<div>
<div> {{field type="radio" name="result" value="OK" label="Да" hotkey="1"}}
{{field type="radio" name="result" value="BAD" label="Нет" hotkey="2"}}
{{field type="radio" name="result" value="404" label="Ошибка загрузки" hotkey="3"}}</div>
```

{% endif %}{% if locale == "en-com" %}

```html
{{img src=image width="100%" height="400px"}} <div>Is there a  <b>traffic sign</b> in the picture?<div>
<div> {{field type="radio" name="result" value="OK" label="Yes" hotkey="1"}}
{{field type="radio" name="result" value="BAD" label="No" hotkey="2"}}
{{field type="radio" name="result" value="404" label="Loading error" hotkey="3"}}</div>
```

{% endif %}

Блок **JavaScript:**

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

## Проект 2. Выделить объект на изображении {#section_xnw_b4y_tkb}

**Спецификации:**

#|
||**Входные данные:**|**Выходные данные:**||
||
```json
{
    "image": {
        "type": "url",
        "hidden": false,
        "required": true
    }
}
```
|
```json
{
    "result": {
        "type": "string",
        "hidden": false,
        "required": true
    }
}
```
||
|#

Блок **HTML:**

```html
{{field type="image-annotation" name="result" src=image}}
```

Блок **JavaScript:**

1. {% include [image-annotation-p_tgf_nsv_wlb](../_includes/concepts/t-components/image-annotation/id-image-annotation/p_tgf_nsv_wlb.md) %}

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

Блок **CSS:**

```css
.image-annotation-editor__shape-polygon {
display: none;
}
.image-annotation-editor__annotation-layer {
height: max-content;
}
```

## Проект 3. Верно ли выделены объекты на изображении? {#section_jyg_n4y_tkb}

**Спецификации:**

#|
||**Входные данные:**|**Выходные данные:**||
||
```json
{
    "image": {
        "type": "url",
        "hidden": false,
        "required": true
    },
    "selection": {
        "type": "json",
        "hidden": false,
        "required": false
    },
    "assignment_id": {
        "type": "string",
        "hidden": true,
        "required": true
    }
}
```
|
```json
{
    "result": {
        "type": "string",
        "hidden": false,
        "required": true
    }
}
```
||
|#

Блок **HTML:**

{% if locale == "ru-ru" %}

```html
{{field type="image-annotation" name="object" annotations=selection}}
 {{field type="radio" name="result" value="OK" label="Верно" hotkey="1"}}
  {{field type="radio" name="result" value="BAD" label="Неверно" hotkey="2"}}
```

{% endif %}{% if locale == "en-com" %}

```html
{{img src=image width="100%" height="400px"}} <div>Is there a  <b>traffic sign</b> in the picture?<div>
<div> {{field type="radio" name="result" value="OK" label="Yes" hotkey="1"}}
{{field type="radio" name="result" value="BAD" label="No" hotkey="2"}}
{{field type="radio" name="result" value="404" label="Loading error" hotkey="3"}}</div>
```

{% endif %}

Блок **JavaScript:**

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

Блок **CSS:**

```css
/* disable polygon-editor controls */
.image-annotation-editor__shape-polygon {
  display: none;
}
.image-annotation-editor__annotation-layer {
  height: max-content;
}
```