# Voice recording

In this tutorial, you will learn how to run voice recording in Toloka. We will use a project preset designed specifically for this type of data labeling.

Voice recording is a type of data labeling task with the text block to read and the voice recorder button. Using the Toloka mobile app, Tolokers should tap the button and read the text aloud. After getting the results, you can listen to the recordings and download them.

{% note info %}

You may need additional projects for your task, such as dataset pre-check or checking Tolokers' responses. Learn more about this in [Decomposition of the task](../concepts/solution-architecture.md).

{% endnote %}


## Prerequisites {#prerequisites}

Before you begin:

- Make sure you are [registered](../concepts/access.md) in Toloka as a requester.
- [Top up](../concepts/refill.md) your Toloka account. If you are unsure about the budget, you can do that later in this tutorial. Toloka will display the budget estimate for your project.

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}


1. Follow [this link]({{ voice-recording-preset }}), or create a project manually:

    1. In the main menu, choose the {% if locale == "en-com" %}**Projects**{% endif %} tab, and click {% if locale == "en-com" %}**Create a project**{% endif %}.
    1. Select the {% if locale == "en-com" %}**Voice recording**{% endif %} preset.

1. Click {% if locale == "en-com" %}**Choose solution**{% endif %} in the pop-up tab.

## Create a project {#project}

{% include [toloka-requester-source-who-are-tolokers](../_includes/toloka-requester-source/id-toloka-requester-source/who-are-tolokers.md) %}


1. {% include [toloka-requester-source-add-name-description](../_includes/toloka-requester-source/id-toloka-requester-source/add-name-description.md) %}

    - {% if locale == "en-com" %}**Name to show performers**{% endif %}: In 2–5 words, state the general idea of the project.
    - {% if locale == "en-com" %}**Description for performers**{% endif %}: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

1. In the {% if locale == "en-com" %}**Task interface**{% endif %} section, set up what your tasks will look like. This preset has a task template with layout and validation pre-configured.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. In the {% if locale == "en-com" %}**Config**{% endif %} section, you can edit the code to change the appearance and layout of the task elements. For a trial pool, keep the code as is.
    To learn about the properties of the {% if locale == "en-com" %}**Config**{% endif %} section, their possible values and the impact on the task interface, see the [Template Builder Help](https://toloka.ai/en/docs/template-builder/reference/).

    1. In the {% if locale == "en-com" %}**Input data example**{% endif %} section, you can change the sample text. This text is only used to display the task interface preview on the right.
    1. {% include [toloka-requester-source-specification-definition](../_includes/toloka-requester-source/id-toloka-requester-source/specification-definition.md) %}

    {% include [toloka-requester-source-click-show-specifications](../_includes/toloka-requester-source/id-toloka-requester-source/click-show-specifications.md) %}

    - {% if locale == "en-com" %}**Input data**{% endif %}: Parameters in the file with raw task data.
    - {% if locale == "en-com" %}**Output data**{% endif %}: Parameters in the file with labeling results.

    {% include [toloka-requester-source-specification-match](../_includes/toloka-requester-source/id-toloka-requester-source/specification-match.md) %}

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

    {% include [toloka-requester-source-instruction-note](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-note.md) %}

1. To save your data and continue, click {% if locale == "en-com" %}**Create a project**{% endif %}.

## Create a pool {#pool}

{% include [toloka-requester-source-what-is-pool](../_includes/toloka-requester-source/id-toloka-requester-source/what-is-pool.md) %}


1. Click {% if locale == "en-com" %}**Create new pool**{% endif %}.
1. Under {% if locale == "en-com" %}**General information**{% endif %}, set the {% if locale == "en-com" %}**Pool name**{% endif %}.
1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. Clear {% if locale == "en-com" %}**My tasks may contain shocking or pornographic content**{% endif %} if your project has none of those.
    1. {% include [toloka-requester-source-filters](../_includes/toloka-requester-source/id-toloka-requester-source/filters.md) %}

    1. For example, add the {% if locale == "en-com" %}**Languages**{% endif %} filter:
    1. It is best to launch voice recording tasks in the Toloka mobile app so that Tolokers can record audio directly in a task using the device's built-in voice recorder. Add the {% if locale == "en-com" %}**Client**{% endif %} filter and select {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

    1. Use the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

1. In {% if locale == "en-com" %}**Quality control**{% endif %}, set quality control rules for more accurate results.
    1. Click the {% if locale == "en-com" %}**Non-automatic acceptance**{% endif %} toggle, and specify the number of days for checking the task in the {% if locale == "en-com" %}**Review period in days**{% endif %} field (for example, 21).

    #### What is non-automatic acceptance (assignment review)?

    The non-automatic acceptance option allows you to review completed assignments before accepting them and paying for them. If the Toloker didn't follow the instructions, you can reject the assignment.

    1. The {% if locale == "en-com" %}**Voice recording**{% endif %} preset has the pre-configured quality control rules:
    - In most cases, you can keep the {% if locale == "en-com" %}**Fast responses**{% endif %} rule as is. It filters out Tolokers who complete tasks too fast. The default settings mean that Tolokers are banned from the project for 1 day if they complete tasks in 4 out of 5 task suites in less than 15 seconds.
    - Delete the pre-configured {% if locale == "en-com" %}**Majority vote**{% endif %} rule.

    1. For a trial pool, the settings you’ve just made are enough. You can get better results if you set the additional quality control rules.
    #### The additional quality control rules

    1. Add the {% if locale == "en-com" %}**Results of assignment review**{% endif %} quality control rule and enter the following values:
    This means that if 35% or more of a Toloker's responses are rejected, the Toloker is banned and can't access your tasks for 15 days. The rule takes effect after 3 responses of the Toloker are reviewed.

    1. Add the [Processing rejected and accepted assignments](../concepts/reassessment-after-accepting.md) rule:
    This means that if you reject assignments during the review, they'll be sent for re-completion to another Toloker.

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In {% if locale == "en-com" %}**Price per task suite**{% endif %}, set the amount of money to pay per task suite done by one Toloker.

    A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 8–10 tasks per suite.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

    The value depends on how many recordings of the same phrase you want to collect. If one is enough, set `1`.

    1. At the bottom of the {% if locale == "en-com" %}**Price**{% endif %} section, you see {% if locale == "en-com" %}**Price per 1 task**{% endif %}. This is the amount of money paid per task.

1. Click {% if locale == "en-com" %}**Show advanced settings**{% endif %}. In {% if locale == "en-com" %}**Additional settings**{% endif %}, specify the {% if locale == "en-com" %}**Time per task suite, sec**{% endif %}.

    This time should be enough to read the instructions and load the task (for example, 1,200 seconds).

1. To save the settings and continue, click {% if locale == "en-com" %}**Create pool**{% endif %}.

## Upload data {#upload}

At this step, upload your task data to Toloka.

1. Click {% if locale == "en-com" %}**Upload data**{% endif %}.
1. Create the tasks for Tolokers:
    1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

    For this type of project, the file with tasks must have one parameter. Its name equals `INPUT:text`, and the values are texts.

    ```json
    INPUT:text
    Does white chocolate have cocoa?
    How many rings are there in the Olympic Games symbol?
    What is the capital of Australia?
    ```

    1. Open the downloaded file, and replace the sample values with your texts.
    1. Click {% if locale == "en-com" %}**Drop file here or select**{% endif %}, and upload the file you’ve just made.
    1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

    - {% if locale == "en-com" %}**General tasks**{% endif %}: These are tasks for Tolokers to label.
    - {% if locale == "en-com" %}**Control tasks**{% endif %}: These are tasks with predefined answers used to control the quality of responses. For this project, you don’t need control tasks.
    - {% if locale == "en-com" %}**Training tasks**{% endif %}: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

    For example, you can add 5 general tasks per suite:

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).
1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

1. In the pop-up panel, review the budget and click {% if locale == "en-com" %}**Launch**{% endif %}.

## See the results {#results}

Track the labeling progress on the pool page. You can start the review when the first results are received.

After the time period specified in step 4.1 of [creating the pool](#pool), all responses are automatically accepted, regardless of their quality.

1. Go to the pool, and click {% if locale == "en-com" %}**Review assignments**{% endif %}.
1. Choose an assignment.
1. Check the responses, and click {% if locale == "en-com" %}**Accept**{% endif %} or {% if locale == "en-com" %}**Decline**{% endif %}. For rejected responses, enter a comment to specify the reason.
    {% note info %}

    To learn about other ways of review, see the [Reviewing Tolokers' responses](../concepts/accept.md) section.

    {% endnote %}

1. After checking all the assignments, click {% if locale == "en-com" %}**Download results**{% endif %}.
    You will get the TSV file with the labeling results.

1. To download the recordings, click the arrow next to the {% if locale == "en-com" %}**Download results**{% endif %} button. Choose {% if locale == "en-com" %}**Download attachments**{% endif %} from the drop-down menu.


## Troubleshooting {#troubleshooting}

#### How do I show two different versions of the text to Tolokers?

If you pass texts to the input data, you can upload 2 different tasks to the pool: pass Text 1 in the `INPUT: <input field name>` field of Task 1. In Task 2, use this field to pass Text 2.

If the text is specified in the task interface, then clone the project. To limit a Toloker to doing only one task in your project, use the [Submitted responses](../concepts/submitted-answers.md) rule. You can assign a skill or ban the Toloker after they submit one response.

#### How do I make an image expand to its maximum size on click?

The `popup` property of the component [view.image](https://toloka.ai/en/docs/template-builder/reference/view.image) specifies whether opening a full-size image with a click is allowed. By default, it is `true` (allowed).


## See also {#seealso}

- [Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Pricing](https://toloka.ai/knowledgebase/pricing/)
