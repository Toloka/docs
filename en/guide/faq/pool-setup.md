# Setting up a pool

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

## Filters {#filters}

{% include [faq-specific-city](../_includes/faq/pool-setup/specific-city.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [faq-calculate-skill](../_includes/faq/pool-setup/calculate-skill.md) %}

{% include [faq-assign-skill](../_includes/faq/pool-setup/assign-skill.md) %}

{% include [faq-limit-number-tolokers](../_includes/faq/pool-setup/limit-number-tolokers.md) %}

{% include [faq-skill-expiration](../_includes/faq/adding-tasks-to-the-pool/skill-expiration.md) %}

{% include [faq-arbitrary-user](../_includes/faq/pool-setup/arbitrary-user.md) %}

{% include [faq-demographic-geo-params](../_includes/faq/pool-setup/demographic-geo-params.md) %}

{% include [faq-task-available](../_includes/faq/pool-setup/task-available.md) %}

{% include [faq-select-specific-tolokers](../_includes/faq/pool-setup/select-specific-tolokers.md) %}

{% include [faq-set-up-filter](../_includes/faq/pool-setup/set-up-filter.md) %}

{% include [faq-two-filters](../_includes/faq/pool-setup/two-filters.md) %}

{% include [faq-raise-skill](../_includes/faq/pool-setup/raise-skill.md) %}

{% include [faq-assigned-skill](../_includes/faq/pool-setup/assigned-skill.md) %}

{% include [faq-show-skill](../_includes/faq/pool-setup/show-skill.md) %}

{% include [faq-find-gender](../_includes/faq/pool-setup/find-gender.md) %}

{% include [faq-auto-assign-skill](../_includes/faq/pool-setup/auto-assign-skill.md) %}

## Quality control {#quality-control}

{% include [faq-set-quality-control](../_includes/faq/pool-setup/set-quality-control.md) %}

{% include [faq-how-many-control-tasks](../_includes/faq/pool-setup/how-many-control-tasks.md) %}

{% include [faq-add-control-tasks](../_includes/faq/pool-setup/add-control-tasks.md) %}

{% include [faq-correct-responses-counted](../_includes/faq/pool-setup/correct-responses-counted.md) %}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-make-different](../_includes/faq/pool-setup/make-different.md) %}

{% cut "Isn't the exam a regular pool that I pay for? How does it differ from a regular pool?" %}

An exam pool contains only control tasks. It's usually small and used for checking how well users learned to do your tasks after they read the instructions and completed the [training](../concepts/additionals-q.md#selection). Unlike your main pool, you already know the correct responses for every task in this pool. You can set the price to zero.

Based on the results of responses to control tasks, you can assign a skill to the Tolokers and then specify it in the main pool as a filter. For example, `MySkill = 80 or = Is missing`. You don't have to create an exam. For simple tasks, the training pool provides enough practice, but many requesters also use exams.

{% endcut %}

{% cut "Is the time specified per task suite in the fast response settings?" %}

Yes, the [fast response](../concepts/quick-answers.md) settings specify the time per task suite.

{% endcut %}

{% cut "I set up a rule to ban users after the first incorrect captcha. This is to eliminate any bots. Is this too strict? What rule do most projects use?" %}

Indeed, this rule is probably too strict. Even the most careful user can make a mistake, so you probably want to relax the rule. Besides the requester-specific bans, we have system processes that ban users who regularly fail captcha checks in Toloka.

{% endcut %}

{% cut "The pool has an overlap and majority vote set up, but some fraudulent user opens the task suites, does nothing, and submits empty assignments. Could this cheater get more tasks from the pool before the results of other Tolokers are known? Could a user quickly click through a lot of task suites before the majority vote is accumulated to ban the cheater?" %}

Yes, unfortunately, this can happen. This is why we recommend that you offer a training task or exam before the general task. In this case, only those people who showed good performance at the previous stage are selected for the main pool.

{% endcut %}

{% include [faq-set-up-exam](../_includes/faq/pool-setup/set-up-exam.md) %}

{% cut "How do I test users to determine which kinds of tasks they do better and assign them relevant tasks?" %}

You can add a [training pool](../concepts/train.md) to test your Tolokers. Based on the test results, assign skills to the Tolokers for the tasks they do best.

Then open your pools only to the Tolokers that have a certain skill: use [filters](../concepts/filters.md) for this.

{% endcut %}

{% include [faq-using-smart-mixing](../_includes/faq/adding-tasks-to-the-pool/using-smart-mixing.md) %}

{% cut "If a cheating Toloker gives a lot of incorrect responses, and the system eventually bans them for errors in control tasks, do I have to pay for the bad responses anyway?" %}

If the Toloker already got paid for the tasks, the money can't be refunded to you.

{% endcut %}

{% include [faq-captcha-frequency](../_includes/faq/pool-setup/captcha-frequency.md) %}

{% include [faq-get-access](../_includes/faq/pool-setup/get-access.md) %}

{% cut "If I ban a Toloker for doing my tasks too fast, will all their responses be deleted and given to other Tolokers for labeling?" %}

No. The responses of these Tolokers aren't automatically excluded from the final results file.

But you can do it yourself if you want. When downloading the results, select the option **Exclude assignments by banned users** to delete the responses of Tolokers who were banned at the moment of downloading. You can also forward all the assignments from banned users to other Tolokers using the [Re-completion of assignments from banned users](../concepts/restore-task-overlap.md) rule.

{% endcut %}

{% cut "Can I create two active training pools, one for practice and the other for admitting users to the main pool? In other words, one pool is for users to practice and the other pool tests them." %}

Yes, you can do that. In this case, create the first pool based on the [training pool](../../glossary.md#training-pool) and the exam pool based on your main pool. If a pool contains only control and/or training tasks, the price can be set to zero.

In the exam pool, you can create a skill reflecting the exam result and granting admission to the main pool. For example, `if the number of responses is ≥ 10, set the skill value in the <exam skill> as % of correct responses`. In your exam pool user requirements, specify: `<exam skill> < 80 or = Is missing>`. In the main pool, set up a filter: `<exam skill> >= 80 and (<main skill> >= 70 or = Is missing)`. You can choose the skill values depending on how well the Tolokers handle your task.

{% endcut %}

{% cut "Can I get more details on the best practices for using captchas? For which projects is it better to use captchas and how often?" %}

[Captcha](../concepts/captcha.md) is usually used in simple projects with automatic acceptance, like classification, categorization, or information search. These are cases where there are few response options and users don't need to upload files or write texts. It helps you filter out bots and sloppy Tolokers.

The frequency of issuing captchas is configured in the pool.

No

: Don't show captchas.

Low

: Show a captcha after every 20 assignments.

Average/High

: Show a captcha after every 10 assignments.

{% endcut %}

{% cut "I found the following terms related to captcha in Help: “Percentage of correct responses” and “Percentage of incorrect responses”. Are they determined from the control sample?" %}

The percentage of correct responses is based on the total number of captchas processed by the Toloker within the “range” specified in the **Recent control task responses to use** field. If the value is empty, the percentage is calculated using all the captchas that are shown for the tasks in the pool which uses the captcha rule.

{% endcut %}

{% cut "My task uses a form with multiple fields. When there is an overlap and “Majority vote” is used for quality control, is each field taken into account, or if one field mismatches the majority vote, are the task results considered incorrect?" %}

All responses to the task are taken into account. If one response differs from the majority vote, the whole task is counted as mismatching the responses of other Tolokers.

{% endcut %}

{% cut "Have I understood correctly that if I use `set the the skill value = 1` with the `percentage of accepted responses >= 75` and `10 recent values to use`, for every 8 correctly completed tasks out of 10 the Toloker is given 1 skill point?" %}

No, this is incorrect. With these settings, each time a rule condition is met, the Toloker gets `skill = 1`. To change the skill value in the process of task review, you need a “multi-step” rule, which has multiple identical rules with different values of **Total reviewed responses**.

{% endcut %}

{% include [troubleshooting-hint](../_includes/troubleshooting/pool-setup/hint.md) %}

{% cut "Can I use non-automatic acceptance in the training pool?" %}

No. But you can create a pool of the **Training** type based on your main pool and enable non-automatic acceptance there.

{% endcut %}

{% cut "Can the Tolokers see which questions are control tasks?" %}

No, they can't.

{% endcut %}

{% cut "I have two text versions that I want to show to my respondents: one version to half of the audience, and another version to the other half (like in A/B testing). Is this possible in Toloka, or do I need to create two separate projects?" %}

If you pass texts to the input data, you can load 2 different tasks in the pool. In one task, pass Text 1 in the `INPUT: <input field name>` field, and in the other task, use this field to pass Text 2. But if the text is in the HTML block of the task template, you need to clone the project. To let a Toloker do only one task in your project, use the [Submitted responses](../concepts/submitted-answers.md) rule. You can assign a skill or ban the Toloker after they submit one response.

{% endcut %}

{% cut "If I ban users from my project so that everyone can complete a maximum of one task, are the Tolokers notified of the ban?" %}

No, the Tolokers are unaware of the ban.

{% endcut %}

{% cut "What output format do I use for the review results to filter out mismatching users based on the “Majority vote”?" %}

To perform actions with users (assign a skill or ban them) based on the majority vote, add a relevant [rule](../concepts/mvote.md) to the pool.

Don't forget to enable **Keep task order** in the pool parameters. Majority vote is used in the projects with preset options (radio buttons or checkboxes). This rule won't apply to the text entry or file upload fields.

{% endcut %}

{% cut "I want to create training and exam pools to match the entered text against a sample, and sometimes the matching fails. How do I implement this?" %}

For a control or training assignment to be counted as correct, it must exactly match the control assignment. To do this, you need to normalize the response text using JavaScript: remove spaces, punctuation marks, special characters, and capital letters, and write the result in a separate output field. Now you can match the processed assignment text against your control text.

Another option for selecting Tolokers for a project of this type is assignment review (non-automatic acceptance).

{% endcut %}

{% cut "In the section about control questions, does "Number of control responses" mean the total number of responses to control questions (including incorrect responses) or the number of correct responses to my control questions?" %}

This is the total number of responses to the control questions.

{% endcut %}

{% cut "How do I classify users as good Tolokers and poor Tolokers as they complete tasks, and ban the poor Tolokers?" %}

You can create a task pool for all your Tolokers and create Toloker skills in it. In this case, you can open your tasks only to the Tolokers with the necessary skills.

{% endcut %}

{% cut "How can I speed up the pool completion?" %}

- To motivate Tolokers, assign a [public skill](../concepts/nav-create.md#public) and use [dynamic pricing](../concepts/dynamic-pricing.md).

- Try to [increase the project rating](../concepts/project_rating_stat.md), so that your task is higher in the list of tasks for Tolokers.

- Adjust the [quality-speed ratio](../concepts/adjust.md).

- Set a higher [priority](../concepts/pool_poolparams.md#priority) for the pool among other project pools.

{% endcut %}

## Overlap {#overlap}

{% cut "What overlap should I set?" %}

Overlap defines how many Tolokers complete the same pool task.

The best overlap is an overlap that provides satisfying quality of results. For most tasks that are not [reviewed](../../glossary.md#assignment-review), overlap from “3” to “5” is enough. If the tasks are simple, overlap of “3” is likely to be enough. For tasks that are reviewed, set overlap to “1”.

{% endcut %}

{% cut "Can I change overlap after the pool is started?" %}

Yes. [Open edit mode for the pool](../concepts/pool-edit.md) and set a new overlap value. You don't need to restart the pool. Updating the settings is usually fast, but if there are many tasks, it may take several minutes.

{% endcut %}

{% include [faq-dynamic-overlap](../_includes/faq/pool-setup/dynamic-overlap.md) %}

{% cut "How does counting work if I set `overlap = 3` in the pool and `response threshold = 3` in the majority vote?" %}

In this case, if you don't have 3 identical responses for your task (response threshold), no user would be considered a good or poor Toloker, because the system can't see which of the Tolokers made an error.

But if you set `response threshold = 2` with `overlap = 3`, then two users with the same responses are considered good Tolokers, but the third user, who gives a different response, is a poor Toloker.

{% endcut %}

{% cut "Can I do it like this: set a basic overlap of 2 users, then, if both Tolokers select the same response, close the pool, but if they give different responses, show the task to one more user?" %}

Yes, you can do that. Set up [dynamic overlap](../concepts/dynamic-overlap.md) (incremental relabeling, IRL).

{% endcut %}

{% cut "Is there a cross-check feature for tasks?" %}

You can use overlap to let multiple Tolokers do the same task. The overlap value is set up in the [pool settings](../concepts/pool-edit.md).

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}