# Creating a project

If you already have a project and you want to create an identical one, [clone](#clone) the existing project. If not, create a new project.

## How to create a project {#new-project}

The project defines what the task will look like for a Toloker.

To get better results, make tasks as simple as possible and divide complex tasks into several projects.

{% note info %}

You can first create and test your project for free in the [sandbox](sandbox.md) and then [move](sandbox.md#export) it to the Toloka production version.

{% endnote %}

To create a project in the interface:

1. Choose a preset:

    1. Click the **Create a project** button on the **Projects** page.

    1. Choose a preset. The preset contains pre-configured [input and output data fields](incoming.md) and [the task interface](spec.md), which you can edit.

        If there is no suitable preset, choose an empty preset.

        {% note tip %}

        If you unsure which preset to choose, you can ask Toloka experts to create a project for you. To do that,

        - click **Get expert help**,
        - select the way Toloka can contact you (WhatsApp, Telegram, Viber, email, or phone),
        - enter your phone number or email address,
        - briefly describe the project and the results you want to get.

        Toloka engineering team will contact you for more details and explain your further steps.

        {% endnote %}

1. Provide general information:

    1. Enter the **Name to show Tolokers** and **Description for Tolokers**. Tolokers will see this in the task list.

    1. Optionally add a **Private comment**.

1. Edit the task interface:

    {% list tabs %}

    - Template Builder

      1. [Create the task interface](../../template-builder/index.md).

      1. Click **Show specifications** to see the input and output data fields.

          Input data fields are created from the code on the **Example of input data** tab.

          The output data fields depend on the components that use `data.output` and values supported by it.

          Learn more about [input and output data fields](../../template-builder/operations/create-specs.md) in the Template Builder Help.

      1. Specify the settings for field task display if you use one of the field task templates.

    - HTML/JS/CSS editor

      1. [Describe the task interface](spec.md).

      1. Add fields for [input and output data](incoming.md) in the **Data specification** block.

      1. Specify the settings for field task display if you use one of the field task templates.

    {% endlist %}

1. [Write guidelines](instruction.md) for Tolokers.

    You can prepare instructions in HTML format, then copy and paste into the editor. Click **<>** to switch to HTML mode.

1. Optionally, if your project assumes the collection of any personal data:

    {% include [personal-data](../_includes/toloka-requester-source/id-toloka-requester-source/personal-data.md) %}

1. Optionally, add translations to other languages:

    1. Select the source language and the target languages.

    1. Fill in the fields in the table.

    1. Click **Finish**.

After creating the project, add a [task pool](pool-main.md) to it. You can also set up [quality control](control.md) in the project.

{% note tip "How to work via Toloka API" %}

To create a project using Toloka API, send a `POST` request with the information about the project:

```bash
curl -X POST 'https://toloka.dev/api/v1/projects' \
     -H 'Content-Type: application/json' \
     -H 'Authorization: ApiKey PlaceYourRealApiKey_Here' \
     -d '{"public_name":"Elephant color","public_description":"What color is the elephant in the picture?","public_instructions":"<p>Look at the picture and decide what color the elephant is.</p> You can zoom in or out using the buttons:</p> <img src=\"disc/img1.png>\"","private_comment":"My first project","task_spec":{"input_spec":{"image":{"type":"URL","required":true,"hidden":false}},"output_spec":{"result":{"type":"string","required":true,"hidden":false}},"view_spec":{"assets":{"script_urls":["library1.js","library2.js"]},"markup":"<task interface code>","script":"<JavaScript code>","styles":"<CSS code>","settings":{"showSkip":true,"showTimer":true,"showTitle":true,"showSubmit":true,"showFullscreen":true,"showInstructions":true,"showFinish":true,"showMessage":true,"showReward":true}}},"assignments_issuing_type":"AUTOMATED","assignments_automerge_enabled":false,"max_active_assignments_count":15,"quality_control":{"configs":[{"collector_config":{"type":"SKIPPED_IN_ROW_ASSIGNMENTS"},"rules":[{"conditions":[{"key":"skipped_in_row_count","operator":"GTE","value":10}],"action":{"type":"REJECT_ALL_ASSIGNMENTS","parameters":{"public_comment":"Skipped more than 10 task suites in a row"}}}]}]},"localization_config":{"default_language":"EN"}}'
```

Refer to the [Create project](https://toloka.ai/docs/api/api-reference/#post-/projects) section of the Toloka API documentation for more details about the request, its parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

{% endnote %}

{% include [project-moderation](../_includes/toloka-requester-source/id-toloka-requester-source/project-moderation.md) %}

## How to clone a project {#clone}

You can view the list of created projects on the **Projects** page. Open the project page to view the list of pools, [project rating](project_rating_stat.md), and [project statistics](project-statistic.md).

To clone a project, click ![](../_images/location-job/project/clone-project.svg) in the list of projects or select **Project actions → Clone** on the project page.

{% note warning %}

Quality control in the project is not cloned.

{% endnote %}

If you need to change the project settings, [open edit mode](edit-project.md).

## How to pin a project {#pin}

{% include [toloka-requester-source-pin-project](../_includes/toloka-requester-source/id-toloka-requester-source/pin-project.md) %}

## What's next {#what_next}

- [Create a task pool](pool-main.md) in the project.
- Learn more about how to set up a project:

    - [Writing instructions](instruction.md).
    - [Input and output data](incoming.md).
    - [Task interface](spec.md).
    - [Adapt a task for mobile devices](mobile.md).
    - [Setting up quality control](project-qa.md).

## See also {#see-also}

- [Efficiency indicators: Quality of interface](efficiency-metrics/interface-quality.md)

## For developers {#for-developers}

- [Toloka API: Creating project](https://toloka.ai/docs/api/api-reference/#post-/projects)
- [Toloka-Kit recipe: Create project](../../toloka-kit/recipes/create-project.md)

## Troubleshooting {#troubleshooting}

{% cut "General task settings" %}

{% include [faq-complex-task](../_includes/faq/questions-about-templates/complex-task.md) %}

{% include [faq-many-classes](../_includes/faq/project-settings/many-classes.md) %}

{% include [faq-validation-depending-checkbox](../_includes/faq/questions-about-templates/validation-depending-checkbox.md) %}

{% include [faq-how-many-tasks-in-suite](../_includes/faq/adding-tasks-to-the-pool/how-many-tasks-in-suite.md) %}

{% endcut %}

{% cut "Setting up tasks with images" %}

{% include [faq-irrelevant-products](../_includes/faq/questions-about-templates/irrelevant-products.md) %}

{% include [faq-elements-web-pages](../_includes/faq/questions-about-templates/elements-web-pages.md) %}

{% include [faq-selecting-objects](../_includes/faq/questions-about-templates/selecting-objects.md) %}

{% include [faq-different-areas](../_includes/faq/questions-about-templates/different-areas.md) %}

{% include [faq-input-data-labeling-image](../_includes/faq/questions-about-templates/input-data-labeling-image.md) %}

{% include [faq-mark-triangles](../_includes/faq/questions-about-templates/mark-triangles.md) %}

{% include [faq-large-number-objects](../_includes/faq/questions-about-templates/large-number-objects.md) %}

{% include [faq-control-area-selection](../_includes/faq/questions-about-templates/control-area-selection.md) %}

{% include [faq-paired-images-comparison](../_includes/faq/questions-about-templates/paired-images-comparison.md) %}

{% endcut %}

{% cut "Setting up tasks with texts" %}

{% include [faq-text-classification](../_includes/faq/questions-about-templates/text-classification.md) %}

{% include [faq-input-output-text-fields](../_includes/faq/questions-about-templates/input-output-text-fields.md) %}

{% include [faq-simple-survey](../_includes/faq/questions-about-templates/simple-survey.md) %}

{% include [faq-survey-single-question](../_includes/faq/questions-about-templates/survey-single-question.md) %}

{% endcut %}

{% include [faq-limit-source-photo](../_includes/faq/questions-about-templates/limit-source-photo.md) %}

{% include [contact-support](../_includes/contact-support.md) %}