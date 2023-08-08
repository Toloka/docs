# Editing a project

You can view the list of created [projects](../../glossary.md#project) on the **Projects** page. Open the project page to view the [list of pools](pool-main.md), [the project rating](project_rating_stat.md) and [the project statistics](project-statistic.md).

To edit project parameters, click ![](../_images/location-job/project/edit-project.svg) in the list of projects or **Project actions → Edit** on the project page.

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

A block for [input data](incoming.md) (to be uploaded as tasks), and output data (user [task responses](../../glossary.md#task-response)) in the [task interface](spec.md).

#### Settings for displaying field tasks

Specify the settings for field task display if you use one of the field task templates.

The **Map provider for tasks** parameter allows you to specify which map the Tolokers will use. You can select one of the following options:

- Set by Toloker
- Google Maps
- Yandex.Maps

#### Common interface elements

You can specify which interface elements the Toloker will see when working on a task. To do this, click **Show common interface elements** and select the elements you need.

## Instructions for Tolokers {#project-task-instructions}

Instructions are the basic rules that you need to tell Tolokers about before they start completing your tasks.

This field should contain formatted text with images, links, and tables if they're needed to make the task conditions clear.

Learn more about how to write good [instructions](instruction.md).

## Personal data policy {#personal-data-policy}

If your project assumes the collection of any personal data, provide the information about your company in the **Personal data policy** section.

{% cut "Instruction" %}

{% include [personal-data](../_includes/toloka-requester-source/id-toloka-requester-source/personal-data.md) %}

{% endcut %}

## Translations {#translations}

If you want labeling to be done by Tolokers from different countries, you can [translate your project into their native languages](project-languages.md).

{% note tip "How to work via Toloka API" %}

To edit a project using Toloka API, send a `PUT` request with all the project parameters including the ones you want to modify:

```bash
curl -X PUT 'https://toloka.dev/api/v1/projects/118252' \
     -H 'Content-Type: application/json' \
     -H 'Authorization: ApiKey PlaceYourRealApiKey_Here' \
     -d '{"id":"118252","public_name":"Elephant color (advanced)","public_description":"What color is the elephant in the picture?","public_instructions":"<p>Look at the picture and decide what color the elephant is.</p> You can zoom in or out using the buttons:</p> <img src=\"disc/img1.png>\"","private_comment":"My first project","task_spec":{"input_spec":{"image":{"type":"URL","required":true,"hidden":false}},"output_spec":{"result":{"type":"string","required":true,"hidden":false}},"view_spec":{"assets":{"script_urls":["library1.js","library2.js"]},"markup":"<task interface code>","script":"<JavaScript code>","styles":"<CSS code>","settings":{"showSkip":true,"showTimer":true,"showTitle":true,"showSubmit":true,"showFullscreen":true,"showInstructions":true,"showFinish":true,"showMessage":true,"showReward":true}}},"assignments_issuing_type":"AUTOMATED","assignments_automerge_enabled":false,"max_active_assignments_count":15,"quality_control":{"configs":[{"collector_config":{"type":"SKIPPED_IN_ROW_ASSIGNMENTS"},"rules":[{"conditions":[{"key":"skipped_in_row_count","operator":"GTE","value":10}],"action":{"type":"REJECT_ALL_ASSIGNMENTS","parameters":{"public_comment":"Skipped more than 10 task suites in a row"}}}]}]},"localization_config":{"default_language":"EN"}}'
```

Refer to the [Edit project](https://toloka.ai/docs/api/api-reference/#put-/projects/-id-) section of the Toloka API documentation for more details about the request, its parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

{% endnote %}

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

- [Toloka API: Editing project](https://toloka.ai/docs/api/api-reference/#put-/projects/-id-)
- [Toloka-Kit recipe: Edit project](../../toloka-kit/recipes/edit-project.md)

{% include [contact-support](../_includes/contact-support.md) %}