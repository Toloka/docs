# Overview

You can choose which Tolokers will have access to pool tasks. For example, you can select Tolokers by region, skill, or type of browser (desktop or mobile).

To set up Toloker filtering for a pool, add the `filter` JSON object to the pool. A [sample filter in JSON](#request-example) with a [parameter description](#params) is shown below.

{% note info %}

The JSON filter description must not exceed 10,000 characters.

{% endnote %}

## Sample filter in JSON {#request-example}

This example selects Tolokers from Russia and Ukraine for completing tasks (it uses the region detected from the Toloker's IP address and the country specified in the profile). Users must have a minimum skill level of 60 for the control page results.

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
            "value":225
          },
          {
            "category":"computed",
            "key":"region_by_ip",
            "operator":"IN",
            "value":187
          }
        ]
      },
      {
        "category":"profile",
        "key":"country",
        "operator":"EQ",
        "value":"RU"
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
|| **category** | **string \| mandatory**

Group of data for filtering:

- `skill` — The skill.
- `profile` — Profile data.
- `computed` — Computed data, such as the Toloker's region according to the IP address. ||
|| **key** | **string \| mandatory**

Attribute to use for filtering Tolokers. For example, the country (`country`), or a skill (specify the skill ID). ||
|| **operator** | **string \| mandatory**

Comparison operator in the condition. For example, the condition "Toloker must be 18 or older" uses the date of birth and the `GTE` ("Greater than or equal to") operator. Possible values for the `operator` key depend on the type of data in the `value` field. To choose the correct value, see the descriptions of filters in the sections [Filter by profile data](filter-profile.md), [Filter by calculated data](filter-computed.md), [Filter by skills](filter-skill.md).

{% note info %}

The `operator` value must be lowercase.

{% endnote %} ||
|| **value** | **boolean**, **string**, **list of strings**, **integer \| mandatory**

The value of the attribute from the `key` field. For example, the ID of the region specified in the profile, or the minimum skill value. To choose the correct value, see the descriptions of filters in the sections [Filter by profile data](filter-profile.md), [Filter by calculated data](filter-computed.md), [Filter by skills](filter-skill.md). ||
|#