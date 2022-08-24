# Additional helpers

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in [Template Builder]({{ tb-quickstart }}).

{% endnote %}


Helpers are functions that you can use to pass any number of expressions. After processing the result, they return HTML code.

## Concatenation {#concat}

To concatenate two or more strings into a single string, use the `{{concat "<string 1> " ... " <string _n_>"}}` helper. Example:

```
{{#each inputValues}}
  {{field type="input" name=(concat "field_" this)}}
{{/each}}
```

## Object operations {#object}

To get the key value from an object, use the `{{get <object> "<key>"}}` helper. Example:

```
{{get inputValuesObj "key"}}
```

## Logical operations and comparisons {#equal}

Logical operations and comparison operations return either `true` or `false`.
To apply a logical operation to boolean values, use the helpers:
- AND: `{{and "a" … "n"}}`,
- AND: `{{or "a" … "n"}}`,
- Negation: `{{not "a"}}`.

To compare numeric values, use the helpers:

- Greater than: `{{gt "a" "b"}}`,
- Greater than or equal to `{{gte "a" "b"}}`,
- Less than: `{{lt "a" "b"}}`,
- Less than or equal to: `{{lte "a" "b"}}`,
- Equal to: `{{equal "a" "b"}}`.
    {% note info %}

    The `{{equal}}` helper lets you compare values of any data type.

    {% endnote %}


## Recording output data field values in JSON {#js_fields}

The values of multiple components can be written to the [output data field](../incoming.md) in JSON format.

To do this, specify the output data field in the `name` attribute of the component and add a unique ID separated by a dot.

For example, the values of the two text input fields are written as JSON objects in the `result` output data field.

```
{{field type="input" name="result.input1"}}
{{field type="input" name="result.input2"}}
```

The [TSV file](../../../glossary.md#tsv-file-definition-ru) with responses will contain the following in the `result` column:{% if locale == "en-com" %}
```
{result {"input1": "<Toloker's response", "input2": "Toloker's response>"}}
```
{% endif %}

{% include [contact-support](../../_includes/contact-support-help.md) %}