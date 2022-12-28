# Overview

To improve quality of answers, you must [select the audience](filters.md) you need and [train](train.md) it.

![](../_images/other/quality-control.svg)

## Selecting the audience {#audience-select}

### Filters {#audience-filters}

- [Demographics](filters.md#filter-user-profile) (age, gender, education, languages, region, citizenship).

- [Device specs](filters.md#filter-calc-data) (device type, OS and browser version).

- [Skills](filters.md#filter-skill) (quality on specific [tasks](../../glossary.md#task)).

- Top \% of the best on the platform.

{% cut "Filter example" %}

![](../_images/other/quality-control-2.png)

{% endcut %}

### Training and onboarding {#audience-training}

- Correct answers + hints.

- High scores continue on to the [exam](../../glossary.md#exam).

### Exam {#audience-exam}

- Scored by \% correct answers.

- Best scores grant access to paid tasks.

## Multi-level quality checks {#quality-checks}

### Quality control {#quality-control}

- [Overlap](overlap-faq.md) (including dynamic overlap).

- [Control tasks](goldenset.md).

- [Majority vote](mvote.md).

- Validation by other annotators.

### Protection from cheaters and bots {#protection-from-cheaters}

- [Ban](ban.md) for [fast responses](quick-answers.md).

- [Captcha](captcha.md).

- Limit [skipped assignments](skipped-assignments.md).

- Limit number of tasks per person.

{% cut "Examples of the quality control rules" %}

{% cut "Fast responses" %}

![](../_images/control-rules/quick-answers/qcr-quick_answers_example1.png)

A Toloker who completes a [task suite](../../glossary.md#task-suite) in less than 10 seconds will be banned and won't be able to access your tasks.

{% endcut %}

{% cut "Skipped assignments" %}

![](../_images/control-rules/skipped-assignments/qcr-skipped_assignments_example1.png)

A Toloker who skips 2 task suites in a row is restricted from accessing the pool and can't complete your tasks for 5 days.

{% endcut %}

{% endcut %}

### Anti-Fraud system {#anti-fraud}

- Behavior analysis system.

- Platform-wide ban for fraudulent Tolokers.

## Obtaining quality results after data labeling {#obtaining-results}

![](../_images/results/aggregation-scheme.svg)

### Aggregating results {#aggregating-results}

- Using [majority vote](mvote.md).

- Using the [Dawid-Skene method](result-aggregation.md#dawid-skene).

- [By skill level](result-aggregation.md#aggr-by-skill).

### Evaluating metrics {#evaluating-metrics}

- Accuracy\/completeness/F1/MCC, etc.

- Consistency.

- Confidence.

### Reassigning tasks {#reassigning-tasks}

- If the submitted task is rejected.

- If consistency is low.

- If answers from banned Tolokers are thrown out.

## Main project scenarios {#main-project-scenarios}

### Validate results {#validate-results}

- [Control tasks](goldenset.md) — set the Toloker’s skill level based on answers in control tasks and exclude Tolokers who give the wrong answers.

- [Majority vote](mvote.md) — have multiple Tolokers do the same task and look for consistency in answers.

- Manually check results — evaluate Tolokers by the number of accepted and rejected tasks.

### Diversify the audience {#diversify-audience}

- [Earnings](income.md) — limit the earnings per person in your [pool](../../glossary.md#pool) in 24 hours.

- Completed tasks — limit the number of tasks per person in your pool in 24 hours.

### Prevent random clicking and bots {#random-clicking}

- [Fast responses](quick-answers.md) — monitor the minimum time to complete a [task suite](../../glossary.md#task-suite).

- [Captcha](captcha.md) — periodically display a [captcha](../../glossary.md#captcha) to catch automated scripts and bots.

- [Skipped assignments](skipped-assignments.md) — exclude Tolokers who skip too many tasks in a row.

### Redo certain tasks {#redo-tasks}

- [Re-assign tasks](restore-task-overlap.md) completed by someone who was banned — if a Toloker gets banned, all their completed tasks can be automatically assigned to other people.

- [Rejected and accepted task processing](reassessment-after-accepting.md) — set the rules for assigning rejected tasks to other people.

## Technologies for quality management {#quality-management-tech}

Transform the crowd into computing power with advanced technologies for quality management.

### Multiple quality control methods {#multiple-quality}

Toloka offers different approaches to achieve the best quality for each [project](../../glossary.md#project).

- Post-verification.

- Task-based crowd training and testing.

- Golden sets (honeypots) to monitor quality.

- Advanced [aggregation](result-aggregation.md) tools.

- Platform-wide anti-fraud system.

### Adaptive selection of Tolokers {#adaptive-selection}

Multi-stage selection of a distributed crowd.

- Audience [filters](filters.md) by language, age, gender, interests, location, real-time ranking, and more.

- [Training](train.md), [exams](how-to-use-exams.md), and retraining to find Tolokers for your exact task.

### Smart matching mechanisms {#smart-matching}

Patent-pending matching system that honors the preferences of requesters and Tolokers for mutual benefit.

- Invite Tolokers to a project who are most qualified to handle it.

- Offer Tolokers personalized recommendations of interesting projects they will enjoy.

### Autolabeling \& verification (on demand) {#autolabeling-verification}

Autolabeling and pretrained models with quality control built in.

- Automated prelabeling. Results are verified by human Tolokers for high accuracy.

- Human in the loop workflows.

## What's next {#what_next}

- [Set up quality control](qa-pool-settings.md).
- [Add tasks](pool.md) to the pool.
- [Start the pool](pool-run-and-stop.md).

## See also {#see-also}

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

{% cut "Can I use a skill beyond a particular pool or project and apply it to other projects as well?" %}

Yes, of course — you can use the same skill for different projects. But most often, a skill is intended for a specific project. If the Toloker completes a certain task well, this doesn't mean that they will complete other ones successfully. Another disadvantage is that if you filter by skills that were set long ago, you will artificially limit the number of available Tolokers.

{% endcut %}

{% cut "I set up quality control, after which I copied my Toloker requirements. All my quality control settings were deleted and replaced with the copied settings. Is that normal?" %}

Yes. When you copy the filter and quality control settings, the settings you previously added manually are overwritten. You should see a warning about this in the copy settings window.

{% endcut %}

{% cut "Can one Toloker get access to two pools in the same project? Can I avoid that?" %}

Yes, if they can access both pools, they can do both of them. To restrict access to subsequent tasks for a Toloker, use the [Completed tasks](submitted-answers.md) rule and select a ban at the project level.

{% endcut %}

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

{% cut "I want to create training and exam pools to match the entered text against a sample, and sometimes the matching fails. How do I implement this?" %}

For a control or training assignment to be counted as correct, it must exactly match the control assignment. To do this, you need to normalize the response text using JavaScript: remove spaces, punctuation marks, special characters, and capital letters, and write the result in a separate output field. Now you can match the processed assignment text against your control text.

Another option for selecting Tolokers for a project of this type is assignment review (non-automatic acceptance).

{% endcut %}

{% cut "I want to create an exam with three tasks. If a Toloker does two out of three tasks correctly, they get the skill. I'm trying to put “3“ in the “Recent control and training task responses to use“ field, but I'm getting an error telling me that the value is too small. Can I get around this without increasing the number of tasks to five?" %}

The **Recent control and training task responses to use** field is for the number of recent responses from Toloker. If you use non-automatic acceptance for your task, then to set up your intended rule you need to specify `3` in **Total reviewed responses**.

{% endcut %}

{% cut "I have two text versions that I want to show to my respondents: one version to half of the audience, and another version to the other half (like in A/B testing). Is this possible in Toloka, or do I need to create two separate projects?" %}

If you pass texts to the input data, you can load 2 different tasks in the pool. In one task, pass Text 1 in the `INPUT: <input field name>` field, and in the other task, use this field to pass Text 2. But if the text is in the HTML block of the task template, you need to clone the project. To let a Toloker do only one task in your project, use the [Submitted responses](submitted-answers.md) rule. You can assign a skill or ban the Toloker after they submit one response.

{% endcut %}

{% endcut %}

{% cut "Control tasks" %}

{% cut "How many control tasks do I need to add?" %}

We recommend adding at least 1% of control tasks in the pool. And for small pools — 5–10%.

{% cut "Why's that?" %}

Each control task is shown to the Toloker only once. If you use smart mixing, you determine how many control tasks should be in a suite. If each suite contains one control task, then the maximum number of suites the Toloker can complete is equal to the number of control tasks in the pool. If you increase the number of control tasks in a suite, the number of suites available to the Toloker decreases by the same number.

There shouldn't be too few pages available. Otherwise:

- You won't be able to correctly evaluate the quality of the Toloker's responses.
- The Toloker won't be motivated to complete such tasks because they'll spend a lot of time studying instructions but won't earn much.

{% cut "Example" %}

#### A large pool with 1% control tasks (good)

There are 10,000 tasks in the pool, and 100 of them are control tasks (1%). Each suite contains 10 tasks, and 1 of them is a control task. This means a Toloker can complete up to 100 suites.

#### A small pool with 1% control tasks (bad)

There are 100 tasks in the pool, and 1 of them is a control task (1%). Each suite contains 10 tasks, and 1 of them is a control task. This means a Toloker can only complete 1 suite.

#### A small pool with 10% control tasks (good)

There are 100 tasks in the pool, and 10 of them are control tasks (10%). Each suite contains 10 tasks, and 1 of them is a control task. This means a Toloker can complete up to 10 suites.

{% endcut %}

If there are few control tasks in the open pool, [add new control tasks](../troubleshooting/pool-setup.md#add-gs).

{% endcut %}

{% cut "What for" %}

In a large pool with few control tasks, there might be a situation when a Toloker who has completed a lot of tasks in the project stops getting new task suites. This happens when the Toloker completes all control tasks in the pool.

{% note info %}

To filter out Tolokers, use the [Control tasks](control.md) quality control rule. To rank Tolokers by the quality of responses in control tasks, use a [skill](nav.md).

{% endnote %}

{% endcut %}

{% endcut %}

{% cut "How are the correct responses to control questions counted?" %}

The Control tasks rule starts working after the Toloker completes the number of control tasks you specified. If your pool contains both [training](../../glossary.md#training-task) and control tasks, you can take into account the responses in both of them (the **Number of responses** parameter) or only in control tasks (the **Number of control responses** parameter).

As soon as the needed number of responses is collected, Toloka calculates the percentage of correct and incorrect responses and performs an action (assigns a skill, or blocks the Toloker in the pool or in the project). Then this percentage is updated as the tasks are completed by the Toloker. The number of the Toloker's recent responses that's used in the calculation is set in the **Recent control and training task responses to use** field. If you leave it empty, all the responses from the Toloker in the pool are counted.

{% endcut %}

{% cut "Can I make my training or control tasks totally different from the general tasks?" %}

Your [training](train.md) and control tasks have the same project specification. However, you can create a separate project with the tasks and assign a skill based on Toloker responses. Then you can admit Tolokers to the main project based on their skill.

{% endcut %}

{% cut "Isn't the exam a regular pool that I pay for? How does it differ from a regular pool?" %}

An exam pool contains only control tasks. They're usually small, only intended to make sure Tolokers know how to complete your tasks after reading the instructions and completing the [training](additionals-q.md#selection). Unlike your main pool, you already know the correct responses for every task in this pool. You can set the price to zero.

Based on the results of the control tasks, you can assign a skill to Tolokers and then use it in the main pool as a filter. For example, `MySkill = 80 or = Is missing`. You don't have to create an exam. For simple tasks, the training pool provides enough practice, but many requesters also use exams.

{% endcut %}

{% cut "How do I set up an exam so that different people can take it without running out of tasks?" %}

When you load tasks, use smart mixing. In this case, you'll have infinite overlap in your exam.

However, this poses the risk that you might spend a lot of money on the exam. You might want to open this pool only when the main pool opens, and close it when labeling of the main pool ends.

{% endcut %}

{% include [faq-using-smart-mixing](../_includes/faq/adding-tasks-to-the-pool/using-smart-mixing.md) %}

{% cut "Can I create two active training pools, one for practice and the other for admitting Tolokers to the main pool? In other words, one pool is for Tolokers to practice and the other pool tests them." %}

Yes, you can do that. In this case, create the first pool based on the [training pool](../../glossary.md#training-pool) and the exam pool based on your main pool. If a pool contains only control and/or training tasks, the price can be set to zero.

In the exam pool, you can create a skill reflecting the exam result and granting admission to the main pool. For example, `if the number of responses is ≥ 10, set the skill value in the <exam skill> as % of correct responses`. Here are the requirements you should use for Tolokers in the exam pool: `<skill being tested for> < 80 or = none>`. In the main pool, set up a filter: `<exam skill> >= 80 and (<main skill> >= 70 or = Is missing)`. You can choose the skill values depending on how well the Tolokers perform your task.

{% endcut %}

{% cut "I created a training pool with one task containing a hint. A Toloker makes a mistake on their first attempt but eventually succeeds. The Toloker gets the skill “0“. How do I grant to the Toloker access to my tasks? The minimum required level that you can set is “10“." %}

Technically, if you have only one task in your training pool, you don't have this option. The skill will be either `0` or `100`. We recommend that you add several tasks, or at least 2 so that the Toloker will practice on the first task and will be able to do the second task correctly. In this case, you can admit Tolokers to your main pool starting from the skill value of `50`.

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

{% cut "When I export a project from the Sandbox, the task files are not exported. Is this how it's supposed to work? I suddenly lost the markup of the control tasks that I created in the sandbox." %}

The tasks themselves are not exported, only the project configuration and the settings of the selected pool. However, you can download your marked up tasks from the **Sandbox** pool and import them to the pool you created. To download the control tasks only (if you marked them up in the interface), go to **Mark up**, then click **Control tasks** and **Download**.

{% endcut %}

{% endcut %}

{% cut "Ban" %}

{% cut "Can I disable tasks for Tolokers who do a poor job on tasks?" %}

You can deny access to the pool if the Toloker's responses are [too fast](quick-answers.md), if they don't match the [majority vote](mvote.md), or if the Toloker makes too many mistakes in [control tasks](goldenset.md). Tasks completed by such Tolokers can be [given to other Tolokers](restore-task-overlap.md).

{% endcut %}

{% cut "If a cheating Toloker gives a lot of incorrect responses, and the system eventually bans them for errors in control tasks, do I have to pay for the bad responses anyway?" %}

If the Toloker already got paid for the tasks, you can't get your money back.

{% endcut %}

{% cut "If I ban Tolokers from my project so that everyone can complete a maximum of one task, will they be notified?" %}

No, Tolokers don't know when they're blocked.

{% endcut %}

{% cut "If I ban a Toloker for doing my tasks too fast, will all their responses be deleted and given to other Tolokers for labeling?" %}

No. The responses of these Tolokers aren't automatically excluded from the final results file.

But you can do it yourself if you want. When downloading the results, select the option **Exclude assignments by banned Tolokers** to delete the responses of Tolokers who were banned at the moment of downloading. You can also forward all the assignments from banned Tolokers to other Tolokers using the [Re-completion of assignments from banned Tolokers](restore-task-overlap.md) rule.

{% endcut %}

{% cut "How do I classify Tolokers as good Tolokers and poor Tolokers as they complete tasks, and ban the poor Tolokers?" %}

You can create a task pool for all your Tolokers and create Toloker skills in it. In this case, you can open your tasks only to the Tolokers with the necessary skills.

{% endcut %}

{% endcut %}

{% cut "Majority vote" %}

{% cut "The pool has an overlap and majority vote set up, but some fraudulent Toloker opens the task suites, does nothing, and submits empty assignments. Could this cheater get more tasks from the pool before the results of other Tolokers are known? Could a Toloker quickly click through a lot of task suites before the majority vote is accumulated to ban the cheater?" %}

Yes, unfortunately, this can happen. This is why we recommend that you offer a training task or exam before the general task. In this case, only those people who showed good performance at the previous stage are selected for the main pool.

{% endcut %}

{% cut "My task uses a form with multiple fields. When there is an overlap and “Majority vote” is used for quality control, is each field taken into account, or if one field mismatches the majority vote, are the task results considered incorrect?" %}

All responses to the task are taken into account. If one response differs from the majority vote, the whole task is counted as mismatching the responses of other Tolokers.

{% endcut %}

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