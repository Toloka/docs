# Filter by profile data

To select Tolokers based on profile data, define a `assignments_issuing_config.filter` object in the [pool parameters](https://toloka.ai/docs/api/api-reference/#tag--pool).

## Sample filter in JSON {#request-example}

This example selects Tolokers who set their country as US and the city as Washington, D.C. in the profile.

```json
{
  "filter": {
    "and": [
      {
        "or": [
          {
            "category": "profile",
            "key": "country",
            "operator": "EQ",
            "value": "US"
          }
        ]
      },
      {
        "or": [
          {
            "category": "profile",
            "key": "city",
            "value": 87,
            "operator": "IN"
          }
        ]
      }
    ]
  }
}
```

## Key and value parameters {#params}

#|
|| Key parameter | Value description ||
|| `gender` | _string_

The Toloker's gender:

- `MALE` — Male.
- `FEMALE` — Female.

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to. ||
|| `country` | _string_

The Toloker's country of residence (the two-letter code from the [ISO 3166-1 alpha-2](https://www.iso.org/obp/ui/#search/code/) standard).

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to. ||
|| `citizenship` | _string_

The Toloker's country of citizenship (the two-letter code from the [ISO 3166-1 alpha-2](https://www.iso.org/obp/ui/#search/code/) standard).

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to. ||
|| `education` | _string_

The Toloker's level of education:

- `BASIC` — Secondary education (high school).
- `MIDDLE` — Specialized secondary education (vocational school).
- `HIGH` — Post-secondary education (university).

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to. ||
|| `adult_allowed` | _boolean_

The Toloker agrees to perform tasks that contain adult content.

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to. ||
|| `date_of_birth` | _integer_

The Toloker's date of birth specified as a [UNIX timestamp](https://unixtime.org/).

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to.
- `GT` — Greater than.
- `LT` — Less than.
- `GTE` — Greater than or equal to.
- `LTE` — Less than or equal to. ||
|| `city` | _integer_

The Toloker's city ([the region ID in the search database](regions.md)).

Value of `operator`:

- `IN` — Contained in the list of regions or languages in the profile.
- `NOT_IN` — Not contained in the list of regions or languages in the profile. ||
|| `languages` | _string_

The languages the Toloker entered in the profile (uppercase two-letter ISO code conforming to [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)).

Value of `operator`:

- `IN` — Contained in the list of regions or languages in the profile.
- `NOT_IN` — Not contained in the list of regions or languages in the profile.||
|#

## See also {#see-also}

- [{#T}](../../guide/concepts/filters.md)
- [Toloka-Kit recipe: Filter Tolokers](../../toloka-kit/recipes/filter-tolokers.md)
- [Toloka-Kit recipe: Filter Tolokers with confirmed language knowledge](../../toloka-kit/recipes/filter-tolokers-languages.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}