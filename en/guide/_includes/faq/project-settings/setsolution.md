{% cut "How do I run setSolution validation in "OnRender"?" %}

Try to add a condition to check for the second progress bar:

```javascript
setSolution: function(solution) {
    var secondScale = this.getDOMElement().querySelector('.second-scale');

    if(secondScale) {
        secondScale.style.display = solution.output_values.grammar === 'no' ? 'block' : 'none';
    }

    TolokaHandlebarsTask.prototype.setSolution.call(this, solution);
}
```

{% endcut %}