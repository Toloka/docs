# Majority vote

## Overview {#about}

Majority vote is a quality control method based on matching responses from the majority of Tolokers who complete the same task. The response chosen by the majority is considered correct, and other responses are considered incorrect. Depending on the percentage of correct responses, you can either increase the Toloker's skill value, or ban the Toloker from tasks.

The majority vote algorithm only works with the required fields of the output specification.

For majority vote verification based on Toloker responses, you can set up the following:

- Count of skill values.
- Skill value updates.
- Toloker account blocking.

To set up the verification, define key values in the `quality_control.configs` array (pool parameters).

## Request body {#body}

The pool is set up to use verification with an overlap of "5". The calculation uses tasks in which three or more Tolokers submitted the same response. The percentage of correct responses (those that match the majority vote) is stored as skill level 43. You can apply the skill for [filtering Tolokers](filter-skill.md). The skill is first calculated after two tasks that coincide with the majority vote have been completed.

You can ban a Toloker from accessing the tasks in the project for a given number of days, hours, minutes (at a time or in total) or forever.

#### Ban for 10 days

```json
{
  "configs": [
    {
      "collector_config": {
        "type": "MAJORITY_VOTE",
        "parameters": {
          "answer_threshold": 3,
          "history_size": 10
        }
      },
      "rules": [
        {
          "conditions": [
            {
              "key": "total_answers_count",
              "operator": "GT",
              "value": 2
            }
          ],
          "action": {
            "type": "SET_SKILL_FROM_OUTPUT_FIELD",
            "parameters": {
              "skill_id": "43",
              "from_field": "correct_answers_rate"
            }
          }
        },
        {
          "conditions": [
            {
              "key": "total_answers_count",
              "operator": "GTE",
              "value": 5
            },
            {
              "key": "incorrect_answers_rate",
              "operator": "GT",
              "value": 3
            }
          ],
          "action": {
            "type": "RESTRICTION_V2",
            "parameters": {
              "scope": "PROJECT",
              "duration_unit": "DAYS",
              "duration": 10,
              "private_comment": "Does not correspond to the opinion of the majority"
            }
          }
        }
      ]
    }
  ]
}
```

To set a different ban period, change the applicable [parameter](goldenset.md#configs-rules-action-parameters-duration) for the `action` key:

{% list tabs %}

- for 12 hours

    ```json
    {
      ...
        "action": {
          "type":"RESTRICTION_V2",
          "parameters": {
            "scope": "PROJECT",
            "duration_unit": "HOURS",
            "duration": 12,
            "private_comment": "Does not correspond to the opinion of the majority"
          }
        }
      ...
    }
    ```

- for 30 minutes

    ```json
    {
      ...
        "action": {
          "type":"RESTRICTION_V2",
          "parameters": {
            "scope": "PROJECT",
            "duration_unit": "MINUTES",
            "duration": 30,
            "private_comment": "Does not correspond to the opinion of the majority"
          }
        }
      ...
    }
    ```

- permanently

    ```json
    {
      ...
        "action": {
          "type":"RESTRICTION_V2",
          "parameters": {
            "scope": "PROJECT",
            "duration_unit": "PERMANENT",
            "private_comment": "Does not correspond to the opinion of the majority"
          }
        }
      ...
    }
    ```

{% endlist %}

#|
|| Parameter | Overview ||
|| **configs[]** | **array of objects \| required**

Array of quality control settings. ||
|| **configs.collector_config** | **object \| required**

Parameters for collecting statistics (for example, the number of tasks skipped in the pool). ||
|| **configs.collector_config.type** | **string \| required**

Criteria for the quality control rule:

- `GOLDEN_SET` — The number of correct and incorrect responses in the control tasks.
- `MAJORITY_VOTE` — The percentage of responses that matched the majority vote.
- `CAPTCHA` — The number of captchas entered successfully and unsuccessfully.
- `INCOME` — Payment for tasks completed by the Toloker over the past 24 hours.
- `SKIPPED_IN_ROW_ASSIGNMENTS` — The number of task suites skipped in a row.
- `ANSWER_COUNT` — The number of task suites completed by the Toloker in the pool.
- `ASSIGNMENT_SUBMIT_TIME` — The number of "fast" responses (the minimum response speed is set in the parameters).
- `ACCEPTANCE_RATE` — The percentage of Toloker responses that were rejected during manual review.
- `ASSIGNMENTS_ASSESSMENT` — The number of assignments accepted or rejected with manual review enabled.
- `USERS_ASSESSMENT` — The Toloker's skill value and their bans. ||
|| **configs.collector_config. parameters.answer_ threshold** | **integer \| required**

The number of Tolokers considered the majority (for example, 3 out of 5). ||
|| **configs.collector_config. parameters.history_size** | **integer \| required**

The maximum number of the Toloker's recent responses in the project to use for calculating the percentage of correct responses.

If this field is omitted, the calculation is based on all the Toloker's responses in the pool. ||
|| **configs.rules.conditions** | **object \| required**

Conditions (for example, 10 task suites skipped in a row). Multiple conditions are combined with the "OR" operator. ||
|| **configs.rules.conditions.key** | **string \| required**

Values that are checked in the condition:

- `total_answers_count` — The number of completed tasks that had a majority vote (specify the majority in `answer_threshold`).
- `correct_answers_rate` — The percentage of correct responses, meaning responses that matched the majority vote (from 0 to 100).
- `incorrect_answers_rate` — The percentage of incorrect responses, meaning responses that didn't match the majority vote (from 0 to 100). ||
|| **configs.rules.conditions. operator** | **string \| required**

Comparison operator (the `key` data is compared with the threshold value from `value`):

- `EQ` ("Equal") — Equal to.
- `NE` ("Not equal to") — Not equal to.
- `GT` ("Greater than") — Greater than.
- `LT` ("Less than") — Less than.
- `GTE` ("Greater than equal to") — Greater than or equal to.
- `LTE` ("Less than equal to") — Less than or equal to. ||
|| **configs.rules.conditions. value** | **integer \| required**

The threshold value of the variable specified in `key`. ||
|| **configs.rules.action** | **object \| required**

The action to perform if conditions are met (for example, block access to the project). ||
|| **configs.rules.action.type** | **string \| required**

Type of action:

- `RESTRICTION` — Ban access to projects or pools.
- `SET_SKILL_FROM_OUTPUT_FIELD` — Set the "percentage of correct responses" as the skill value (used in [control tasks](goldenset.md) and [majority vote](mv.md) rules).

    You can use the skill value for filtering Tolokers.

- `CHANGE_OVERLAP` — Change the overlap. For example, to re-assign a task suite to other Tolokers or cancel the recompletion of already accepted assignments.
- `REJECT_ALL_ASSIGNMENTS` — Reject all Toloker responses. For example, after a certain number of Toloker responses, it became clear that the Toloker completed tasks poorly.
- `APPROVE_ALL_ASSIGNMENTS` — Accept all Toloker responses. For example, if the Toloker completes most tasks well and you are satisfied with this result.
- `SET_SKILL` — Assign the specified constant value to the skill. ||
|| **configs.rules.action. parameters** | **object \| required**

Action parameters. ||
|| **configs.rules.action. parameters.scope** | **string \| required**

Scope:

- `POOL` — pool. Affects the Toloker's rating.
- `PROJECT` — The project. Affects the Toloker's rating.
- `ALL_PROJECTS` — All the requester's projects. ||
|| **configs.collector_config. parameters** | **object \| required if**

Required if `configs.collector_config.type=``GOLDEN_SET`, `MAJORITY_VOTE`, `CAPTCHA`, `ASSIGNMENT_SUBMIT_TIME`.

Parameters for collecting data (depends on the quality control rule specified in the `type` key). ||
|| **configs.rules.action. parameters.skill_id** | **string \| required if**

Required if `type=SET_SKILL_FROM_OUTPUT_FIELD`.

ID of the skill to update as tasks are completed. ||
|| **configs.rules.action. parameters.from_field** | **string \| required if**

Required if `type=SET_SKILL_FROM_OUTPUT_FIELD`.

The value to assign to the skill:

- `correct_answers_rate` — The percentage of correct responses.
- `wrong_answers_rate` — The percentage of incorrect responses. ||
|| **configs.rules.action. parameters.skill_value** | **integer \| required if**

Required if `type=SET_SKILL_FROM_OUTPUT_FIELD`.

A fixed value to assign to the skill (a number from 0 to 100). ||
|| **configs.rules.action. parameters.delta** | **integer \| required if**

Required if `type=CHANGE_OVERLAP`.
The value determines the amount to change the overlap by. ||
|| **configs.rules.action. parameters.public_comment** | **string \| required if**

Required if `type=REJECT_ALL_ASSIGNMENTS`.

Comments (the reason for rejecting responses). Available to the requester and the Toloker. ||
|| **configs.rules.action. parameters.duration_unit** | **string**

Ban duration unit:

- `MINUTES` — Minutes
- `HOURS` — Hours
- `DAYS` — Days
- `PERMANENT` — Permanent ban ||
|| **configs.rules.action. parameters.duration** | **integer**

Ban duration. ||
|| **configs.rules. action.parameters. private_comment** | **string**

Comments (the reason for blocking access). Visible only to the requester. ||
|| **configs.rules.action. parameters.open_pool** | **boolean**

Determines whether to re-open a closed pool:

- `true` — Open the pool after making changes if it is closed.
- `false` — Don't open the pool after making changes, if it is closed.||
|#

## See also {#see-also}

- [{#T}](../../guide/concepts/mvote.md)