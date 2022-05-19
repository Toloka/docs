# Read and write

This section contains the code examples for reading from the input data (`data.input`) and writing to the output data (`data.output`).

Read and write for interim data (`data.internal`) is similar.

For more information on how to add a quotation mark `"`, backslash `\`, line break, or tab to the object in the input data, see [If you're not familiar with JSON](../quickstart.md). For more information about escaping in TSV files, see the [Requester's guide]({{ toloka-requester-create-tsv }}).

## Basic example {#read-write-data}

Let's say you want to display the question text from the input data and write the response to the output data. Sample input data:
```json
{  
  "question": "Would you buy an elephant?"
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

[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOkgB6CQI6qrzcAhgCMi3TSACCUPiSIAnLHQAWRLAEcArkQCcNDIwipKeJBQkjFsVKpieOqsKLQAJuZ05pxwUEz+hsaJNHhMWZ52AUF0IVB4EWIAvo1YTcVKCYnJzKkUePA26Zyu5ukhALQIrhD+TOEmkSAQTLXQsmkKi6pdJThmVjZ2AJpBC3ulBObcgWx0rrfbSu2tYrt7B9a2aXgAchDnC7sa63NIwa58VhPZqvLAAXQ6phAmWy8Vh+3ovTsKJyszoBSK6No5S8dnwbnGYEMsJaT1pYjhilpTSMIDyBJQaEUeGqwWgdgA6rNuOksAxZlhLP4GFhzNgbEQmJ45XQAPwNKAsppAA).

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


[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOkgB6CQI6qryQoki2yqqxedaxS0AJgEM6rznChMAroeNbGjwmdwALTRAoVylHFSUAX0DbPG5XACMibkiAORiiZDx4nCTi5RMle2ZHCi1iHQQAJwhfJmEynFSMrMiAJSIEfjpG9zhoLFdnZ0aiPlkjDtpzS0MKGyC1asjtHiH2itMQZzgZsDoxqEiwiEa4AC9oD2yFg8qQCWl5igVX1XWN4L0LZOOpcfQBRaHZZEKxOf4AwEOSJuDxeHz+fYIt6hOgREEgGaDAQjc7QAD6gAYQKYzOacMASBhFX62UrMw5pTLPWogADCDMKIEhNFZWPhAKqGnxO3BmKxS0eMNW5TliOB3JRnm8fghbJSIBxeO5hKGJIulOpsz4nEm00tTJVIrlXU5kUACCAWuYCoUlIUAXUWCTKjrEYtVku5OyaLTaLyCzp6+P6fDgzkVrm4Ew982SUIVsLWQolNXY9V2AllcaOJyIZwuVxu90e6Yreo+Mnk3uVTqB4ZLYKIBhb4vAeaVoeHSPxGrR2qHCJC4UiNJTae45tttPpjHtcuD85AHIT3L5jC9upKOY2471k4jpZlse70PzXZVReR7k16J1Ks6+sX+LLqmFjpuuNJWja4E7lie7DoeXK0O6G58GeMF+gGQbxP61CBlACRGO834oGgih4NEsSRAAkvgrjYNRtEQPgsp4MaxKjOSVLIdY8RmC0FiNIyia+HMcCuC2ZgMpEACyEB8JAZCPn+kF2viAAq+BEI0fAANauAwrhYMSQhYAAzAAtAArCZO6OixswriBa6cVBcI8SOvj8YJ3K9MJyZiYpSySfiMlyRACmXngylzJEABa5EwrphnDMZACMACcZkAEwAAw2Zg+EJEAA).


## Writing JSON data {#write-json}

The output data is written similarly. If you enter the path separated by dots, the field with the output data will have the object type in the specification.


[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNnnhFuAE06SAHoJAjqqvNwCGAIx2aQAGSsCsUK1NamVSvE2tgRAAWEHpEAE4OAJL4VlAQ+MI+Yni6VnRWbFSqKfTMXhSp6VacEACudEwVSeY5fulBDu6enHxl4c1eyTQAvt09ZqrZdXkaKLTaegZExjU5tNZ23A4AYnDhrp1zI-5WgSFhkeN4MXHbFiBpGVndueoFtFcl5ZXV3rUXTA1NHkSc8Bs6FsQLcsH0PmDBkphhd7g5JvojCYoRdFvZjiAALJwXS6bhENy-c6+EC7fahXQRaKxeKEMCNd7zIrXcYwkZwjFPUoVKrI0E4ep0BmFECdThSHF4ojA0Hg1QDbpsu75eHEKZQMpSOxHFEktHLDEAQQQXl1uTJwQpVIxACYbcTck8bhDlWMRVyXryHSSvkKHFYTXhZWaaHgJVA4FJNWwAAz9HwAXV1lls6JFAFEoJJwlgGOUczAytxuITPEHqOCeqYQHAoLyUGgqz0gA).


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


[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOcKQEMErECOqq8AVwBO3NlVVi864xTwATfXX26oTC4JMVBzwmTwALTRA9QyI+TgAGPCCxAF9krBTTVXtg+mYXdmIdaKNhdJxLGztymid8yI8vHz8ArIcKkFC6CJRxAyM4gEYksyU00ZxM9JzzPI1erSLdfuM22etbXpnc5wbPbzhffzKJpRDwyJLYzgAmEfbx1UeaAF1FcZSTKKO6FDRFPBXWS9BSjPBhOh0Jh8ZAAelhYDcUE4AggYAA1nwoPomLoILC9AgALTdCxSABGfFhAE4AGzxEiwvjWGBEKxEkj6fBEAD6AGYACIAIQA8gBNIUABSFfIAGpwAFZMBAnRwgCFQmHwxHI1EYrE4vEEqTE0kUql0hmw+B8MJsgxQIl8ODcMIQCxESG8gCqAEEBd6ADIAJWDAAkAKIAaUVytVtXVkOhcIRSJRdDRmOxuLg+MJJLCZMpNPpjIg3DcRKYbozPIA4hGAIo3ADsIoA6gAtABq3djKpAijeUE+KSAA).


If the array length is unknown or very large, you can get all the array values using the [helper.transform](../reference/helper.transform.md) component.

For example, you can convert an array of image links to an array of [view.image](../reference/view.image.md) components to display them in the interface.


[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOcKQEMErECOqq8AVwBO3NlVVi864xTwATfXX26oTC4JMVBzwmTwALTRA9QyI+TgAGPCCxAF9krBTTVXtg+mYXdmIdaKNhdJxLGztymid8yI8vHz8ArIcKkFC6CJRxAyM4gEYksyU00ZxM9JzzPI1erSLdfuM22etbXpnc5wbPbzhffzKJpRDwyJLYzgAmEfbx1UeaAF1FcZSTKKO6FDRFPBXWS9BSjPBhOh0Jh8ZAAelhYDcUE4AggYAA1nwoPomLoILC9AgALTdCxSABGfFhAE4AGzxEiwvjWGBEKxEkj6fBEAD6AGYACIAIQA8gBNIUABSFfIAGpwAFZMBAnRwgCFQmHwxHI1EYrE4vEEqTE0kUql0hmw+B8MJsgxQIl8ODcMIQCxESG8gCqAEEBd6ADIAJWDAAkAKIAaUVytVtXVkOhcIRSJRdDRmOxuLg+MJJLCZMpNPpjIg3DcRKYbozPIA4hGAIo3ADsIoA6gAtABq3djKpAijeUE+KSAA).


## Writing the array data {#write-array}

Similarly to reading elements from an array, you can also write the results to an array. For this, use the `path` property for the path to the array and the element number starting from zero. Example:
```json
{
  "type": "data.output",
  "path": "images.0"
}
```


[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNnnhFuAE06SAHoJAjqqvLoCGdK2yqqxedaxS1rtzhACudJr+EVRzwmGwALTXAIbh8AJz5OAAY8ILEAX1SsNLNVB2D6ZlcKLWI9AyJjQPMlSxs7NzzHNULIjysvX38THKbaULoItzxIGO94zgBGFOr0zOzMxpqCjSGQbTKjbsycWtt7bZpnFtW2jr8A0wOdkH7B4qjR8YAmaaaMmayggF0e6+4rABGOkiAFEoJJYlgBrEiEQsBAYFgGHEsDArPgILEJHCRpjZCBFO80qYQHAoF0UGhiWkgA).

## Related information

- [Creating specifications](https://toloka.ai/docs/template-builder/operations/create-specs.html)
- [Clearing the entered values](https://toloka.ai/docs/template-builder/operations/clear-data.html)

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
