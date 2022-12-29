# Filter by skills

To use a skill value for selecting Tolokers, define the `filter` object in the pool parameters.

To filter Tolokers without a skill set the `"operator": "EQ"` parameter and exclude the `value` parameter.

## Sample filter in JSON {#request-example}

```json
{
  "filter" : {
    "and" : [ {
      "category": "skill",
      "key": 55,
      "operator": "GT",
      "value": 59.7
      }
    ]
  }
}
```

## Key, value parameters {#params}

#|
|| Key parameter | Value description ||
|| **integer**

Skill ID. | **float**

Fractional value of the skill. Minimum — 0, maximum — 100.

Value of "operator":

- `EQ` — Equal to.
- `NE` — Not equal to.
- `GT` — Greater than.
- `LT` — Less than.
- `GTE` — Greater than or equal to.
- `LTE` — Less than or equal to.||
|#

## See also {#see-also}

- [More information about filters](../../guide/concepts/filters.md)