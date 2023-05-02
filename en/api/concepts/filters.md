# Overview

You can choose which Tolokers will have access to pool tasks. For example, you can select Tolokers by region, skill, or type of browser (desktop or mobile).

To set up Toloker filtering for a pool, add the `filter` JSON object to the pool. A [sample filter in JSON](#request-example) with a [parameter description](#params) is shown below.

{% note info %}

The JSON filter description must not exceed **10,000** characters.

{% endnote %}

## Sample filter in JSON {#request-example}

This example selects Tolokers from US or United Kingdom for completing tasks (it uses the region detected from the Toloker's IP address and the country specified in the profile). Users must have a minimum skill level of 60 for the control page results.

```json
{
  "filter" : {
    "and":[
      {
        "or":[
          {
            "category":"computed",
            "key":"region_by_ip",
            "operator":"IN",
            "value":84
          },
          {
            "category":"computed",
            "key":"region_by_ip",
            "operator":"IN",
            "value":102
          }
        ]
      },
      {
        "category":"skill",
        "key":"2",
        "operator":"GTE",
        "value":"60"
      }
    ]
  }
}
```

## Parameters {#params}

{% note info %}

The `and` and `or` parameters must be lowercase.

{% endnote %}

#|
|| Parameter | Overview ||
|| `category` | _string_ \| **required**

Group of data for filtering:

- `skill` — The skill.
- `profile` — Profile data.
- `computed` — Computed data, such as the Toloker's region according to the IP address. ||
|| `key` | _string_ \| **required**

Attribute to use for filtering Tolokers. For example, the country (`country`), or a skill (specify the skill ID). ||
|| `operator` | _string_ \| **required**

Comparison operator in the condition. For example, the condition "Toloker must be 18 or older" uses the date of birth and the `GTE` ("Greater than or equal to") operator. Possible values for the `operator` key depend on the type of data in the `value` field. To choose the correct value, see the descriptions of filters in the sections [Filter by profile data](filter-profile.md), [Filter by calculated data](filter-computed.md), [Filter by skills](filter-skill.md).

{% note info %}

The `operator` value must be lowercase.

{% endnote %} ||
|| `value` | _boolean_, _string_, _list of strings_, _integer_ \| **required**

The value of the attribute from the `key` field. For example, the ID of the region specified in the profile, or the minimum skill value. To choose the correct value, see the descriptions of filters in the sections [Filter by profile data](filter-profile.md), [Filter by calculated data](filter-computed.md), [Filter by skills](filter-skill.md). ||
|#

## See also {#see-also}

- [{#T}](../../guide/concepts/filters.md)
- [Toloka-Kit recipe: Filter Tolokers](../../toloka-kit/recipes/filter-tolokers.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}