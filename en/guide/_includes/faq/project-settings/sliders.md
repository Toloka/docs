{% cut "How do I use sliders as interface elements for selecting parameter values?" %}

In the HTML code of the template, enter the following:

```html
<input type=""range"" list=""rng"" class=""res"">
```

and include the following in `onRender` in your JS:

```javascript
onRender: function() {
    // Generated DOM element for the task (available via #getDOMElement())
    //Adding auxiliary variables
    var $root = $(this.getDOMElement());
    var _this = this;
    var solution = TolokaHandlebarsTask.prototype.getSolution.apply(this, arguments);
    $root.on('change', '.res', function(){
        var range_result = $(this).val()
        _this.setSolutionOutputValue('result', range_result);
        return solution;
    })
}
```

{% endcut %}