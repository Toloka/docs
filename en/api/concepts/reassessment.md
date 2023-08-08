# Processing rejected and accepted assignments

You can use this rule to:

- Resend rejected task suites for recompletion to other Tolokers.

    If you rejected a task suite, you may want it to be completed by a different Toloker instead of the one whose response you rejected. To do this, you can increase the [overlap](../../glossary.md#overlap) for this task suite only. This is especially helpful if you have the overlap value set to **1**.

- Save money on re-completing task suites that you have already accepted.

    If you reviewed and accepted a task suite, it may not make sense for other Tolokers to complete it. To avoid this, you can reduce the overlap only for accepted task suites.

Set key values in the `quality_control.configs` array in the [pool settings](https://toloka.ai/docs/api/api-reference/#tag--pool).

## Request body {#body}

Re-assign task suites that didn't pass manual review.

```json
{
  "configs": [
    {
      "collector_config": {
        "type": "ASSIGNMENTS_ASSESSMENT"
      },
      "rules": [
        {
          "conditions": [
            {
              "key": "rejected_assignments_count",
              "operator": "GTE",
              "value": "1"
            },
            {
              "key": "assessment_event",
              "operator": "EQ",
              "value": "REJECT"
            }
          ],
          "action": {
            "type": "CHANGE_OVERLAP",
            "parameters": {
              "delta": 1,
              "open_pool": true,
            }
          }
        }
      ]
    }
  ]
}
```

#|
|| Parameter | Overview ||
|| `configs[]` | _array of objects_ \| **required**

Array of quality control settings. ||
|| `configs[].collector_config` | _object_ \| **required**

Parameters for collecting statistics (for example, the number of tasks skipped in the pool). ||
|| `configs[].collector_config.type` | _string_ \| **required**

{% include [quality-control-criteria](../_includes/quality-control-list.md) %}
||
|| `configs[].collector_config.parameters` | _object_ \| **required if**

Required if `configs[].collector_config.type` is equal to one of the values:

- `GOLDEN_SET`
- `MAJORITY_VOTE`
- `ASSIGNMENT_SUBMIT_TIME`

Parameters for collecting data (depends on the quality control rule specified in the `type` key). ||
|| `configs[].collector_config.parameters.history_size` | _integer_ \| **required**

The maximum number of the Toloker's recent responses in the project to use for calculating the percentage of correct responses.

If this field is omitted, the calculation is based on all the Toloker's responses in the pool. ||
|| `configs[].rules` | _object_ \| **required**

{% include [configs-rules](../_includes/configs-rules.md) %} ||
|| `configs[].rules.conditions` | _object_ \| **required**

Conditions (for example, 10 task suites skipped in a row). Multiple conditions are combined with the `AND` operator. ||
|| `configs[].rules.conditions.key` | _string_ \| **required**

Values that are checked in the condition:

- `pending_assignments_count` — The number of task suites that are completed and awaiting review.
- `accepted_assignments_count` — The number of task suites accepted after the review.
- `rejected_assignments_count` — The number of task suites rejected after the review. ||
|| `configs[].rules.conditions.operator` | _string_ \| **required**

Comparison operator (the `key` data is compared with the threshold value from `value`):

- `EQ` — Equal to.
- `NE` — Not equal to.
- `GT` — Greater than.
- `LT` — Less than.
- `GTE` — Greater than or equal to.
- `LTE` — Less than or equal to. ||
|| `configs[].rules.conditions.value` | _string_ \| **required**

The number of task suites with a specific status. ||
|| `configs[].rules.action` | _object_ \| **required**

The action to perform if conditions are met (for example, block access to the project). ||
|| `configs[].rules.action.type` | _string_ \| **required**

`CHANGE_OVERLAP` — Change the overlap. For example, to re-assign a task suite to other Tolokers or cancel the recompletion of accepted task suites. ||
|| `configs[].rules.action.parameters` | _object_ \| **required**

Action parameters. ||
|| `configs[].rules.action.parameters.scope` | _string_ \| **required**

Scope:

- `POOL` — pool. Affects the Toloker's rating.
- `PROJECT` — The project. Affects the Toloker's rating.
- `ALL_PROJECTS` — All the requester's projects. ||
|| `configs[].rules.action.parameters.skill_id` | _string_ \| **required if**

Required if `type=SET_SKILL_FROM_OUTPUT_FIELD`.

ID of the skill to update as tasks are completed. ||
|| `configs[].rules.action.parameters.from_field` | _string_ \| **required if**

Required if `type=SET_SKILL_FROM_OUTPUT_FIELD`.

The value to assign to the skill:

- `correct_answers_rate` — The percentage of correct responses.
- `wrong_answers_rate` — The percentage of incorrect responses. ||
|| `configs[].rules.action.parameters.skill_value` | _integer_ \| **required if**

Required if `type=SET_SKILL_FROM_OUTPUT_FIELD`.

A fixed value to assign to the skill (a number from 0 to 100). ||
|| `configs[].rules.action.parameters.delta` | _integer_ \| **required if**

Required if `type=CHANGE_OVERLAP`.

The value determines the amount to change the overlap by. ||
|| `configs[].rules.action.parameters.public_comment` | _string_ \| **required if**

Required if `type=REJECT_ALL_ASSIGNMENTS`.

Comments (the reason for rejecting responses). Available to the requester and the Toloker. ||
|| `configs[].rules.action.parameters.duration_unit` | _string_

{% include [duration-unit](../_includes/duration-unit.md) %} ||
|| `configs[].rules.action.parameters.duration` | _integer_

{% include [duration](../_includes/duration.md) %} ||
|| `configs[].rules.action.parameters.private_comment` | _string_

Comments (the reason for blocking access). Visible only to the requester. ||
|| `configs[].rules.action.parameters.open_pool` | _boolean_

Determines whether to re-open a closed pool:

- `true` — Open the pool after making changes if it is closed.
- `false` — Don't open the pool after making changes, if it is closed.||
|#

## See also {#see-also}

- [{#T}](../../guide/concepts/reassessment-after-accepting.md)
- [Toloka-Kit recipe: Use quality control rules](../../toloka-kit/recipes/use-quality-control-rules.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}