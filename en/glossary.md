# Glossary

### A

#### Action components (component type for Template Builder) {#action}

A category of [components](#component) used in Template Builder that perform actions, such as open a link, display a message, or play a video. Some components work with data. For example, they can change the value from `true` to `false`. [List of actions](template-builder/reference/actions.md)

#### Active Tolokers {#active-tolokers}

Tolokers with access to the [pool](#pool) who took tasks during the last hour.

#### Aggregated answer {#aggregated-answer}

See [Item](#item).

#### Archived pool {#archive-pool}

A [pool](#pool) that was moved to the archive. Archived pools can't be started or edited and are not available for the [assignment review](#assignment-review). The pool is automatically archived if there is no activity in it for a month. With the archived pool, you can [view the pool statistics](guide/concepts/pool_statistic-pool.md), [download](guide/concepts/result-of-eval.md) the pool data, and [clone the pool](guide/concepts/pool-main.md#clone).

#### Assignment {#assignment}

A task suite that a [Toloker](#toloker) decides to complete. An assignment can have one the following statuses: **accepted**, **active**, **expired**, **rejected**, **skipped**, or **submitted**. Refer to the [Toloka API documentation](api/concepts/result.md#query-params) for more information on each status.

### B

#### Banning Tolokers {#banning-tolokers}

Blocking a Toloker's access to one or more [projects](#project). This lets you control manually which Tolokers will complete tasks. For example, you can choose all Tolokers with a [skill](#skill) value lower than `N` and block their access to tasks. You can also unblock access.

#### Batch (in bespoke solutions) {#batch}

Datasets that you send for labeling at a time. Batches are used in [bespoke solutions](https://toloka.ai/pricing/).

#### Benchmark task {#benchmark-task}

See [Control task](#control-task).

### C

#### Captcha {#captcha}

A type of challenge–response test to determine whether the user is human. Protects your project against fake users (robots). Restricts access to tasks for Tolokers who fail the test several times in a row.

#### Certified partners {#certified-partners}

Companies that take on the launch and implementation of your project and help you process the results. These companies have already integrated [crowdsourcing](#crowdsourcing) into their business processes and offer excellent solutions.

#### Component (component type for Template Builder) {#component}

JSON objects with a specified structure which help you build a task interface in Template Builder. Components are categorized depending on their purpose, such as [data entry fields](#data-entry-field), [conditions](#condition), or [actions](#action). The name of the component is specified in the `type` property in the `<category>.<name>` format. [List of components](template-builder/reference/index.md)

#### Condition components (component type for Template Builder) {#condition}

A category of [components](#component) used in Template Builder that check whether the expression matches the specified condition. You can use them to check that the text is entered in a field. [List of conditions](template-builder/reference/conditions.md)

#### Configuration {#configuration}

A description of your interface in the JSON format. You write the code for it in the Template Builder editor panel called **Config**.

#### Control task (gold question, honeypot, benchmark task) {#control-task}

A task that contains the correct response. Control tasks are used to monitor the quality of the Toloker's responses.

For example, you can track the percentage of correct responses and block Tolokers who respond poorly. To do this, use the [Control tasks](guide/concepts/goldenset.md) quality control rule.

In addition to control tasks, there are [general](#general-task) and [training](#training-task) tasks.

#### Crowdsourcing {#crowdsourcing}

The practice of obtaining information or services from a large dispersed group of people. These people perform micro tasks, and their collective work provides valuable input. For example, they can classify images into categories, and the resulting data can be used later to improve search relevance or recommendation systems.

#### Crowdsourcing experts {#crowdsourcing-experts}

Professionals who help create and configure [projects](#project), post tasks, and much more. They have passed a [certification exam](https://toloka.ai/csa-certification/) to prove their knowledge of crowdsourcing and earned a registered e-certificate.

#### CSV {#csv-format}

Comma-separated values. A text file format in which data is separated by the comma, and lines are separated by a newline symbol.

### D

#### Data entry field components (component type for Template Builder) {#data-entry-field}

A category of [components](#component) used in Template Builder that create data entry fields, such as text fields or drop-down lists. [List of data entry fields](template-builder/reference/fields.md)

#### Decomposition {#decomposition}

A process of dividing a large project into several small ones. Decomposition results in shorter tasks that are easier to do, which helps improve quality.

#### Dynamic overlap (incremental relabeling, IRL) {#dynamic-overlap}

A type of [overlap](#overlap) that changes the number of Tolokers to complete each [item](#item) in the [pool](#pool). This number depends on confidence in the results: how well the Tolokers cope with the tasks or how consistent their responses are. The dynamic overlap value increases with the decreasing cofidence in the results, and vice versa.

#### Dynamic pricing {#dynamic-pricing}

An option to set prices that depend on the Toloker's [skill](#skill). This allows you, for example, to pay more to those who have a higher skill. [Learn more](guide/concepts/dynamic-pricing.md)

### E

#### Earnings (quality control rule name) {#earnings}

A [quality control](#quality-control) rule that restricts the Toloker's earnings in the [pool](#pool) for a day. This allows you to get responses from as many Tolokers as possible and provide extra protection against robots.

#### Element layout components (component type for Template Builder) {#element-layout}

A category of [components](#component) used in Template Builder that arrange the interface elements, such as in columns or side-by-side. [List of layout options](template-builder/reference/layouts.md)

#### Exam {#exam}

A [pool](#pool) with [control tasks](#control-task) for choosing Tolokers. You can assign [skills](#skill) to Tolokers depending on whether their responses are correct and identify the best Tolokers.

### F

#### Fast responses (quality control rule) {#fast-responses}

A [quality control](#quality-control) rule that restricts access to tasks for Tolokers who respond too quickly. You can use it to:

  - Suspend access for Tolokers who respond randomly. You can set a reasonable minimal time required to complete a [task suite](#task-suite).
  - Provide protection from robots (in this case, the time for completing the task suite should be much less).

#### Fee {#fee}

A percentage of the cost of tasks for which the requester is charged by the service when using Toloka.

#### Field task {#field-task}

A task that is performed at a physical location using the mobile app. It usually contains a point on the map that the Toloker needs to go to, check something, and take photos.

#### File with tasks {#tsv}

A file that contains the data you need to label. Requesters use such files to upload tasks. Toloka allows using [TSV](#tsv-format), [XLSX](#xlsx-format), or [JSON](#json-format) files.

#### Filters {#filters}

Criteria for choosing Tolokers. For example, you can select only Tolokers who speak English or have a certain skill.

You can use filters to choose Tolokers when setting up [pools](#pool) (in the **Audience** section), on the [Users](https://platform.toloka.ai/requester/workers) page, and for [sending messages](guide/concepts/messaging.md) to a group of users. [Learn more](guide/concepts/filters.md)

#### Final answer {#final-answer}

See [Item](#item).

#### Final label {#final-label}

See [Item](#item).

### G

#### General task {#general-task}

A task without hints or the correct response. These are the general tasks you upload to the [pool](#pool) for which the Tolokers provide their responses.

In addition, there are [control](#control-task) tasks (which contain the correct responses) and [training](#training-task) tasks (which contain the correct responses and hints).

#### Gold question {#gold-question}

See [Control task](#control-task).

### H

#### Helper components (component type for Template Builder) {#helper}

A category of [components](#component) used in Template Builder for auxiliary operations, such as working with arrays. [List of helpers](template-builder/reference/helpers.md)

#### Honeypot {#honeypot}

See [Control task](#control-task).

### I

#### Incomplete task suite {#incomplete-task-suite}

The last task suite which contains a number of [general](#general-task) tasks which is insufficient to form a complete suite. In this case, Tolokers will see a page with fewer general tasks and the full number of control and training tasks. Incomplete task suites can be enabled for tasks uploaded using [smart mixing](#smart-mixing).

#### Incremental relabeling {#incremental-relabeling}

See [Dynamic overlap](#dynamic-overlap).

#### Input and output data {#input-output-data}

The format of input and output data that you set in the **Data specification** field of the **Task interface** section when setting up a project.

  - _Input data_ is the source data you want to display or use. For example, links to images that will be shown to Tolokers. Use the `data.input` component of [Template Builder](template-builder/index.md) to access the input data.
  - _Output data_ is the data you receive after the task is completed, like the Tolokers' responses to your questions. Use the `data.output` component of Template Builder to access the output data.

See the Template Builder [Read and write](template-builder/operations/input-output-data.md) instructions to learn about working with data.

#### Instructions {#instructions}

Project instructions that Tolokers see when choosing and completing the task. The clarity and completeness of the instructions affect response quality and the [project](#project) rating. Good instructions help Tolokers complete the task correctly.

#### Interested Tolokers {#interested-users}

The number of Tolokers who started at least one [task suite](#task-suite).

#### Internal data (used with Template Builder) {#internal-data}

The data available only from within the task. This data is not saved to the results. Use it to calculate or store intermediate values. To access the internal data, use the `data.internal` component of [Template Builder](template-builder/operations/input-output-data.md).

#### IRL (incremental labeling) {#irl}

See [Dynamic overlap](#dynamic-overlap).

#### Item (final answer, aggregated answer, final label) {#item}

Corresponds to the final labeled data unit or a unique data unit to be labelled in Toloka. It is calculated as the aggregated result of all responses received for a task.

### J

#### JSON {#json-format}

JavaScript Object Notation. A text file format used to store and transfer structured data.

### K

#### Keep task order {#keep-task-order}

Distributing the task suites in the [pool](#pool) in the same order as they are in the uploaded [file](#tsv). The tasks within each suite are shuffled.

### L

#### Labeling {#labeling}

Adding informative tags to the data. For example, indicate if there are certain objects in a photo (streetlights, cars, pedestrians), transcribe an audio file, categorize a text or a video file, and add other similar information.

#### List of target languages {#target-languages}

A set of languages in the [Translations](guide/concepts/project-languages.md#how-it-works) section into which the project interface can be translated.

### M

#### Majority vote (quality control rule name) {#majority-vote}

A [quality control](#quality-control) rule that considers a response correct if it is chosen by the majority of Tolokers (also known as consensus). Other responses are considered incorrect.

### O

#### OCR {#ocr-abbr}

See [Optical character recognition](#ocr).

#### Optical character recognition (OCR) {#ocr}

The conversion of images of typed, handwritten or printed text into machine-encoded text, whether from a scanned document, a photo of a document, a scene-photo or from subtitle text superimposed on an image.

#### Overlap {#overlap}

The number of Tolokers who should complete each [item](#item) in the [pool](#pool). Overlap is used to make sure the results are reliable.

### P

#### Personalized quality forecast {#personilized-quality-forecast}

A real-time quality prediction of how well each particular Toloker will handle your task. The forecast is based on a large amount of data about user behavior in the system, how other Tolokers completed your task, and the task itself.

#### Plugin components (component type for Template Builder) {#plugin}

A category of [components](#component) used in Template Builder that enable advanced features. For example, `plugin.hotkeys` lets you set up shortcuts. [List of plugins](template-builder/reference/plugins.md)

#### Pool {#pool}

A set of data to label in a project. You can use the pool settings to select Tolokers, set the price for tasks, and add various quality control rules. Tasks in a pool share the same properties (such as Toloker selection settings and payment per [task suite](#task-suite)) and are sent out for completion at the same time.

#### Project {#project}

A specific data labeling goal. This could be to moderate comments, to classify images, to transcribe audio recordings, or something else. A project consists of [pools](#pool) with [tasks](#task). Project settings define the [task interface](#task-interface), instructions, and the [input and output data](#input-output-data) shared by all pools within the same project.

#### Project preset {#project-template}

A pre-configured project that contains description, instruction, predefined [input and output data](#input-output-data) fields, and the [task interface](#task-interface) which you can edit.

### Q

#### Quality control {#quality-control}

A monitoring and control system that lets you get more accurate responses and restrict access to tasks for bad actors. Quality control consists of rules that are independent from each other. [Learn more](guide/concepts/control.md)

#### Quality control presets {#ready-protection-sets}

Predefined [quality control rule](#quality-control-rule) combinations available in the **Quality control** section of the pool settings. Three main quality control presets are available: elementary, basic, and advanced.

#### Quality control rule {#quality-control-rule}

Independent rules that make up [quality control](#quality-control). In the pool settings, the **Quality control** section allows you to set rules and configure them.

### R

#### Recompletion of assignments from banned users (quality control rule name) {#recompletion}

A [quality control](#quality-control) rule that can be configured to resend tasks for recompletion to other Tolokers if:

  - [The Toloker is banned](#banning-tolokers) by a [quality control rule](#quality-control-rule) (for example, [control tasks](#control-task) or [majority vote](#majority-vote)).
  - The Toloker's [skill](#skill) value changed (for example, the Toloker's skill value dropped and they no longer match the skill [filter](#filter)).

All [pool](#pool) tasks completed by this Toloker will be resent to other Tolokers. Tasks completed by banned Tolokers are reassigned, but those completed by paused Tolokers are not.

#### Response {#response}

The result of completing an assignment by a Toloker. The responses can be either correct or incorrect. You can decline incorrect responses using the [assignment review](#assignment-review) and even [block Tolokers](#banning-tolokers) who give too many incorrect responses.

#### Retry pool {#retry-pool}

A pool that helps Tolokers who make mistakes improve their [skills](#skill) and get a second chance to complete tasks.

#### Review period {#review-period}

Number of days for checking Toloker responses [manually](#assignment-review).

#### Review task responses manually {#assignment-review}

A [pool](#pool) setting that allows you to manually check [responses](#response) from Tolokers. You can either accept correct responses or reject poorly completed tasks and not pay for them.

#### Reward {#reward}

Extra payment that you can give to Tolokers for completing tasks well. It improves motivation and encourages Tolokers to approach your tasks with care. You can give rewards to one or more Tolokers (in addition to payment for [completed tasks](#completed-tasks)). The reward amount can be from \$0.01 to \$100 per Toloker per time.

### S

#### Sandbox {#sandbox}

The Toloka testing environment. This is where you can test your [project](#project) settings as a Toloker before moving them to the Toloka production version and running the project for real Tolokers. This helps you avoid making mistakes and spending money on a task that isn't working right.

#### SbS {#sbs-abbr}

See [Side-by-side](#sbs).

#### Selective majority vote check {#selective-majority-vote-check}

An option that allows you to selectively increase overlap for some [items](#item). This helps you save money and speed up [pool](#pool) completion. [Learn more](guide/concepts/selective-mvote.md)

#### Side-by-side (SbS) {#sbs}

Side-by-side comparison type of projects. Toloka has several presets to compare objects side-by-side: [images](guide/tutorials/side-by-side.md), video and audio files.

#### Skill {#skill}

An assessment of the Toloker's quality of task completion on a scale of 0 to 100. The skill can be calculated automatically (for example, based on correct responses to [control tasks](#control-task)), or assigned manually. Skills are used to select Tolokers in a [pool](#pool). [Learn more](guide/concepts/nav.md)

#### Skipped assignments (quality control rule name) {#skipping-tasks}

A [quality control](#quality-control) rule that restricts access to the [pool](#pool) tasks for Tolokers who skip several [task suites](#task-suite) in a row.

#### Smart mixing {#smart-mixing}

A way to randomly combine tasks and generate task suites so that tasks aren't repeated and look different for each new Toloker.

#### Submitted in pool {#submitted-in-pool}

A pool statistics parameters which shows the number of Tolokers who completed and submitted at least one task suite in the pool.

#### Submitted responses (quality control rule name) {#completed-tasks}

A [quality control](#quality-control) rule that limits the number of [task suites](#task-suite) a Toloker can complete per day (taking [overlap](#overlap) into account). This allows getting a broader selection of users.

### T

#### Task {#task}

A request or question that elicits a response from an annotator in [Toloka]({{ toloka }}). A task is created for a single data unit that requires labeling, like a photo to classify, or a comment to review. It is a part of a web page (a [task suite](#task-suite)) that can contain various objects: images, text, input fields, and others. Tolokers read the instructions for the task, complete it and enter [responses](#response). In [Template Builder](template-builder/index.md), you can create an interface for such tasks.

#### Task interface {#task-interface}

The appearance of a task for Tolokers and the logic for processing responses.

#### Task markup {#task-markup}

Adding correct responses and hints to the tasks and changing task types. You can transform a [general task](#general-task) into a [control task](#control-task) by adding the correct response, or into a [training task](#training-task) by adding the correct response and a hint. Task markup is available only for training pools and pools uploaded with “[smart mixing](#smart-mixing)”. [Learn more](guide/concepts/task_markup.md)

#### Task suite {#task-suite}

A group of several tasks given to a Toloker to submit all at once. For example, you can show four images on the same page. If the tasks are simple, you can add 10–20 tasks per suite. Don't make task suites too long because it slows down loading speed for Tolokers. A task suite may consist of a single task.

#### Toloka API {#toloka-api}

The application programming interface which describes methods (a set of classes, procedures, functions, structures, or constants) used by Toloka to interact with other computer programs, and allows you to create tasks and receive user responses. [Learn more](api/index.md)

The requests to the Toloka API are made using the [HTTPS protocol](https://en.wikipedia.org/wiki/HTTPS). The service returns data in the [JSON](https://www.json.org/json-en.html) format.

#### Toloker {#toloker}

Any person from around the world who completes tasks in Toloka and gets paid for that. Collectively, they are usually referred to as "the crowd".

#### Toloker rating {#toloker-rating}

An assessment which reflects the quality of the Toloker's [responses](#response). It takes into account responses to [control tasks](#control-task), bans, and periods without work. The rating is calculated as the weighted average value for the last few weeks. This is why the rating can have sharp drops or spikes.

#### Training {#training}

A main [pool](#pool) that consists only of [training tasks](#training-task) and can have zero cost. Use it to train Tolokers before performing real tasks if you can't use a [training pool](#training-pool) for your project.

#### Training pool {#training-pool}

A [pool](#pool) of zero-price tasks for training Tolokers. Training tasks contain correct responses and hints that are shown if the Toloker answers incorrectly.

To improve the quality of results, you can add a training pool and choose only those Tolokers who pass training successfully. [Learn more](guide/concepts/train.md)

#### Training skill {#training-skill}

A [skill](#skill) that is automatically created when the first training pool is added to the project. The skill name is `<project name> - training`. The value is the percentage of correct responses in the training pool. The skill is assigned to the Toloker after they complete the training pool.

There is only one training skill for the entire project. If you create new training pools, they will use the same skill. [Learn more](guide/concepts/nav.md)

#### Training task {#training-task}

A task that contains the correct response and a hint. If the Toloker responds incorrectly, they will see a hint and won't be able to go to the next [task suite](#task-suite) until they complete all tasks correctly. Only the first response to the task is taken into account for [quality control](#quality-control) and [skill](#skill) calculation.

Training tasks can be used in zero-price [training pools](#training-pool) to choose Tolokers who pass training.

They can also be used in regular pools as [control tasks](#control-task) with hints. For example, you can track the percentage of correct responses and [ban Tolokers](#banning-tolokers) who respond poorly. To do this, use the [Control tasks](guide/concepts/goldenset.md) quality control rule.

#### TSV {#tsv-format}

Tab-separated values. A text file format in which data is separated by a tab, and lines are separated by a newline symbol.

### V

#### View components (component type for Template Builder) {#view}

A category of [components](#component) used in Template Builder that create visual interface elements. Examples include text, list, audio player, or image. [List of views](template-builder/reference/views.md)

### X

#### XLSX {#xlsx-format}

A spreadsheet file format developed by Microsoft to replace the outdated XLS file type.