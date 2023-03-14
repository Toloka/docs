**boolean**

Shows whether the list is complete.

Acceptable values:

- `true` — Not all elements are included in the output due to restrictions in the [limit](../../api/concepts/standard-query-parameters.md#limit) parameter.

  You can get the rest of the results by using the `_lt(e)` and `_gt(e)` parameters.
  
  Learn more about [standard query parameters](../../api/concepts/standard-query-parameters.md).

- `false` — The output contains all the items.