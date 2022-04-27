# Read and write

This section contains the code examples for reading from the input data (`data.input`) and writing to the output data (`data.output`).

Read and write for interim data (`data.internal`) is similar.

For more information on how to add a quotation mark `"`, backslash `\`, line break, or tab to the object in the input data, see [If you're not familiar with JSON](../quickstart.md). For more information about escaping in TSV files, see the [Requester's guide]({{ toloka-requester-create-tsv }}).

## Basic example {#read-write-data}

Let's say you want to display the question text from the input data and write the response to the output data. Sample input data:
```json
{  "question": "Would you buy an elephant?"
}
```
Example of the question display in the [view.text](../reference/view.text.md) component:
```json
{
  "type": "view.text",
  "label": "Answer the question:",
  "content": {
    "type": "data.input",
    "path": "question"
  }
}
```
Example of writing a response using the [field.radio-group](../reference/field.radio-group.md) component:
```json
{
  "type": "field.radio-group",
  "options": [...],
  "data": {
    "type": "data.output",
    "path": "verdict"
  }
}
```

When you respond with yes and click **Send**, the result looks like this:

```json
{
  "output": {
    "verdict": true
  }
}
```

.

## Reading JSON input data {#read-json}

If you pass a JSON object in the input data and want to get a value for some nested key, specify the path to it using the dot as a separator.

Let's say you have an input object that describes a residential address.
```json
{
    "name": "Ivan Ivanov",
    "registration_address": {
        "country": "Russia",
        "city": "Moscow",
        "address": "Tverskaya str, 3-53"
    },
    ...
```

To display the value from the city property in the interface, specify the path to this value using the dot separator:
```json
{
  "type": "data.input",
  "path": "registration_address.city"
}
```

.

## Writing JSON data {#write-json}

The output data is written similarly. If you enter the path separated by dots, the field with the output data will have the object type in the specification.

.

## Reading data with the "array" type {#read-array}

To get a value from a specific element in an array, use the path to specify its sequence number, starting from zero.

Let's say the input data contains of an array of links to images:
```json
{
  "images": [
    "https://cdn.stocksnap.io/img-thumbs/960w/surfer-wave_3DBOYBPB3X.jpg",
    "https://cdn.stocksnap.io/img-thumbs/960w/fisherman-silhouette_UADULRRHEK.jpg",
    "https://cdn.stocksnap.io/img-thumbs/960w/old-photo_GEQ27OWZVV.jpg"
  ]
}
```
You can reference a specific array element like this:
```json
"url": {
  "type": "data.input",
  "path": "images.<Element number, starting from zero>"
}
```

.

If the array length is unknown or very large, you can get all the array values using the [helper.transform](../reference/helper.transform.md) component.

For example, you can convert an array of image links to an array of [view.image](../reference/view.image.md) components to display them in the interface.

.

## Writing the array data {#write-array}

Similarly to reading elements from an array, you can also write the results to an array. For this, use the `path` property for the path to the array and the element number starting from zero. Example:
```json
{
  "type": "data.output",
  "path": "images.0"
}
```

.


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
