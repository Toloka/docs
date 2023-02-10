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

### [Anti-fraud system](https://toloka.ai/anti-fraud/) {#anti-fraud}

- Platform-wide ban for fraudulent Tolokers.

- Behavior analysis system.

- Multilayer technologies to detect and prevent all types of fraud.

### Protect your project {#protection-from-cheaters}

{% include [toloka-requester-source-anti-fraud](../_includes/toloka-requester-source/id-toloka-requester-source/anti-fraud.md) %}

To protect your project from cheaters, you can use the quality control rules:

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