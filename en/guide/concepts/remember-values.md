# "Remember values" parameter

Some quality control rules have the **Remember values** parameter. It sets the dynamic window equal to N, which the values are recalculated within. Depending on the rule, the dynamic window is measured:

- In tasks: the [Review results](reviewing-assignments.md) and [Majority vote](mvote.md) rules, the **Recent tasks to use** field.
- In [control tasks](../../glossary.md#control-task-ru): the [Control tasks](goldenset.md) rule, the **Recent control and training task responses to use** field.
- In [task suites](../../glossary.md#task-page-ru): the [Fast responses](quick-answers.md) rule, the **Recent task suites to use** field.
- In [captcha entries](../../glossary.md#captcha-rule-ru): the [Captcha](captcha.md) rule, the ** Recent captchas to use** field.

## How it works {#how-field-works}

The **Remember values** parameter works the same way for all rules.

Let's see how this parameter works with the [Control tasks](goldenset.md) rule. Go to the project or [pool](../../glossary.md#pool-ru) settings and select this quality control rule.

In our example, the **Remember values** parameter is set in the **Recent control and training task responses to use** field.

#### The field is not filled in

Toloka calculates all responses to control tasks only in the pool to which the rule applies.

#### Example
The Toloker completes several tasks in pool A, where the rule calculates their skill. Then the Toloker goes to pool B with the same rule, where the field is also not filled in. In this case, the skill is calculated for pool B separately. The rule in pool B knows nothing about the Toloker's responses in pool A.

#### The field is filled in

Toloka calculates responses to control tasks not only in the pool to which the rule applies. Responses from other pools where the **Recent control and training task responses to use** field is filled in are also taken into account .

#### Examples

- The Toloker completes pool A, where the field value is set to N = 10. Toloka calculates their skill in the pool using the last 10 responses to control tasks.
- Then the Toloker goes to pool B, where the field in the same rule is not filled in. Toloka forgets the history of the Toloker's responses in pool A and starts calculating their skill only within pool B.
- Then the Toloker goes to pool C, where the field value is set to N = 20. Toloka forgets about pool B but remembers the Toloker's responses in pool A and continues to calculate their skill using the last 20 responses to control tasks.

#### Example 1 with skill setting

What does this mean?

- When the Toloker gives 3 responses to control tasks, the skill is set to the percentage of correct responses. With each next completed task, the skill is recalculated.
- The history only stores the Toloker's last 10 responses to control tasks. As soon as they complete the 11th control task, the response to the first control task is forgotten.

#### Learn more

The rule conditions set in the pool:

- Condition 1: **Recent control and training task responses to use** = 10.
- Condition 2: **Number of responses** >= 3.
- Condition 3: Assign a skill as soon as condition 2 triggers and recalculate this skill within condition 1.


Task
 | Correct response to the control task |
Skill change
 |
Overview

----- | ----- | ----- | -----
1 | 1 |  | Condition 1 (Toloka starts saving responses).
2 | 0 |  | Condition 1 (Toloka continues saving responses).
3 | 1 | 66% — 2 out of 3 correct responses | Condition 1 (within the last 10 tasks), condition 2 (if at least three tasks are completed), condition 3 (assign a skill).
4 | 1 | 75% — 3 out of 4 correct responses | Condition 1 (within the last 10 tasks), condition 2 (if at least three tasks are completed), condition 3 (assign a skill).
5 | 0 | 60% — 3 out of 5 correct responses | Condition 1 (within the last 10 tasks), condition 2 (if at least three tasks are completed), condition 3 (assign a skill).
6 | 1 | 66% — 4 out of 6 correct responses | Condition 1 (within the last 10 tasks), condition 2 (if at least three tasks are completed), condition 3 (assign a skill).
7 | 1 | 71% — 5 out of 7 correct responses | Condition 1 (within the last 10 tasks), condition 2 (if at least three tasks are completed), condition 3 (assign a skill).
8 | 0 | 62% — 5 out of 8 correct responses | Condition 1 (within the last 10 tasks), condition 2 (if at least three tasks are completed), condition 3 (assign a skill).
9 | 0 | 55% — 5 out of 9 correct responses | Condition 1 (within the last 10 tasks), condition 2 (if at least three tasks are completed), condition 3 (assign a skill).
10 | 0 | 50% — 5 out of 10 correct responses | Condition 1 (within the last 10 tasks), condition 2 (if at least three tasks are completed), condition 3 (assign a skill).
11 | 1 | 50% — 5 out of 10 correct responses | Condition 1 (within the last 10 tasks; then Toloka forgets the first response), condition 2 (if at least three tasks are completed), condition 3 (continue calculating the skill).
12 | 1 | 60% — 6 out of 10 correct responses | Condition 1 (within the last 10 tasks; Toloka doesn't remember the first two responses), condition 2 (if at least three tasks are completed), condition 3 (continue calculating the skill).

#### Example 2 with bans

The rule works as in Example 1 with the exception that:

- The Toloker isn't assigned a skill. Toloka performs all calculations "remotely".
- After each completed control task, it checks whether the percentage of correct responses is more than 60 or not. If not, it bans the Toloker.

With this rule, it's difficult to understand why the Toloker was banned because you can't see how their skill changes. Therefore, we often use a combination of two rules (Example 3).

#### Example 3 with skill setting and bans

The rule works both as in Example 1 and Example 2.

#### Example 4 with skill setting, bans, and different parameters

With these settings, it's difficult to understand why the Toloker is banned if they have a high skill level.

#### Learn more

The rule conditions set in the pool:

- Condition 1: **Recent control and training task responses to use** = 5.
- Condition 2: **Number of responses** >= 4.
- Condition 3: When condition 2 is triggered, check the percentage of correct responses within condition 1 and recalculate it.
- Condition 4: Ban the Toloker if, under condition 3, the percentage of correct responses is below 60.
- Condition 5: **Recent control and training task responses to use** = 10.
- Condition 6: **Number of responses** >= 3.
- Condition 3: Assign a skill when condition 6 triggers and recalculate this skill within condition 5.


Task
 | Correct response to the control task |
Ban check
 |
Skill change
 |
Comment on the ban
 |
Comment on the skill

----- | ----- | ----- | ----- | ----- | -----
1 | 1 |  |  | Condition 1 (Toloka starts saving responses). | Condition 5 (Toloka starts saving responses).
2 | 1 |  |  | Condition 1 (Toloka continues saving responses). | Condition 5 (Toloka continues saving responses).
3 | 0 |  | 66% — 2 out of 3 correct responses | Condition 1 (Toloka continues saving responses). | Condition 5 (within the last 10 responses to control tasks), condition 6 (if at least three control tasks are completed), condition 7 (assign a skill).
4 | 1 | 75% — 3 out of 4 correct responses | 75% — 3 out of 4 correct responses | Condition 1 (within the last 5 responses to control tasks), condition 2 (if at least four control tasks are completed), condition 3 (check the percentage of correct responses). | Condition 5 (within the last 10 responses to control tasks), condition 6 (if at least three control tasks are completed), condition 7 (recalculate skill).
5 | 1 | 80% — 4 out of 5 correct responses | 75% — 3 out of 4 correct responses | Condition 1 (within the last 5 responses to control tasks), condition 2 (if at least four control tasks are completed), condition 3 (check the percentage of correct responses). | Condition 5 (within the last 10 responses to control tasks), condition 6 (if at least three control tasks are completed), condition 7 (recalculate skill).
6 | 1 | 80% — 4 out of 5 correct responses | 83% — 5 out of 6 correct responses | Condition 1 (within the last 5 responses to control tasks; then Toloka forgets the first response), condition 2 (if at least four control tasks are completed), condition 3 (check the percentage of correct responses). | Condition 5 (within the last 10 responses to control tasks), condition 6 (if at least three control tasks are completed), condition 7 (recalculate skill).
7 | 1 | 80% — 4 out of 5 correct responses | 85% — 6 out of 7 correct responses | Condition 1 (within the last 5 responses to control tasks; Toloka doesn't remember the first two responses), condition 2 (if at least four control tasks are completed), condition 3 (check the percentage of correct responses). | Condition 5 (within the last 10 responses to control tasks), condition 6 (if at least three control tasks are completed), condition 7 (recalculate skill).
8 | 1 | 100% — 5 out of 5 correct responses | 87% — 7 out of 8 correct responses | Condition 1 (within the last 5 responses to control tasks; Toloka doesn't remember the first three responses), condition 2 (if at least four control tasks are completed), condition 3 (check the percentage of correct responses). | Condition 5 (within the last 10 responses to control tasks), condition 6 (if at least three control tasks are completed), condition 7 (recalculate skill).
9 | 0 | 80% — 4 out of 5 correct responses | 77% — 7 out of 9 correct responses | Condition 1 (within the last 5 responses to control tasks; Toloka doesn't remember the first four responses), condition 2 (if at least four control tasks are completed), condition 3 (check the percentage of correct responses). | Condition 5 (within the last 10 responses to control tasks), condition 6 (if at least three control tasks are completed), condition 7 (recalculate skill).
10 | 0 | 60% — 3 out of 5 correct responses | 70% — 7 out of 10 correct responses | Condition 1 (within the last 5 responses to control tasks; Toloka doesn't remember the first five responses), condition 2 (if at least four control tasks are completed), condition 3 (check the percentage of correct responses). | Condition 5 (within the last 10 responses to control tasks), condition 6 (if at least three control tasks are completed), condition 7 (recalculate skill).
11 | 1 | 60% — 3 out of 5 correct responses | 70% — 7 out of 10 correct responses | Condition 1 (within the last 5 responses to control tasks; Toloka doesn't remember the first six responses), condition 2 (if at least four control tasks are completed), condition 3 (check the percentage of correct responses). | Condition 5 (within the last 10 responses to control tasks; then Toloka forgets the first response), condition 6 (if at least three control tasks are completed), condition 7 (recalculate skill).
12 | 0 | 40% — 2 out of 5 correct responses | 70% — 7 out of 10 correct responses | Condition 1 (within the last 10 responses to control tasks; Toloka doesn't remember the first seven responses), condition 2 (if at least three control tasks are completed), condition 3 (continue calculating skill), condition 4 (ban the Toloker if quality is lower than 60%). | Condition 5 (within the last 10 responses to control tasks; Toloka doesn't remember the first two responses), condition 6 (if at least three control tasks are completed), condition 7 (recalculate skill).


After completing the 12th task, the Toloker will have 60% of correct responses and will be blocked for poor quality.

{% note info %}

- If you have previously filled in the **Recent control and training task responses to use** field, you can't change it to empty. But you can delete the rule and create a new one.
- All rules work independently, even if they are united by one entity.

{% endnote %}


## How to clear the Toloker's response history {#clear-history}

The Toloker's response history will be cleared under the following conditions:

- Ban — within the dynamic window if the **Recent control and training task responses to use** field is filled in, or within the entire pool if the field is not filled in.
- Pause on pool — within the entire pool if the field is not filled in.

When the ban or pause is lifted and the Toloker starts performing tasks, the calculation will start again without taking into account previously completed tasks.

{% note warning %}

Only the history of the rule which triggered the ban will be cleared.

{% endnote %}
