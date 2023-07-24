# Setting up quality control

{% include [toloka-requester-source-quality-control](../_includes/toloka-requester-source/id-toloka-requester-source/quality-control.md) %}

{% note warning %}

Quality control rules that you set in the [project](../../glossary.md#project) are applied to all project [pools](../../glossary.md#pool), so you can't change them in one pool.

{% endnote %}

To set up quality control:

1. Go to the pool editing page.

1. If you already have a pool with the appropriate quality control settings, you can copy it along with the audience settings. To do this, go to **Tolokers filter** and click **Copy settings from...** and then **Add Quality Control Rule**.

1. Under **Quality Control**, choose the rules you want to use.

    If you aren't sure which quality control rules you need, use a preset with default settings.

1. Make settings for the rules you added. For more information, see the [List of rules](#id_z4l_prs_2lb).

1. Click **Save**.

{% note info %}

If you already have a pool with the quality control settings you need, you can copy it along with the audience settings:

1. In the **Audience** block, click the **Copy from another pool** button.

1. Select a project and pool.

1. Click the **Copy audience filters and quality control settings** button.

{% endnote %}

## List of rules {#id_z4l_prs_2lb}

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

## What's next {#what_next}

- [Add tasks](pool.md) to the pool.
- Learn more about how to set up a pool:

    - [Setting up pricing](dynamic-pricing.md).
    - [Dynamic overlap](dynamic-overlap.md).
    - Selective [majority vote](selective-mvote.md) control.
    - [Filters](filters.md).
    - [Speed/quality balance](adjust.md).
    - [Reviewed assignments](offline-accept.md).

## See also {#see-also}

- [Efficiency indicators: Bans](efficiency-metrics/ban-rate.md)
- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)

## Troubleshooting {#troubleshooting}

{% cut "Setting up quality control" %}

{% include [faq-set-quality-control](../_includes/faq/pool-setup/set-quality-control.md) %}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [troubleshooting-control-settings-replaced](../_includes/troubleshooting/pool-setup/control-settings-replaced.md) %}

{% include [faq-get-access](../_includes/faq/pool-setup/get-access.md) %}

{% include [faq-set-skill](../_includes/faq/pool-setup/set-skill.md) %}

{% include [faq-time-specified](../_includes/faq/pool-setup/time-specified.md) %}

{% include [faq-test-tolokers](../_includes/faq/pool-setup/test-tolokers.md) %}

{% include [faq-match-entered-text](../_includes/faq/pool-setup/match-entered-text.md) %}

{% include [troubleshooting-exam-three-tasks](../_includes/troubleshooting/pool-setup/exam-three-tasks.md) %}

{% include [faq-two-text-versions](../_includes/faq/pool-setup/two-text-versions.md) %}

{% endcut %}

{% cut "Control tasks" %}

{% include [faq-how-many-control-tasks](../_includes/faq/pool-setup/how-many-control-tasks.md) %}

{% include [faq-correct-responses-counted](../_includes/faq/pool-setup/correct-responses-counted.md) %}

{% include [faq-make-different](../_includes/faq/pool-setup/make-different.md) %}

{% include [faq-exam-pool](../_includes/faq/pool-setup/exam-pool.md) %}

{% include [faq-set-up-exam](../_includes/faq/pool-setup/set-up-exam.md) %}

{% include [faq-using-smart-mixing](../_includes/faq/adding-tasks-to-the-pool/using-smart-mixing.md) %}

{% include [faq-two-training-pools](../_includes/faq/pool-setup/two-training-pools.md) %}

{% include [faq-hint](../_includes/faq/pool-setup/hint.md) %}

{% include [faq-number-of-control-responses](../_includes/faq/pool-setup/number-of-control-responses.md) %}

{% include [faq-review-training](../_includes/faq/pool-setup/review-training.md) %}

{% include [faq-questions-are-control](../_includes/faq/pool-setup/questions-are-control.md) %}

{% endcut %}

{% cut "Ban" %}

{% include [faq-disable-tasks](../_includes/faq/result-questions/disable-tasks.md) %}

{% include [faq-incorrect-responses](../_includes/faq/pool-setup/incorrect-responses.md) %}

{% include [faq-one-task](../_includes/faq/pool-setup/one-task.md) %}

{% include [faq-ban](../_includes/faq/pool-setup/ban.md) %}

{% include [faq-classify-users](../_includes/faq/pool-setup/classify-users.md) %}

{% endcut %}

{% cut "Majority vote" %}

{% include [faq-submit-empty-assignments](../_includes/faq/pool-setup/submit-empty-assignments.md) %}

{% include [faq-multiple-fields](../_includes/faq/pool-setup/multiple-fields.md) %}

{% include [faq-format-review-results](../_includes/faq/pool-setup/format-review-results.md) %}

{% endcut %}

{% cut "Speed of task completion" %}

{% include [troubleshooting-speed-dropped](../_includes/troubleshooting/pool-setup/speed-dropped.md) %}

{% include [faq-labeling-speed](../_includes/faq/project-settings/labeling-speed.md) %}

{% include [faq-speed-up-completion](../_includes/faq/pool-setup/speed-up-completion.md) %}

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}