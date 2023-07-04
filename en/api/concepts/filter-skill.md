# Filter by skills

To use a skill value for selecting Tolokers, define the `assignments_issuing_config.filter` object in the [pool parameters](https://toloka.ai/docs/api/api-reference/#tag--pool).

To filter Tolokers without a skill set the `"operator": "EQ"` parameter and exclude the `value` parameter.

## Sample filter in JSON {#request-example}

{% list tabs %}

- Filter Tolokers with skill

  ```json
  {
    "filter": {
      "and": [
        {
          "category": "skill",
          "key": 1124,
          "operator": "GT",
          "value": 59.7
        }
      ]
    }
  }
  ```

- Filter Tolokers without skill

  ```json
  {
    "filter": {
      "and": [
        {
          "category": "skill",
          "key": 1124,
          "operator": "EQ",
        }
      ]
    }
  }
  ```

{% endlist %}

## Key, value parameters {#params}

#|
|| Key parameter | Value description ||
|| _integer_

The ID of the skill you want to use to filter Tolokers.

You can get the list of all available skills using the [Get list of skills](https://toloka.ai/docs/api/api-reference/#get-/skills) method. | _float_

The fractional value of the skill. Minimum — `0`, maximum — `100`.

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to.
- `GT` — Greater than.
- `LT` — Less than.
- `GTE` — Greater than or equal to.
- `LTE` — Less than or equal to.||
|#

## See also {#see-also}

- [{#T}](../../guide/concepts/filters.md)
- [Toloka-Kit recipe: Filter Tolokers](../../toloka-kit/recipes/filter-tolokers.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}