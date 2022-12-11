# Sentiment analysis and content moderation

In this tutorial, you will learn how to run content moderation in Toloka. We will use a project preset designed specifically for this type of data labeling.

Content moderation is a type of data labeling task with a text and a number of response options. Tolokers read the text and choose one of the given answer options. After that, they can specify their answer using an additional question with checkboxes.

[![Sentiment analysis and content moderation](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-preview-interface.png =400x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-preview-interface.png)

Use this preset when you need to:

- Moderate comments and nicknames on a forum.

- Check ads on a site, product reviews in a store, or messages in social networks.

- Check for the presence of a brand or company name.

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ content-moderation-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Select the {% if locale == "en-com" %}**Sentiment analysis & Content moderation**{% endif %} preset.

1. Click {% if locale == "en-com" %}**Choose this preset**{% endif %} in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - {% if locale == "en-com" %}**Name to show Tolokers**{% endif %}: In 2–5 words, state the general idea of the project.

    - {% if locale == "en-com" %}**Description for Tolokers**{% endif %}: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    [![Create a project. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-create-project-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-create-project-step-1.png)

1. In the {% if locale == "en-com" %}**Task interface**{% endif %} section, set up what your tasks will look like. This preset has a task template with validation, keyboard shortcuts, and task layout pre-configured.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Write the first question Tolokers will see in your task. All tasks in a project use the same question.

        [![Create a project. Config question](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-config-question-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-config-question-1.png)

    1. Set answer options. In the {% if locale == "en-com" %}`options`{% endif %} list, replace the sample answers with your values in the following properties:

        - {% if locale == "en-com" %}`label`{% endif %}: This is the label that Tolokers will see. Make sure it is clear and correct.

        - {% if locale == "en-com" %}`value`{% endif %}: This is the value you will see in the file with the labeling results.

        [![Create a project. Config answer options](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-config-answer-options-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-config-answer-options-1.png)

    1. When a Toloker selects an option which requires additional information, the second question with checkboxes appears. You can change the condition under which the additional question becomes visible. To to that, replace the value of the {% if locale == "en-com" %}`to`{% endif %} propertу with one of the values you’ve already specified in the {% if locale == "en-com" %}`value`{% endif %} properties in the previous step:

        [![Create a project. Config answer options](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-config-condition.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-config-condition.png)

    1. Configure the text and the answer options for the additional question:

        [![Create a project. Config condition](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/config-answer-options-2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/config-answer-options-2.png)

    1. In the {% if locale == "en-com" %}**Input data example**{% endif %} section, add a sample text. It is only used to display the task interface preview on the right.

        [![Create a project. Input data example](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-input-example.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-input-example.png)

    1. {% include [toloka-requester-source-specification-definition](../_includes/toloka-requester-source/id-toloka-requester-source/specification-definition.md) %}

        {% include [toloka-requester-source-click-show-specifications](../_includes/toloka-requester-source/id-toloka-requester-source/click-show-specifications.md) %}

        - {% if locale == "en-com" %}**Input data**{% endif %}: Parameters in the file with raw task data.
        - {% if locale == "en-com" %}**Output data**{% endif %}: Parameters in the file with labeling results.

        {% include [toloka-requester-source-specification-match](../_includes/toloka-requester-source/id-toloka-requester-source/specification-match.md) %}

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

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

        For example, add the {% if locale == "en-com" %}**Languages**{% endif %} filter:

        [![Create a pool. Languages filter](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-language-filter.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-language-filter.png)

    1. Tasks in pools will automatically be available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the desired value: {% if locale == "en-com" %}**Toloka web version**{% endif %} or {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

    1. Use the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. Under {% if locale == "en-com" %}**Quality control**{% endif %}, set quality control rules for more accurate results.

    1. To filter out Tolokers who complete tasks too fast, edit the pre-configured {% if locale == "en-com" %}**Fast responses**{% endif %} rule. Specify the following values:

        [![Create a pool. Fast responses rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-fast-responses.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-fast-responses.png)

        These settings mean that a Toloker who completes a task suite in less than 20 seconds will be suspended and won't be able to access your tasks for 10 days.

        A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 10–20 tasks per suite.

        {% note tip %}

        To determine the {% if locale == "en-com" %}**Minimum time per task suite**{% endif %} value, complete your task suite and record the time. If you ban users for one fast response, then set a minimal time. If you do it after several fast responses, increase the time slightly.

        {% endnote %}

    1. Keep the pre-configured {% if locale == "en-com" %}**Majority vote**{% endif %} rule as is. It accepts the most popular response as the correct one, and allows you to filter out Tolokers who answer incorrectly. The default settings mean that Tolokers who give correct responses to less than 40% of tasks are banned from the project for 1 day. {% if locale == "en-com" %}**Accept as majority**{% endif %} set to `2` means that 2 similar responses out of all responses given to a single task will be considered as the correct answer.

    1. Click {% if locale == "en-com" %}**Add a quality control rule → Control tasks**{% endif %}, and enter the following values:

        [![Create a pool. Control tasks rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-control-rule.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-control-rule.png)

        This means that a Toloker who gives more than 40% of incorrect responses will be blocked and won't be able to complete tasks in this project for 10 days.

1. Click {% if locale == "en-com" %}**Show advanced settings**{% endif %}. In {% if locale == "en-com" %}**Additional settings**{% endif %}, specify {% if locale == "en-com" %}**Time per task suite, sec**{% endif %}. It should be long enough to read the instructions and wait for task data to download (for example, 150 seconds).

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In {% if locale == "en-com" %}**Price per task suite**{% endif %}, set the amount of money to pay per a page with tasks done by one Toloker.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        For content moderation tasks, it is usually 3–5. The default value (`3`) means that each task will have 3 responses.

1. To save the settings and continue, click {% if locale == "en-com" %}**Create pool**{% endif %}.

## Upload data {#upload}

At this step, upload your task data to Toloka.

1. Click {% if locale == "en-com" %}**Upload data**{% endif %}.

1. Create the tasks for Tolokers:

    1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

        For this type of project, the file with tasks must have one parameter. Its name equals `INPUT:comment`, and the values are texts.

        ```plaintext
        INPUT:comment
        This movie is terrible with only a few funny scenes.
        Hard to beat Cinnamon Toast Crunch
        The trigger stopped working after 5 uses. Really
        ```

    1. Open the downloaded file, and replace the sample comments with your texts.

    1. Click {% if locale == "en-com" %}**Drop file here or select**{% endif %}, and upload the file you’ve just made.

    1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

    - {% if locale == "en-com" %}**General tasks**{% endif %}: These are tasks for Tolokers to label.

    - {% if locale == "en-com" %}**Control tasks**{% endif %}: These are tasks with predefined answers used to control the quality of responses. You will create them in the next step.

    - {% if locale == "en-com" %}**Training tasks**{% endif %}: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

    For example, you can add 9 general tasks and 1 control task per suite:

    [![Upload data. Tasks per suite](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-smart-mixing.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-smart-mixing.png)

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.

1. To create control tasks, add correct answers to some of your tasks.

    1. Click {% if locale == "en-com" %}**Edit**{% endif %}.

        [![Upload data. Click Edit](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-edit-button.png =610x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-edit-button.png)

    1. On the {% if locale == "en-com" %}**Edit tasks**{% endif %} page, click {% if locale == "en-com" %}**Create control tasks**{% endif %}.

        [![Upload data. Create control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-create-control-button.png =500x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-create-control-button.png)

    1. Select all the checkboxes, and specify the correct answer for a task. Then, click the {% if locale == "en-com" %}**Save and go to next**{% endif %} button. Add several control tasks this way.

        [![Upload data. Create control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-creating-control-task.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-creating-control-task.png)

    1. Note the {% if locale == "en-com" %}**Distribution of correct responses for control tasks**{% endif %} graph on the right side of the page. It shows how many control tasks of each type you have. We recommend adding an equal quantity of each correct response.

        [![Upload data. Distribution of correct responses for control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-distibution.png =440x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-distibution.png)

    1. When you are done adding control tasks, click the pool name in the menu.

        [![Upload data. Click pool name](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-pool-name.png =600x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-pool-name.png)

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    [![Start labeling. Step 2](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-start-labeling.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-start-labeling.png)

1. In the pop-up panel, review the budget and click {% if locale == "en-com" %}**Launch**{% endif %}.

## See the results {#results}

1. You can see the labeling progress on the pool page. Wait until the labeling is completed. Refresh the page to check the progress.

    [![See the results. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-see-results-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-see-results-step-1.png)

1. When the labeling is complete, click the arrow next to the {% if locale == "en-com" %}**Download results**{% endif %} button and choose {% if locale == "en-com" %}**Run Dawid-Skene model**{% endif %} from the drop-down menu. Click {% if locale == "en-com" %}**Yes**{% endif %} in the pop-up window.

    [![See the results. Step 2](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-see-results-step-2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/content-moderation/content-moderation-see-results-step-2.png)

1. Open the same drop-down menu again, and click {% if locale == "en-com" %}**View aggregations list**{% endif %}.

1. Wait until the aggregation is complete, and click {% if locale == "en-com" %}**Download**{% endif %}. You will get a TSV file with the labeling results:

    - {% if locale == "en-com" %}**INPUT**{% endif %}: The data you uploaded for labeling.

    - {% if locale == "en-com" %}**OUTPUT**{% endif %}: The results of labeling (answers given by Tolokers).

    - {% if locale == "en-com" %}**CONFIDENCE**{% endif %}: The response significance according to the [Dawid-Skene model](../concepts/result-aggregation.md#dawid-skene).

## See also {#seealso}

- [Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Toloka-Kit — sentiment analysis](https://github.com/Toloka/toloka-kit/blob/main/examples/5.nlp/sentiment_analysis/sentiment_analysis.ipynb)

## Datasets and reference {#datasets}

- [Sample dataset file with tasks](https://tlk.s3.yandex.net/knowledge-base/reviews.tsv)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles.md) %}