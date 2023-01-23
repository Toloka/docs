# Setting up quality control

Quality control lets you get more accurate responses and restrict access to tasks for cheating users. Quality control consists of rules. All rules work independently.

{% note warning %}

Quality control rules that you set in the [project](../../glossary.md#project) are applied to all project [pools](../../glossary.md#pool), so you can't change them in one pool.

{% endnote %}

To set up quality control:

1. Go to the pool editing page.

1. If you already have a pool with the appropriate quality control settings, you can copy it along with the audience settings. To do this, go to {% if locale == "en-com" %}**Tolokers filter**{% endif %} and click {% if locale == "en-com" %}**Copy settings from...**{% endif %} and then {% if locale == "en-com" %}**Add Quality Control Rule**{% endif %}.

1. Under {% if locale == "en-com" %}**Quality Control**{% endif %}, choose the rules you want to use.

    If you aren't sure which quality control rules you need, use a preset with default settings.

1. Make settings for the rules you added. For more information, see the [List of rules](#id_z4l_prs_2lb).

1. Click {% if locale == "en-com" %}**Save**{% endif %}.

{% note info %}

If you already have a pool with the quality control settings you need, you can copy it along with the audience settings:

1. In the {% if locale == "en-com" %}**Audience**{% endif %} block, click the {% if locale == "en-com" %}**Copy from another pool**{% endif %} button.

1. Select a project and pool.

1. Click the {% if locale == "en-com" %}**Copy audience filters and quality control settings**{% endif %} button.

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

- [Efficiency indicators: Bans](./efficiency-metrics/ban-rate.md)
- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)

## Troubleshooting {#troubleshooting}

{% cut "Setting up quality control" %}

{% cut "How do I set quality control in a pool correctly?" %}

The settings for [quality control](../../glossary.md#quality-control) rules depend on the type of tasks. General recommendations:

- Always use one or more ways to control quality of answers.

- Counting [fast responses](quick-answers.md) makes sense for most tasks.

- If the Toloker has to choose between options (for example, by selecting checkboxes), check the answers using [majority vote](mvote.md) or [control tasks](goldenset.md).

- If the Toloker has to provide a response as a text or link or upload a photo, the best way to control quality is by [reviewing assignments](accept.md). You can outsource task acceptance to Tolokers. Create a task with a question (for example, “Is this phrase translated correctly?”) and possible responses (for example, “yes”/“no”). Set up [overlap](dynamic-overlap.md) and [majority vote](mvote.md) check.

- If a task is more like an opinion poll (for example, choosing nice pictures from a set), [majority vote](../../glossary.md#majority-vote) is not a good way to control quality. Make [control tasks](../../glossary.md#control-task) with artificial examples where the choice is evident.

{% endcut %}

{% cut "Should I create a skill for every pool?" %}

It is better to use one [skill](../../glossary.md#skill) in a project. You can choose the way to calculate the skill:

- Calculate the skill for each pool separately. The current skill value is the value of the skill in the pool the Toloker completed last. This option is convenient if:

    - The pools are intended for different groups of Tolokers (for example, there are filters by city or country).

    - Pools are started one by one and you don't want to take into account the responses in the previous pools to calculate the skill in the current pool.

    This calculation method is used by default when adding a quality control rule to a pool. For the control tasks block, leave the **Recent control and training task responses to use** field empty.

- Calculate skill based on all tasks in a project This option is good if the pools are small and you don't need to have skill calculated for each pool.

    This option is available only for skills on control tasks. To use it, fill in the **Recent control and training task responses to use** field in pool quality control rules.

{% endcut %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% cut "I set up quality control, after which I copied my Toloker requirements. All my quality control settings were deleted and replaced with the copied settings. Is that normal?" %}

Yes. When you copy the filter and quality control settings, the settings you previously added manually are overwritten. You should see a warning about this in the copy settings window.

{% endcut %}

{% include [faq-get-access](../_includes/faq/pool-setup/get-access.md) %}

{% cut "Am I correct in understanding that if I use “set the the skill value = 1“ with a “percentage of accepted responses >= 75“ and “10 recent values to use“, Tolokers will get one skill point for every eight tasks completed correctly out of ten?" %}

No, this is incorrect. With these settings, each time a rule condition is met, the Toloker gets `skill = 1`. To change the skill value in the process of task review, you need a “multi-step” rule, which has multiple identical rules with different values of **Total reviewed responses**.

{% endcut %}

{% cut "Is the time specified per task suite in the fast response settings?" %}

Yes, the [fast response](quick-answers.md) settings specify the time per task suite.

{% endcut %}

{% cut "How do I test Tolokers to see which kinds of tasks they do better and make sure that's what I have them do?" %}

You can add a [training pool](train.md) to test your Tolokers. Based on the test results, assign skills to the Tolokers for the tasks they do best.

Then limit your pools to Tolokers with a certain skill using [filters](filters.md) for this.

{% endcut %}

{% include [faq-match-entered-text](../_includes/faq/pool-setup/match-entered-text.md) %}

{% cut "I want to create an exam with three tasks. If a user does two out of three tasks correctly, they get the skill. I'm trying to put “3“ in the “Recent control and training task responses to use“ field, but I'm getting an error telling me that the value is too small. Can I get around this without increasing the number of tasks to five?" %}

The **Recent control and training task responses to use** field is for the number of recent responses from Toloker. If you use non-automatic acceptance for your task, then to set up your intended rule you need to specify `3` in **Total reviewed responses**.

{% endcut %}

{% include [faq-two-text-versions](../_includes/faq/pool-setup/two-text-versions.md) %}

{% endcut %}

{% cut "Control tasks" %}

{% include [faq-how-many-control-tasks](../_includes/faq/pool-setup/how-many-control-tasks.md) %}

{% include [faq-correct-responses-counted](../_includes/faq/pool-setup/correct-responses-counted.md) %}

{% cut "Can I make my training or control tasks totally different from the general tasks?" %}

Your [training](train.md) and control tasks have the same project specification. However, you can create a separate project with the tasks and assign a skill based on user responses. Then you can admit Tolokers to the main project based on their skill.

{% endcut %}

{% cut "Isn't the exam a regular pool that I pay for? How does it differ from a regular pool?" %}

An exam pool contains only control tasks. They're usually small, only intended to make sure Tolokers know how to complete your tasks after reading the instructions and completing the [training](additionals-q.md#selection). Unlike your main pool, you already know the correct responses for every task in this pool. You can set the price to zero.

Based on the results of the control tasks, you can assign a skill to Tolokers and then use it in the main pool as a filter. For example, `MySkill = 80 or = Is missing`. You don't have to create an exam. For simple tasks, the training pool provides enough practice, but many requesters also use exams.

{% endcut %}

{% include [faq-set-up-exam](../_includes/faq/pool-setup/set-up-exam.md) %}

{% include [faq-using-smart-mixing](../_includes/faq/adding-tasks-to-the-pool/using-smart-mixing.md) %}

{% cut "Can I create two active training pools, one for practice and the other for admitting users to the main pool? In other words, one pool is for users to practice and the other pool tests them." %}

Yes, you can do that. In this case, create the first pool based on the [training pool](../../glossary.md#training-pool) and the exam pool based on your main pool. If a pool contains only control and/or training tasks, the price can be set to zero.

In the exam pool, you can create a skill reflecting the exam result and granting admission to the main pool. For example, `if the number of responses is ≥ 10, set the skill value in the <exam skill> as % of correct responses`. Here are the requirements you should use for Tolokers in the exam pool: `<skill being tested for> < 80 or = none>`. In the main pool, set up a filter: `<exam skill> >= 80 and (<main skill> >= 70 or = Is missing)`. You can choose the skill values depending on how well the Tolokers perform your task.

{% endcut %}

{% cut "I created a training pool with one task containing a hint. A Toloker makes a mistake on their first attempt but eventually succeeds. The Toloker gets the skill “0“. How do I grant to the Toloker access to my tasks? The minimum required level that you can set is “10“." %}

Technically, if you have only one task in your training pool, you don't have this option. The skill will be either `0` or `100`. We recommend that you add several tasks, or at least 2 so that the Toloker will practice on the first task and will be able to do the second task correctly. In this case, you can admit users to your main pool starting from the skill value of `50`.

You can also create a training pool based on the main pool. Assign a skill using the [Control tasks](goldenset.md) rule, in which case, you can admit Tolokers to your main pool with any skill level, zero included. But we don't advise giving tasks to people who failed training.

{% endcut %}

{% cut "In the section about control questions, does "Number of control responses" mean the total number of responses to control questions (including incorrect responses) or the number of correct responses to my control questions?" %}

This is the total number of responses to the control questions.

{% endcut %}

{% cut "Can I use non-automatic acceptance in the training pool?" %}

No. But you can create a pool of the **Training** type based on your main pool and enable non-automatic acceptance there.

{% endcut %}

{% cut "Can the Tolokers see which questions are control tasks?" %}

No, they can't.

{% endcut %}

{% include [troubleshooting-export](../_includes/troubleshooting/pool-setup/export.md) %}

{% endcut %}

{% cut "Ban" %}

{% include [faq-disable-tasks](../_includes/faq/result-questions/disable-tasks.md) %}

{% include [faq-incorrect-responses](../_includes/faq/pool-setup/incorrect-responses.md) %}

{% cut "If I ban Tolokers from my project so that everyone can complete a maximum of one task, will they be notified?" %}

No, Tolokers don't know when they're blocked.

{% endcut %}

{% cut "If I ban a Toloker for doing my tasks too fast, will all their responses be deleted and given to other Tolokers for labeling?" %}

No. The responses of these Tolokers aren't automatically excluded from the final results file.

But you can do it yourself if you want. When downloading the results, select the option **Exclude assignments by banned users** to delete the responses of Tolokers who were banned at the moment of downloading. You can also forward all the assignments from banned Tolokers to other Tolokers using the [Re-completion of assignments from banned users](restore-task-overlap.md) rule.

{% endcut %}

{% cut "How do I classify users as good Tolokers and poor Tolokers as they complete tasks, and ban the poor Tolokers?" %}

You can create a task pool for all your Tolokers and create Toloker skills in it. In this case, you can open your tasks only to the Tolokers with the necessary skills.

{% endcut %}

{% endcut %}

{% cut "Majority vote" %}

{% include [faq-submit-empty-assignments](../_includes/faq/pool-setup/submit-empty-assignments.md) %}

{% include [faq-multiple-fields](../_includes/faq/pool-setup/multiple-fields.md) %}

{% cut "Which format should I use to review results if I'm looking to filter out mismatching Tolokers based on the "Majority vote"?" %}

To assign a skill to or ban Tolokers based on the majority vote, add a relevant [rule](mvote.md) to the pool.

Don't forget to enable **Keep task order** in the pool parameters. Majority vote is used in the projects with preset options (radio buttons or checkboxes). This rule won't apply to the text entry or file upload fields.

{% endcut %}

{% endcut %}

{% cut "Speed of task completion" %}

{% cut "Why has the speed of pool completion dropped?" %}

Possible reasons:

- You've stopped the [main pool](../../glossary.md#training-pool). This could limit the number of Tolokers with access to the pool. Start the training pool again. There will be more Tolokers who can access the tasks.

- The filters you set are too strict. For example, a strong restriction on a certain skill that most Tolokers don't have.

- Too many Tolokers are banned. Ease the quality control rules.

{% endcut %}

{% cut "How can I speed up the pool completion?" %}

- To motivate Tolokers, assign a [public skill](nav-create.md#public) and use [dynamic pricing](dynamic-pricing.md).

- Try to [increase the project rating](project_rating_stat.md), so that your task is higher in the list of tasks for Tolokers.

- Adjust the [quality-speed ratio](adjust.md).

- Set a higher [priority](pool_poolparams.md#priority) for the pool among other project pools.

{% endcut %}

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}