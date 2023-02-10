# Quality control rules

Quality control rules allow you to get more accurate responses and restrict access to tasks to cheating Tolokers. All rules work independently.

## List of rules {#rules}

- **To keep track of how often Tolokers make mistakes:**

    - [Control tasks](goldenset.md): Use them to assign a [skill](../../glossary.md#skill) to Tolokers based on their responses to control tasks and ban Tolokers who submit incorrect responses.

    - [Majority vote](mvote.md): Quality is based on matching the response from the majority of Tolokers who complete the same task.

    - [Results of checking](reviewing-assignments.md): Evaluate Tolokers based on the number of accepted and rejected responses.

- **To protect your project from robots and cheaters:**

    - [Fast responses](quick-answers.md): Control the minimum time that must be spent per [task suite](../../glossary.md#task-suite).

    - [Skipped assignments](skipped-assignments.md): Restrict access to your pool tasks for Tolokers who [skip multiple assignments](pool_statistic-pool.md#skipped-tasks) in a row.

- **To attract a variety of Tolokers:**

    - [Earnings](income.md): Limit the amount each Toloker can earn in the [pool](../../glossary.md#pool) per day.

    - [Submitted assignments](submitted-answers.md): Limit how many assignments each Toloker can submit in the pool per day.

- **To allow recompletion of certain assignments:**

    - [Recompletion of assignments from banned users](restore-task-overlap.md): Send [completed assignments](../../glossary.md#completed-tasks) to other Tolokers to redo them if the Toloker was banned.

    - [Processing of rejected and accepted assignments](reassessment-after-accepting.md): Send rejected assignments to other Tolokers to redo them.

## Quality control presets {#rule-set}

Toloka has presets of quality control rules. Currently, there are three of them:

- **Elementary** — suitable for requesters who need tasks to be completed by a large number of Tolokers in a short time.

- **Basic** — suitable for those who need to balance quality and quantity.

- **Advanced** — a set with a large number of rules required for complex tasks.

The table shows the rules included in each of the sets.

|                | Earnings | Skipped assignments | Control tasks | Majority vote | Submitted answers | Fast responses |
|----------------|----------|---------------------|---------------|---------------|-------------------|----------------|
| **Elementary** | +        | +                   | −             | −             | −                 | -              |
| **Basic**      | +        | +                   | +             | +             | −                 | -              |
| **Advanced**   | +        | +                   | +             | +             | +                 | +              |

## How to set up quality control {#control_how}

You can configure quality control in the [pool](qa-pool-settings.md) and in the [project](project-qa.md).

{% list tabs %}

- Pool

  Go to pool editing (click ![](../_images/location-job/project/edit-project.svg) in the upper-right corner of the page) and click **Add Quality Control Rule** in the **Quality control** section.

  You can copy quality control settings from another pool. To do this, click **Copy audience filters and quality control settings** in the **Audience** section.

- Project

  Open the project page, open the **Quality control** tab and click **Set quality control**. Then click **+ Add Quality Control Rule**.

  The rules are applied to all project pools, so you can't change settings in just one of the pools.

  {% note alert "Restriction" %}

  When you [clone a project](project.md), its quality control settings aren't transferred.

  {% endnote %}

{% endlist %}

## See also {#see-also}

- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)

## For developers {#for-developers}

- [Toloka API: Quality control rules](../../api/concepts/quality_control.md)
- [Toloka-Kit: QualityControl class](../../toloka-kit/reference/toloka.client.quality_control.QualityControl.md)

## Troubleshooting {#troubleshooting}

{% cut "Setting up quality control" %}

{% include [faq-set-quality-control](../_includes/faq/pool-setup/set-quality-control.md) %}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [troubleshooting-control-settings-replaced](../_includes/troubleshooting/pool-setup/control-settings-replaced.md) %}

{% include [faq-time-specified](../_includes/faq/pool-setup/time-specified.md) %}

{% include [faq-set-skill](../_includes/faq/pool-setup/set-skill.md) %}

{% endcut %}

{% cut "Overlap" %}

{% include [faq-overlap](../_includes/faq/pool-setup/overlap.md) %}

{% include [faq-specific-number](../_includes/faq/pool-setup/specific-number.md) %}

{% include [faq-change-overlap](../_includes/faq/pool-setup/change-overlap.md) %}

{% endcut %}

{% cut "Banning Tolokers" %}

{% include [faq-submit-empty-assignments](../_includes/faq/pool-setup/submit-empty-assignments.md) %}

{% include [faq-incorrect-responses](../_includes/faq/pool-setup/incorrect-responses.md) %}

{% include [faq-get-access](../_includes/faq/pool-setup/get-access.md) %}

{% include [faq-ban](../_includes/faq/pool-setup/ban.md) %}

{% include [faq-one-task](../_includes/faq/pool-setup/one-task.md) %}

{% endcut %}

{% cut "Majority vote" %}

{% include [faq-output-format](../_includes/faq/pool-setup/output-format.md) %}

{% include [faq-multiple-fields](../_includes/faq/pool-setup/multiple-fields.md) %}

{% endcut %}

{% cut "Control tasks" %}

{% include [faq-how-many-control-tasks](../_includes/faq/pool-setup/how-many-control-tasks.md) %}

{% include [faq-using-smart-mixing](../_includes/faq/adding-tasks-to-the-pool/using-smart-mixing.md) %}

{% include [faq-correct-responses-counted](../_includes/faq/pool-setup/correct-responses-counted.md) %}

{% include [faq-hint](../_includes/faq/pool-setup/hint.md) %}

{% include [faq-questions-are-control](../_includes/faq/pool-setup/questions-are-control.md) %}

{% include [troubleshooting-export](../_includes/troubleshooting/pool-setup/export.md) %}

{% include [faq-number-of-control-responses](../_includes/faq/pool-setup/number-of-control-responses.md) %}

{% include [faq-classify-users](../_includes/faq/pool-setup/classify-users.md) %}

{% include [faq-make-different](../_includes/faq/pool-setup/make-different.md) %}

{% include [faq-exam-pool](../_includes/faq/pool-setup/exam-pool.md) %}

{% include [faq-set-up-exam](../_includes/faq/pool-setup/set-up-exam.md) %}

{% include [faq-test-tolokers](../_includes/faq/pool-setup/test-tolokers.md) %}

{% include [faq-two-training-pools](../_includes/faq/pool-setup/two-training-pools.md) %}

{% include [troubleshooting-exam-three-tasks](../_includes/troubleshooting/pool-setup/exam-three-tasks.md) %}

{% endcut %}

{% cut "Speed of task completion" %}

{% include [troubleshooting-speed-dropped](../_includes/troubleshooting/pool-setup/speed-dropped.md) %}

{% include [faq-labeling-speed](../_includes/faq/project-settings/labeling-speed.md) %}

{% include [faq-speed-up-completion](../_includes/faq/pool-setup/speed-up-completion.md) %}

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}