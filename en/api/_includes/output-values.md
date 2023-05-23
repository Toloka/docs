Output data values to check. You should specify values for all required output data fields.

```json
  "<ID of field 1>": "<correct response>",
  "<ID of field 2>": "<correct response>",
  ...
```

{% note info %}

If the output field isn't required in the control task, don't specify it in the `known_solutions[].output_values` parameter.

{% endnote %}