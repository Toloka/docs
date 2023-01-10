{% cut "How do I create a shortcut for adding a polygon in "image-annotation"?" %}

To create a shortcut, add the following action to the "onKey" method:

```javascript
onKey: function(key) {
    var el = this.getDOMElement().querySelector(".image-annotation-editor__shape-polygon");

    if (key === 'D') {
        el.click();
        el.classList.add('image-annotation-editor__shape_active')
    }
}
```

If you need to further modify the area-selection editor, use [this library](https://github.com/vmit/image-annotation).

{% endcut %}