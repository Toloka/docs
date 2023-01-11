# Collecting offline data

In this tutorial, you will learn how to run offline data collection in Toloka. We will use a project preset designed specifically for this type of data labeling.

Offline data collection is intended for field tasks in the Toloka mobile app. A Toloker selects a point on the map, goes to the location, takes photos, and writes a comment.

{% note info %}

You may need additional projects for your task, such as dataset pre-check or checking Tolokers' responses. Learn more about this in [Decomposition of the task](../concepts/solution-architecture.md).

{% endnote %}

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ collect-offline-data-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Select the {% if locale == "en-com" %}**Spatial Crowdsourcing**{% endif %} preset.

1. Click {% if locale == "en-com" %}**Choose this preset**{% endif %} in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - {% if locale == "en-com" %}**Name to show Tolokers**{% endif %}: In 2–5 words, state the general idea of the project.

    - {% if locale == "en-com" %}**Description for Tolokers**{% endif %}: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    [![Create a project. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-create-project-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-create-project-step-1.png)

1. In the {% if locale == "en-com" %}**Task interface**{% endif %} section, set up what your tasks will look like.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Copy the code of the [example](https://ya.cc/t/Fz_--ktr3ttAX9) and paste it to the {% if locale == "en-com" %}**Config**{% endif %} section of your project. This code has validation and task layout pre-configured.

        [![Create a project. Config section](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-config-section.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-config-section.png)

    1. You can edit the code. For example, to configure the text above the {% if locale == "en-com" %}**Take photo**{% endif %} section, replace the sample text with your value in the `label` property.

        [![Create a project. Config text](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-config-text.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-config-text.png)

    1. The Toloker will be able to submit the response when they are within 50 meters of the specified location. To change this condition, replace the value of the `max` property with the desired distance:

        [![Create a project. Config distance](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-config-distance.png =560x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-config-distance.png)

        {% note info %}

        To learn about other properties of the {% if locale == "en-com" %}**Config**{% endif %} section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/reference/index.md).

        {% endnote %}

    1. {% include [toloka-requester-source-specification-definition](../_includes/toloka-requester-source/id-toloka-requester-source/specification-definition.md) %}

        {% include [toloka-requester-source-click-show-specifications](../_includes/toloka-requester-source/id-toloka-requester-source/click-show-specifications.md) %}

        - {% if locale == "en-com" %}**Input data**{% endif %}: Parameters in the file with raw task data.

        - {% if locale == "en-com" %}**Output data**{% endif %}: Parameters in the file with labeling results.

        {% include [toloka-requester-source-specification-match](../_includes/toloka-requester-source/id-toloka-requester-source/specification-match.md) %}

    1. In the **Settings for displaying field tasks** section, configure the settings which affect the task display on the map.

        - The **Title format** and **Short description format** are used to help a Toloker distinguish one task from another when they select a task on the map. These fields contain links to the input data fields to show the name of the point and its coordinates. You can leave these fields unchanged.

        - The **Map provider for tasks** field sets which map a Toloker will use when performing your tasks.

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

    Field task instructions should be easy to read on a mobile phone screen.

    {% include [toloka-requester-source-instruction-note](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-note.md) %}

1. To save your data and continue, click {% if locale == "en-com" %}**Create a project**{% endif %}.

    {% include [tutorials-create-project-image](../_includes/tutorials/create-project-image.md) %}

## Create a pool {#pool}

{% include [toloka-requester-source-what-is-pool](../_includes/toloka-requester-source/id-toloka-requester-source/what-is-pool.md) %}

1. Click {% if locale == "en-com" %}**Create new pool**{% endif %}.

1. Under {% if locale == "en-com" %}**General information**{% endif %}, set the {% if locale == "en-com" %}**Pool name**{% endif %}.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. Clear {% if locale == "en-com" %}**My tasks may contain shocking or pornographic content**{% endif %} if your project has none of those.

    1. {% include [toloka-requester-source-filters](../_includes/toloka-requester-source/id-toloka-requester-source/filters.md) %}

        [![Create a pool. Languages filter](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-language-filter.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-language-filter.png)

    1. Tasks in pools are available in the web version of Toloka and the mobile app by default. Make your tasks available in the mobile app only: add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the {% if locale == "en-com" %}**Toloka for mobile**{% endif %} option.

    1. Use the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. Under {% if locale == "en-com" %}**Quality control**{% endif %}, set quality control rules for more accurate results.

    1. Click the {% if locale == "en-com" %}**Non-automatic acceptance**{% endif %} toggle, and specify the number of days for checking the task in the {% if locale == "en-com" %}**Review period in days**{% endif %} field (for example, 21).

        {% include [tutorials-na-acceptance](../_includes/tutorials/na-acceptance.md) %}

    1. Click {% if locale == "en-com" %}**Add a quality control rule → Results of assignment review**{% endif %}, and enter the following values:

        [![Create a pool. Results of assignment review rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-results-rule.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-results-rule.png)

        This means that if 35% or more of a Toloker's responses are rejected, the Toloker is banned and can't access your tasks for 15 days. The rule takes effect after 3 responses of the Toloker are reviewed.

    1. Add the {% if locale == "en-com" %}**Processing rejected and accepted assignments**{% endif %} rule. When the overlap value is {% if locale == "en-com" %}**1**{% endif %}, you should resend assignments to the pool for other Tolokers to redo them.

        [![Create a pool. Processing rejected and accepted assignments rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-rejected.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-rejected.png)

        This means that if you reject assignments during the review, they’ll be sent for re-completion to another Toloker.

1. Click {% if locale == "en-com" %}**Show advanced settings**{% endif %}. In the {% if locale == "en-com" %}**Additional settings**{% endif %}, specify {% if locale == "en-com" %}**Time per task suite, sec**{% endif %}. It should be long enough to get to the place, find the specified point and upload the photos. For field tasks, this time is usually 86,400 seconds (24 hours).

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In {% if locale == "en-com" %}**Price per task suite**{% endif %}, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks.

        For this type of project, a task suite must contain only one task. You will set the number of tasks per suite later in this tutorial.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        For field tasks, it is usually 1. This means that each task will have 1 response.

1. To save the settings and continue, click {% if locale == "en-com" %}**Create pool**{% endif %}.

## Upload data {#upload}

At this step, upload your task data to Toloka.

1. Click {% if locale == "en-com" %}**Upload data**{% endif %}.

1. Create the tasks for Tolokers:

    1. To download a template, click one of the buttons:

        - {% if locale == "en-com" %}**Template in XLSX**{% endif %}

        - {% if locale == "en-com" %}**Template in TSV**{% endif %}

        - {% if locale == "en-com" %}**Template in JSON**{% endif %}

        For this type of project, the file with tasks must four parameters:

        - `INPUT:name`: A string with the name of the object.

        - `INPUT:position`: The coordinates of the place where the Toloker should go.

        - `AI:latitude`, `AI:longitude`: The latitude and longitude from the `INPUT:position` parameter presented separately. The values of `INPUT:position`, `AI:latitude` and `AI:longitude` should have the same accuracy, that is have the same number of digits after the decimal separator.

        ```plaintext
        INPUT:name	INPUT:position	AI:latitude	AI:longitude
        Name 1	53.947516,27.669428	53.947516	27.669428
        Name 2	53.947517,27.669429	53.947517	27.669429
        Name 3	53.947518,27.669428	53.947518	27.669428
        ```

    1. Open the downloaded file, and replace the sample values with your data. You can use a service like Google Maps to get the coordinates.

    1. Click {% if locale == "en-com" %}**Drop file here or select**{% endif %}, and upload the file you’ve just made.

    1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

    1. Go to the {% if locale == "en-com" %}**Set manually**{% endif %} tab.

    1. In this type of project, the task suite must contain only one task:

        [![Upload data. Tasks in suite](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-number-tasks.png =570x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-number-tasks.png)

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    [![Start labeling](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-start-labeling-step-2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-start-labeling-step-2.png)

1. In the pop-up panel, review the budget and click {% if locale == "en-com" %}**Launch**{% endif %}.

## See the results {#results}

Track the labeling progress on the pool page. You can start the review when the first results are received.

After the specified time period, all responses are automatically accepted, regardless of their quality.

1. Go to the pool, and click {% if locale == "en-com" %}**Review assignments**{% endif %}.

    [![See the results. Review assignments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-review-results.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-review-results.png)

1. Choose an assignment.

1. Check the responses, and click {% if locale == "en-com" %}**Accept**{% endif %} or {% if locale == "en-com" %}**Decline**{% endif %}. For rejected responses, enter a comment to specify the reason.

    {% note info %}

    To learn about other ways of review, see the [Reviewing Tolokers' responses](../concepts/accept.md) section.

    {% endnote %}

1. After checking all the assignments, click {% if locale == "en-com" %}**Download results**{% endif %}.

    [![See the results. Download results](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-results-download.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-results-download.png)

    You will get the TSV file with the labeling results.

1. To download the files Tolokers attached to the tasks, go to the pool page and click the arrow next to the {% if locale == "en-com" %}**Download results**{% endif %} button. Choose {% if locale == "en-com" %}**Download attachments**{% endif %} from the drop-down menu.

    [![See the results. Download attachments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-results-download-attachments.png =484x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/walk/walk-results-download-attachments.png)

## Troubleshooting {#troubleshooting}

{% cut "Can I limit the source of the photo to camera-only in a field task so that the Toloker can't upload a photo from anywhere else?" %}

The `accept` property of the `field.media-file` component adds different buttons for four types of uploads. To prohibit using any sources except of the camera, use the `"photo": true` property only, like it is done in the .

If you allow Tolokers to use the mobile device gallery, you can prohibit adding images without geotags to limit uploading photos taken from the Internet. To do that, specify the `"requiredCoordinates": true` property.

To learn more about setting up the `field.media-file` component, see the [Template Builder Help](../../template-builder/reference/field.media-file.md).

{% endcut %}

{% cut "How do I check the task display in the mobile Toloka app?" %}

To check the task's look-and-feel on the mobile phone screen, you can use the following buttons:

- **Preview task** on the project settings page.

- **Preview** on the pool settings page.

You can also use the mobile version of the sandbox. [Write to support](../troubleshooting/support.md#support-work-toloka) to get access to it.

{% endcut %}

## See also {#see-also}

- [Crowdsourcing concepts: Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Crowdsourcing concepts: Pricing](https://toloka.ai/knowledgebase/pricing/)

## For developers {#for-developers}

- [Toloka-Kit: Spatial crowdsourcing example](https://github.com/Toloka/toloka-kit/blob/main/examples/2.spatial_crowdsourcing/0.simplest_example/spatial_crowdsourcing.ipynb)

## Datasets and reference {#datasets}

- [Sample dataset file with tasks](https://tlk.s3.yandex.net/dataset/moscow_metro_entrance_2020_en.tsv)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles.md) %}