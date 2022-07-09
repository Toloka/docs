### A

Active Tolokers {#active-tolokers}

: Tolokers who viewed or completed tasks during the last hour and match the [filters](#filters) specified in the [pool](#pool) settings. This is the number of Tolokers who will see your task if you publish it now.

Archive pool {#archive-pool}

: A [pool](#pool) that was moved to the archive. Archive pools can't be started or edited and are not available for [assignment review](#assignment-review). The pool is automatically archived if there is no activity in it for a month.

Assignment review {#assignment-review}

: A [pool](#pool) setting that allows you to check responses so you don't have to pay for poorly completed tasks.

### B

Banning Tolokers {#banning-tolokers}

: You can block a Toloker's access to one or more [projects](#project). This lets you control manually which Tolokers will complete tasks. For example, you can choose all Tolokers with a [skill](#skill) value lower than N and block their access to tasks. You can also unblock access.

### C

Captcha (quality control rule) {#captcha}

: Restricts access to tasks for Tolokers who fail to enter captcha several times in a row. Protects your project against fake users (robots).

Certified partners {#certified-partners}

: Companies that take on the launch and implementation of your project and help you process the results. These companies have already integrated crowdsourcing into their business processes and offer excellent solutions.

Checking completed tasks

: Manually checking the responses received by the requester. The requester accepts or rejects the responses. Rejected responses aren't paid for.

Completed tasks (quality control rule) {#completed-tasks}

: Number of completed [task suites](#task-suite) (taking [overlap](#overlap) into account).

Component {#component}

: The task interface consists of ready-made components representing JSON objects with a specified structure. Components are categorized depending on their purpose, such as data entry fields, conditions, or actions. The name of the component is specified in the `type` property in the format `<category>.<name>`.

  [List of components](../template-builder/reference/index.md)

Configuration {#configuration}

: Description of your interface in the JSON format. This is also the name of the panel in the editor where you write this code.

Control task {#control-task}

: A task that contains the correct response. Control tasks are used to monitor the quality of the Toloker's responses.

  For example, you can track the percentage of correct responses and block Tolokers who respond poorly. To do this, use the [Control tasks](https://toloka.ai/docs/guide/concepts/goldenset.html) rule.

  {% note tip %}

  - Add [at least 1% of control tasks](https://toloka.ai/docs/guide/troubleshooting/pool-setup.html#quality-control__how-many-control-tasks) to the pool.
  - Design control tasks so that different versions of correct responses are used with the same frequency. [Learn more](https://toloka.ai/docs/guide/concepts/task-markup-by-yourself.html#task-markup-by-yourself__answer_distribution)

  {% endnote %}

  In addition to control tasks, there are [general](#general-task) and [training](#training-task) tasks.

Crowdsourcing experts {#crowdsourcing-experts}

: Professionals who help create and configure [projects](#project), post tasks, and much more. They have passed a certification exam to prove their knowledge of crowdsourcing and earned a registered e-certificate. To learn about the terms of partnership, contact these experts directly.

### D

Dynamic overlap (incremental relabeling, IRL) {#dynamic-overlap}

: A type of overlap that changes the number of Tolokers to complete each task in the [pool](#pool). This number depends on how well the Tolokers cope with the task or how consistent their responses are.

Dynamic pricing {#dynamic-pricing}

: Allows you to additionally set other prices that depend on the Toloker's [skill](#skill). For example, to pay more to those who have a higher skill. [Learn more](https://toloka.ai/docs/guide/concepts/dynamic-pricing.html)

### E

Earnings (quality control rule) {#earnings}

: Restricts the Toloker's earnings in the [pool](#pool) for a day to get responses from as many Tolokers as possible and provide protection against robots.

Exam {#exam}

: A [pool](#pool) with [control tasks](#control-task) for choosing Tolokers. You can assign [skills](#skill) to Tolokers depending on whether their responses are correct and identify the best Tolokers.

### F

Fast responses {#fast-responses}

: Restricts access to tasks for Tolokers who respond too quickly. You can use it to:

  - Suspend access for Tolokers who cheat in their responses (in this case, set the time required to complete a [task suite](#task-suite) when giving random responses).
  - Provide protection from robots (in this case, the time for completing the task suite should be 2 times less).

Fee {#fee}

: The requester is charged a fee for using Toloka — a percentage of the cost of tasks. It is 30%, but not less than $0.005.

Field task {#field-task}

: A task to be performed in the mobile app. It usually contains a point on the map that the Toloker needs to go to, check something, and take photos.

Filters {#filters}

: Criteria for choosing Tolokers. For example, you can select only Tolokers who speak English or have a certain skill.

  Filters are used in the [pool](#pool) settings on the [Users](https://toloka.yandex.com/en/requester/workers) page and for [sending messages](https://toloka.ai/docs/guide/concepts/messaging.html) to a group of users. [Learn more](https://toloka.ai/docs/guide/concepts/filters.html)

### G

General task {#general-task}

: A task that doesn't provide hints or the correct response. The responses are provided by the Tolokers. These are the general tasks you upload to the [pool](#pool) to give to the Tolokers.

  In addition, there are [control](#control-task) and [training](#training-task) tasks.

### I

Incomplete task suite {#incomplete-task-suite}

: The last suite with an insufficient number of [general](#general-task) tasks. This is generated if less than the minimum remaining number of general tasks are not completed. In this case, the number of control and training tasks must be complete.

Input and output data {#input-output-data}

: The format of input and output data is set in the **Specifications** field.

  _Input data_ is the source data you want to display or use. For example, links to images that will be shown to Tolokers. Use the `data.input` component of [Template Builder](../template-builder/index.md) to access the input data.

  _Output_ is the data you receive after the task is completed, like the Tolokers' responses to your questions. Use the `data.output` component of Template Builder to access the output data.

  See the Template Builder [Read and write](../template-builder/operations/input-output-data.md) instructions to learn about working with data.

Internal data {#internal-data}

: The data available only from within the task. This data is not saved to the results. Use this data to calculate or store intermediate values. To access the internal data, use the `data.internal` component of [Template Builder](../template-builder/index.md).

  See the Template Builder [Read and write](../template-builder/operations/input-output-data.md) instructions to learn about working with data.

Instructions {#instructions}

: Task instructions that the Toloker sees when choosing and completing the task. The clarity and completeness of the instructions affect response quality and the [project](#project) rating. Good instructions help the Toloker complete the task correctly.

Interested users {#interested-users}

: The number of Tolokers who started at least one [task suite](#task-suite).

### K

Keeping the task order {#keep-task-order}

: Task suites in the [pool](#pool) are distributed in the same order as they are in the uploaded [file](#tsv). The tasks within each suite are shuffled. [Learn more](https://toloka.ai/docs/guide/concepts/save-order.html)

### L

List of target languages {#target-languages}

: Used in the [Translations](https://toloka.ai/docs/guide/concepts/project-languages.html#project-languages__how-it-works) section if there is no source language.

  Display order:

  - English
  - Russian
  - Turkish
  - French
  - Indonesian
  - Vietnamese
  - Uzbek
  - Spanish
  - German
  - Italian
  - Polish

### M

Majority vote (quality control rule) {#majority-vote}

: A [quality control](#quality-control) method that considers a response correct if it is chosen by the majority of Tolokers (also known as consensus). Other responses are considered incorrect.

### O

Overlap {#overlap}

: The number of Tolokers who should complete each task in the [pool](#pool). Overlap is used to make sure the results are reliable.

### P

Personalized quality forecast {#personilized-quality-forecast}

: A personalized quality forecast is based on a large amount of data about user behavior in the system, how other users completed your task, and the task itself.

Pool {#pool}

: A set of paid tasks that share the same properties (such as Toloker selection settings and payment per [task suite](#task-suite)) and are sent out for completion at the same time.

Project {#project}

: A project consists of [pools](#pool) with tasks. Project settings define the [task interface](#task-interface) and the [input and output data](#input-output-data).

  Settings for creating tasks:

  - Parameters for objects that are shown in the [task suite](#task-suite) (images, text, and so on).
  - Parameters for input fields.
  - The visual appearance of tasks.

Project template {#project-template}

: The template contains pre-configured [input and output data](#input-output-data) fields and the [task interface](#task-interface), which you can edit.

### Q

Quality control {#quality-control}

: Quality control lets you get more accurate responses and restrict access to tasks for cheating Tolokers. Quality control consists of rules that are independent from each other. The quality control block allows you to set rules and configure them. [Learn more](https://toloka.ai/docs/guide/concepts/control.html)

Quality control rule {#quality-control-rule}

: Independent rules that make up quality control. The quality control block allows you to set rules and configure them.

### R

Ready protection sets {#ready-protection-sets}

: Several [quality control rules](#quality-control-rule) with default settings.

Recompletion of assignments from banned users (quality control rule) {#recompletion}

: A rule that can be configured to resend tasks for recompletion to other Tolokers if:

  - [The Toloker is banned](#banning-tolokers) by a [quality control rule](#quality-control-rule) (for example, [control tasks](#control-task) or [majority vote](#majority-vote)).
  - The Toloker's [skill](#skill) value changed (for example, the Toloker's skill value dropped and they no longer match the skill [filter](#filter)).

  All [pool](#pool) tasks completed by this Toloker will be resent to other Tolokers. Tasks completed by banned Tolokers are reassigned, but those completed by paused Tolokers are not.

Retry pool {#retry-pool}

: The retry pool helps Tolokers who make mistakes improve their [skills](#skill) and get a second chance to complete tasks.

Review period {#review-period}

: Number of days for checking the task.

Reward {#reward}

: You can give rewards to Tolokers for completing tasks well. This improves motivation and encourages Tolokers to approach your tasks with care. You can give rewards to one or more Tolokers (in addition to payment for [completed tasks](#completed-tasks)). The reward amount can be from $0.01 to $100 per Toloker per time.

### S

Sandbox {#sandbox}

: Toloka testing environment. This is where you can test your [project](#project) settings as a Toloker before moving them to the Toloka production version and running the project for real Tolokers. This helps you avoid making mistakes and spending money on a task that isn't working right.

Selective majority vote check {#selective-majority-vote-check}

: Majority vote checks only some tasks. This helps you save money and speed up [pool](#pool) completion.

Skill {#skill}

: An assessment of the Toloker's quality of task completion on a scale of 0 to 100. The skill can be calculated automatically (for example, based on correct responses to [control tasks](#control-task)), or assigned manually. Skills are used for Toloker selection in a [pool](#pool). [Learn more](https://toloka.ai/docs/guide/concepts/nav.html)

Skipping tasks (quality control rule) {#skipping-tasks}

: Restricts access to the [pool](#pool) tasks for Tolokers who skip several [task suites](#task-suite) in a row.

Smart mixing {#smart-mixing}

: Smart mixing randomly generates task suites so that tasks aren't repeated for each Toloker.

Submitted in pool {#submitted-in-pool}

: The number of Tolokers who completed at least one task suite.

### T

Task {#task}

: A special assignment which annotators complete in [Toloka](https://toloka.ai/). It is a part of a web page that can contain various objects: images, text, input fields, and others. The Toloker reads the instructions for the task, completes it and enters responses. In [Template Builder](../template-builder/index.md), you can create an interface for such tasks.

Task interface {#task-interface}

: The task interface defines the task appearance for the Toloker and the logic for processing responses.

Task markup {#task-markup}

: Task markup lets you add correct responses and hints to the tasks, as well as change task types. You can transform a [general task](#general-task) into a [control task](#control-task) by adding the correct response, or into a [training task](#training-task) by adding the correct response and a hint. Task markup is available only for training pools and pools uploaded with “[smart mixing](#smart-mixing)”.

  [Learn more about task markup](https://toloka.ai/docs/guide/concepts/task_markup.html)

Task suite {#task-suite}

: A task suite contains one or several tasks that are shown on the same page. If the tasks are simple, you can add 10-20 tasks per suite. Don't make task suites too long because it slows down loading speed for Tolokers. A task suite may consist of a single task.

Toloka API {#toloka-api}

: The [Toloka API](https://toloka.ai/docs/api/) (Toloka application programming interface) describes methods (a set of classes, procedures, functions, structures, or constants) used by Toloka to interact with other computer programs, and allows you to create tasks and receive user responses (see the [documentation](https://toloka.ai/docs/api/concepts/about.html)).

  The requests to the Toloka API are made using the [HTTPS protocol](https://en.wikipedia.org/wiki/HTTPS). The service returns data in the [JSON](https://www.json.org/json-en.html) format.

Toloker rating {#toloker-rating}

: The Toloker's rating reflects the quality of the Toloker's responses to tasks. It takes into account responses to [control tasks](#control-task), bans, and periods without work. The rating is calculated as the weighted average value for the last few weeks. So the rating can “suddenly” decrease or increase.

Training

: A main [pool](#pool) that consists only of [training tasks](#training-task) and can have zero cost.

  Use it to train Tolokers before performing real tasks if you can't use a [training pool](#training-pool) for your project.

Training pool {#training-pool}

: A [pool](#pool) of zero-cost tasks for training Tolokers. Training tasks contain correct responses and hints that are shown if the Toloker answers incorrectly.

  To improve the quality of results, you can add a training pool and choose only those Tolokers who pass training successfully. [Learn more](https://toloka.ai/docs/guide/concepts/train.html)

Training skill {#training-skill}

: A skill that is automatically created when the first training pool is added to the project. The skill name is `<project name> - training`. The value is the percentage of correct responses in the training pool. The skill is assigned to the Toloker after they complete the training pool.

: There is only one training skill for the entire project. If you create new training pools, they will use the same skill.

  - [Learn more about skills](https://toloka.ai/docs/guide/concepts/nav.html)
  - [Learn more about training pools](https://toloka.ai/docs/guide/concepts/train.html)

Training task {#training-task}

: A task that contains the correct response and a hint. If the Toloker responds incorrectly, they will see a hint and won't be able to go to the next [task suite](#task-suite) until they complete all tasks correctly. Only the first response to the task is taken into account for [quality control](#quality-control) and [skill](#skill) calculation.

  Training tasks can be used in zero-cost [training pools](#training-pool) to choose Tolokers who pass training.

  They can also be used in regular pools as [control tasks](#control-task) with hints. For example, you can track the percentage of correct responses and ban Tolokers who respond poorly. To do this, use the [Control tasks](https://toloka.ai/docs/guide/concepts/goldenset.html) rule.

TSV file with tasks {#tsv}

: TSV (tab-separated values) is a text file format in which data is separated by a tab, and lines are separated by a newline symbol.