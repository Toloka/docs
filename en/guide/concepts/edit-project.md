# Editing a project

You can view the list of created [projects](../../glossary.md#project) on the **Projects** page. Open the project page to view the [list of pools](pool-main.md), [the project rating](project_rating_stat.md) and [the project statistics](project-statistic.md).

To edit project parameters, click ![](../_images/location-job/project/edit-project.svg) in the list of projects or {% if locale == "en-com" %}**Project actions → Edit**{% endif %} on the project page.

{% note alert %}

If you edit a [required field](incoming.md#required), the changes apply only to new [pools](pool-main.md). Existing [pools](../../glossary.md#pool) will continue using the previous version of the project.

{% endnote %}

## General information {#project-general-info}

#### Name to show Tolokers

[Project](../../glossary.md#project) name. You will see it on your **Projects** page.

#### Description for Tolokers

A brief explanation of what will happen in the project.

#### Private comment

A comment that you write for yourself. Tolokers won't see it.

You can make notes here that only you as a requester need to know about.

## Task interface {#project-task-interface}

#### Editor

In this block, you need to create the [task interface](../../glossary.md#task-interface) for users. You can do it manually (using HTML/CSS/JS) or using [Template Builder](../../template-builder/index.md).

To see an example of task display, click **Task preview**.

#### Data specification

A block for [input data](incoming.md) (to be uploaded as tasks), and output data (user responses) in the [task interface](spec.md).

#### Settings for displaying field tasks

Specify the settings for field task display if you use one of the field task templates.

The **Map provider for tasks** parameter allows you to specify which map the Tolokers will use. You can select one of the following options:

- Set by Toloker
- Google Maps
- Yandex.Maps

#### Common interface elements

You can specify which interface elements the Toloker will see when working on a task. To do this, click **Show common interface elements** and select the elements you need.

## Instructions for Tolokers {#project-task-instructions}

#### Instructions

Instructions are the basic rules that you need to tell Tolokers about before they start completing your tasks.

This field should contain formatted text with images, links, and tables if they're needed to make the task conditions clear.

Learn more about how to write good [instructions](instruction.md).

#### Translations

If you want labeling to be done by Tolokers from different countries, you can [translate your project into their native languages](project-languages.md).

## What's next {#what-next}

- [Create a task pool](pool-main.md) in the project.
- Learn more about how to set up a project:

    - [Writing instructions](instruction.md).
    - [Input and output data](incoming.md).
    - [Task interface](spec.md).
    - [Adapt a task for mobile devices](mobile.md).
    - [Setting up quality control](project-qa.md).

## See also {#see-also}

- [Crowdsourcing concepts: Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Crowdsourcing concepts: Interfaces](https://toloka.ai/knowledgebase/interface/)
- [Template Builder: Quick start](../../template-builder/quickstart.md)
- [{#T}](spec.md)

## For developers {#for-developers}

- [Toloka API: Editing project](../../api/concepts/edit-prj.md)
- [Toloka-Kit recipe: Edit project](../../toloka-kit/recipes/edit-project.md)

{% include [contact-support](../_includes/contact-support.md) %}