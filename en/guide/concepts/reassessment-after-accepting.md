# Processing rejected and accepted assignments

You can enable the [Non-automatic acceptance](offline-accept.md) option to [reject or accept](accept.md) assignments that Tolokers completed. Assignments are rejected and accepted on a page-by-page basis.

{% note info %}

After the end of the review period specified in the **Non-automatic acceptance** option, assignments are accepted automatically.

{% endnote %}


## When to use {#when-use}

This rule is helpful when you need to:
- Resend rejected assignments for re-completion to other Tolokers.

    If you rejected an assignment, you may want it to be completed by another Toloker instead of the one whose response you rejected. To do this, you can increase the [overlap](../../glossary.md#overlap-ru) for this assignment only. This is especially helpful if you have the overlap value set to 1.

- Save money on re-completing assignments that you have already accepted.

    If you reviewed and accepted an assignment, it may not make sense for other users to complete the same assignment. To avoid this, you can reduce the overlap for accepted assignments only.

## Rule settings {#rule}

{% note warning %}

All fields in this rule are required. If you don't fill in at least one of them, you won't be able to save the rule.

{% endnote %}



Field
 |
Overview

----- | -----
{% if locale == "en-com" %}**If**{% endif %} | A condition for performing the action in the {% if locale == "en-com" %}**then**{% endif %} field:<br/>- {% if locale == "en-com" %}**submitted assignments**{% endif %} — The number of [task suites](../../glossary.md#task-page-ru) that are completed and awaiting review.<br/>    <br/>- {% if locale == "en-com" %}**approved assignments**{% endif %} — The number of task suites accepted after the review.<br/>    <br/>- {% if locale == "en-com" %}**rejected assignments**{% endif %} — The number of task suites rejected after the review.<br/>    <br/>- {% if locale == "en-com" %}**assignment becomes approved**{% endif %} — The task suite was accepted after the review.<br/>    <br/>- {% if locale == "en-com" %}**assignment becomes approved after rejection**{% endif %} — The task suite was first rejected, but then accepted after the review.<br/>    <br/>    {% note info %}<br/>    <br/>    Note that you can't change the task status if the task [pool](../../glossary.md#pool-ru) was [archived](pool-archive.md).<br/>    <br/>    {% endnote %}<br/>    <br/>- {% if locale == "en-com" %}**assignment becomes rejected**{% endif %} — The task suite was rejected after the review.<br/><br/>To add multiple conditions, click ![](../_images/add.svg).
{% if locale == "en-com" %}**then**{% endif %} | Action to perform for the condition:<br/><br/>- {% if locale == "en-com" %}**extend overlap by**{% endif %} — Resend the [task suite](../../glossary.md#task-page-ru) for completion to other Tolokers.<br/>    <br/>    If you want an assignment to be automatically reassigned even if your pool is already completed and closed, turn on the option {% if locale == "en-com" %}**Open pool if closed**{% endif %}.<br/>    <br/>- {% if locale == "en-com" %}**extend overlap by**{% endif %} — Decrease the number of times a task suite can be completed by Tolokers. For example, use this action to cancel the recompletion of accepted assignments.


## Rule example {#examples}

The task is to send rejected and recompleted assignments for review. Or assign them to new Tolokers after rejection.

#### Correct settings
![](../_images/control-rules/reassessment-after-accepting/qcr-reassessment-after-accepting_example1.png)
A Toloker's assignments rejected after the review are sent to another Toloker for recompletion.

#### Incorrect settings
![](../_images/control-rules/reassessment-after-accepting/qcr-reassessment-after-accepting_example_2.png)
A Toloker's assignments rejected after the review are not sent to another Toloker for recompletion.


## Troubleshooting {#troubleshooting}

#### What overlap should I set?

Overlap defines how many Tolokers complete the same pool task.

The best overlap is an overlap that provides satisfying quality of results. For most tasks that are not [reviewed](../../glossary.md#left-off-acceptance-ru), overlap from <q>3</q> to <q>5</q> is enough. If the tasks are simple, overlap of <q>3</q> is likely to be enough. For tasks that are reviewed, set overlap to <q>1</q>.

#### Can I change overlap after the pool is started?

Yes. [Open edit mode for the pool](pool-edit.md) and set a new overlap value. You don't need to restart the pool. Updating the settings is usually fast, but if there are many tasks, it may take several minutes.


{% include [contact-support](../_includes/contact-support-help.md) %}
