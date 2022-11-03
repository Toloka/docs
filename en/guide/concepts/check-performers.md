# How to check Tolokers: quality control rules

Quality control rules regulate task completion and Toloker access. They are set up both for a project as a whole on the **Quality control** tab and for each pool individually.

## Monitoring Toloker actions {#control-actions}

If your project has a lot of similar tasks, you'll need to protect it from fake users (robots) and cheaters.

#### Limiting fast responses

Configure the [Fast responses](quick-answers.md) rule to filter out cheating Tolokers who don't handle tasks carefully and complete them too quickly. You've tried doing tasks and you know that each task takes at least 15 seconds. You should suspend Tolokers who submit three out of ten assignments in a row faster than the control time.

![](../_images/cp-quick_answers.png)

#### Limit on skipped assignments

Another “optimization” technique that cheaters use is skipping certain assignments. They pick out the ones that seem easier to them, while other Tolokers reliably complete all the assignments they receive. However, both get paid in the same way.

Configure the [Skipped assignments](skipped-assignments.md) rule to avoid this situation. It will restrict access for those Tolokers who skip too many assignments, like more than three in a row.

![](../_images/cp-skipped_assignments.png)

#### Captcha

To protect against robots, use the Captcha rule. In Toloka, a captcha is shown every 10 assignments. If assignments are completed quickly and captchas get in the way, they can be shown every 20 assignments: specify low captcha frequency in the pool settings.

![](../_images/cp-captcha.png)

#### Limit on available tasks

Limits are also useful when you need as many different Tolokers as possible, like to collect statistics for a survey or choosing the best version of a logo. Another case is personal descriptions for a [dating service](https://rb.ru/opinion/chat-bot-dataset/). If texts are all written by the same person, they are likely to turn out monotonous and boring.

You can engage more participants if you limit the number of assignments “per Toloker”. You can do this by setting a limit on the number of tasks available to each Toloker or a limit on daily earnings in a single project. Use the [Submitted responses](submitted-answers.md) and [Earnings](income.md) rules.

![](../_images/cp-submitted_answers.png)

## Task completion quality control {#check-resalts}

Results from conscientious Tolokers should be checked, too. In Toloka, this can be done automatically.

#### Control tasks

In some tasks, Tolokers are given a choice of two or more response options. To check the quality in this type of project, use the [Control tasks](goldenset.md) rule. This involves adding questions where you define the correct response.

Mix the control questions in with the general tasks. They should make up at least 1% of the total tasks. Based on the number of errors, you'll evaluate Tolokers and assign them a skill level from 0 to 100.

![](../_images/cp-goldenset.png)

Those who make a critical number of errors will be automatically excluded from your tasks by skill filters. Pay more to highly skilled Tolokers (who score 90 and higher) as an incentive. This encourages Tolokers to try harder on tasks.

#### Majority vote

Sometimes requesters aren't able to regularly add control tasks and keep them updated.

In this case, the [Majority vote](mvote.md) rule is helpful. The platform assigns the same task to multiple Tolokers. For example, five people get the exact same task. If three or more choose the same answer, we assume it is correct.

![](../_images/cp-mvote.png)

Use the percentage of matching responses to assign skill levels, control access to tasks, and reward Tolokers.

#### Review results

Tasks where each Toloker has to give a unique response, like recording audio, taking a photo, or writing a text, are reviewed by requesters themselves or by other Tolokers. Poor-quality responses are rejected.

Use the [Review results](reviewing-assignments.md) rule to control Tolokers' access to tasks. The platform calculates the percentage of responses accepted and rejected for each Toloker. Those who often made mistakes will stop getting tasks.

![](../_images/cp-reviewing_assignments.png)

## Recompletion of rejected assignments {#revision-results}

Quality control rules let you minimize the consequences of errors. In Toloka, you can choose to resend for recompletion just individual rejected assignments, or all responses from Tolokers who made too many mistakes.

#### Rejected tasks

For example, you can use Toloka to improve speech recognition algorithms. Tolokers listen to a series of 5-10-second recordings and make a transcription of each of them in order to convert speech to text.

Some of the recordings are transcribed incorrectly. Don't accept incorrect responses. Set up the [Processing rejected and accepted assignments](reassessment-after-accepting.md) rule. The platform will automatically send incorrect transcriptions to other Tolokers for revision.

![](../_images/cp-reassessment_after_accepting.png)

#### Responses from banned Tolokers

If a user makes mistakes too many times, the platform bans them from taking more tasks. But the responses that they have already provided remain in the database and may get into the final dataset. Send these assignments for recompletion.

The [Recompletion of assignments from banned users](restore-task-overlap.md) rule is helpful here. It increases the cost of labeling, but protects the dataset from possible errors.

![](../_images/cp-restore_task_overlap.png)

As soon as a Toloker loses access to a project, like due to a low skill level, Toloka automatically sends all their completed assignments to other Tolokers for re-labeling.

## Combination of methods {#combination-methods}

The best practice is to combine quality control rules. For example, if tasks involve selecting a response from several options, you should use:

- [Captchas](captcha.md).
- [Fast responses](quick-answers.md).

Content generation projects like writing texts or taking photos need a different combination:

- [Limit on available tasks](#limit-task).
- [Review results](reviewing-assignments.md).
- [Recompletion of rejected assignments](#revision-results).

## General recommendations {#general-advice}

Each project requires its own approach. Methods that are effective in one case may be pointless in another. But there are some general recommendations:

1. Analyze the task and select the appropriate quality control rules.

1. Write clear instructions. If you create control tasks, make sure they don't have any outdated, ambiguous, or incorrect responses.

1. Test your project in the testing environment, the [Sandbox](sandbox.md). Running and completing tasks in it will help you understand the rules and estimate how much time it will take to complete a single task.

1. Launch the first real project with a small number of tasks. Analyze the results and adjust the settings if necessary.

1. Monitor the labeling results and listen to feedback from Tolokers.

1. Contact support If something isn't working.

{% include [contact-support](../_includes/contact-support-help.md) %}