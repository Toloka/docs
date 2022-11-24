{% include [image-styles](../../../_includes/image-styles.md) %}

# Survey with Toloka template

In this tutorial, you will learn how to create a survey form and run a survey in Toloka. We will use a project preset designed specifically for this type of data collection.

Survey is a type of data collection task with several types of closed-ended and open-ended questions.

{% note info %}

To learn how to run a survey using an external survey form, see the [Survey on third-party platform](questionnaire-other.md) tutorial.

{% endnote %}

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

- See the [What tasks can't be placed in Toloka?](../concepts/unwanted.md#requirements-for-survey) section. Remember that both Tolokers and requesters are anonymous.

    - You should not collect personal data: a full name, contacts, or any other information that can be used to identify a Toloker. To determine whether a Toloker belongs to your target audience, you can ask for their city, date of birth, and age category.

    - To communicate with Tolokers, use private messages in Toloka only.

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ survey-toloka-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Select the {% if locale == "en-com" %}**Survey with Toloka template**{% endif %} preset.

1. Click {% if locale == "en-com" %}**Choose this preset**{% endif %} in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - {% if locale == "en-com" %}**Name to show Tolokers**{% endif %}: In 2–5 words, state the general idea of the project.

    - {% if locale == "en-com" %}**Description for Tolokers**{% endif %}: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    [![Create a project. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-create-project-step-1-toloka.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-create-project-step-1-toloka.png)

1. In the {% if locale == "en-com" %}**Task interface**{% endif %} section, set up what your tasks will look like.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Copy the code of the [example](https://ya.cc/t/PQl1mCfy3bVK59) and paste it to the {% if locale == "en-com" %}**Config**{% endif %} section of your project.

    1. Edit the code: change questions, hints, and answer options. For example, to configure the text of the answer option, replace the sample answers with your values in the following properties:

        - `label`: This is the label that Tolokers will see. Make sure it is clear and correct.

        - `value`: This is the value you will see in the file with the survey results.

        [![Create a project. Config question answer](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-config-question-answer.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-config-question-answer.png)

        {% note info %}

        To learn about other properties of the {% if locale == "en-com" %}**Config**{% endif %} section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/templates/survey.md).

        {% endnote %}

    1. The example code contains one question with an obvious answer to check how attentive a Toloker is. You can change this question if needed:

        [![Create a project. Config question attention](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-config-question-attention.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-config-question-attention.png)

    1. Click {% if locale == "en-com" %}**Data specification → Show specifications**{% endif %}. In the following sections, you will see the parameters which match the task interface you set up in {% if locale == "en-com" %}**Template Builder**{% endif %}:

        - {% if locale == "en-com" %}**Input data**{% endif %}: The technical parameter to run a survey.

        - {% if locale == "en-com" %}**Output data**{% endif %}: The parameters for answers given by Tolokers, including the `check` parameter for the attention check.

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

1. To save your data and continue, click {% if locale == "en-com" %}**Create a project**{% endif %}.

    {% include [tutorials-create-project-image](../_includes/tutorials/create-project-image.md) %}

## Create a pool {#pool}

{% include [toloka-requester-source-what-is-pool](../_includes/toloka-requester-source/id-toloka-requester-source/what-is-pool.md) %}

1. Click {% if locale == "en-com" %}**Create new pool**{% endif %}.

1. Under {% if locale == "en-com" %}**General information**{% endif %}, set the {% if locale == "en-com" %}**Pool name**{% endif %}.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. Clear {% if locale == "en-com" %}**My tasks may contain shocking or pornographic content**{% endif %} if your project has none of those.

    1. Select Tolokers who knows the language of your survey:

        [![Create a pool. Languages filter](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-language-filter.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-language-filter.png)

        Also you can select Tolokers based on their location, age, gender, and other parameters. Use the {% if locale == "en-com" %}**Add filter**{% endif %} button and configure the filters you need.

    1. Tasks in pools will automatically be available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the desired value: {% if locale == "en-com" %}**Toloka web version**{% endif %} or {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

    1. Filter out Tolokers who have already taken one survey. It helps prevent the situation when a Toloker completes your survey several times.

        1. Click the {% if locale == "en-com" %}**Add skill**{% endif %} button. Enter the skill name and description, and leave the skill not public.

            [![Create a pool. Add skill](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-skill-add.png =405x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-skill-add.png)

        1. Click {% if locale == "en-com" %}**Add filter → My skills**{% endif %} and select your skill from the previous step. Configure the filter to recruit Tolokers without the skill.

            [![Create a pool. My skills](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-skill-filter.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-skill-filter.png)

        You will add a rule that assigns this skill to Tolokers who have already taken one survey later.

1. Under {% if locale == "en-com" %}**Quality control**{% endif %}, set quality control rules for more accurate results.

    1. Click the {% if locale == "en-com" %}**Non-automatic acceptance**{% endif %} toggle, and specify the number of days for checking the task in the {% if locale == "en-com" %}**Review period in days**{% endif %} field (for example, 7).

        {% include [tutorials-na-acceptance](../_includes/tutorials/na-acceptance.md) %}

    1. To filter out Tolokers who complete tasks too fast, click {% if locale == "en-com" %}**Add a quality control rule → Fast responses**{% endif %}. Specify the following values:

        [![Create a pool. Fast responses rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-fast-responses.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-fast-responses.png)

        These settings mean that a Toloker who completes a task suite in less than 15 seconds will be blocked and won’t be able to access your tasks anymore.

        A task suite is a page with a number of tasks. In survey projects, a task suite must contain only one task (one survey).

        {% note tip %}

        To determine the {% if locale == "en-com" %}**Minimum time per task suite**{% endif %} value, complete your survey and record the time.

        {% endnote %}

    1. Add the rule which assigns a skill after one submitted survey. As you’ve set the filter to select Tolokers without this skill in step 3.4, the rule allows you to filter out Tolokers who have already completed your survey.

        [![Create a pool. Submitted responses rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-accomplished.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-accomplished.png)

    1. To get the required number of responses, add the {% if locale == "en-com" %}**Processing rejected and accepted assignments**{% endif %} rule. Enter the following values:

        [![Create a pool. Processing rejected and accepted assignments rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-rejected.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-rejected.png)

        This means that if you reject a Toloker’s response during the review, a new survey task will be sent to another Toloker.

    1. To automatically accept tasks from those who give correct answers to the attention check question, use the {% if locale == "en-com" %}**Control tasks**{% endif %} rule:

        [![Create a pool. Control tasks rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-control-rule.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-control-rule.png)

        The rule will work if you specify the correct answer to the attention check question in the file with tasks. You will do that later in this tutorial.

1. Click {% if locale == "en-com" %}**Show advanced settings**{% endif %}. In {% if locale == "en-com" %}**Additional settings**{% endif %}, specify {% if locale == "en-com" %}**Time per task suite, sec**{% endif %}. It should be long enough to read the instructions, wait for the task data to load, and give the answers.

1. In {% if locale == "en-com" %}**Price**{% endif %}, set up the price for answers from one Toloker.

    1. In {% if locale == "en-com" %}**Price per task suite**{% endif %}, set the amount of money to pay for survey completion by one Toloker.

        In survey projects, a task suite must contain only one task. Otherwise, a Toloker will see several identical surveys on one page. You will set the number of tasks per suite later in this tutorial.

    1. In the {% if locale == "en-com" %}**Overlap**{% endif %} field, define how many respondents you need.

        The default overlap (`3`) means that 3 Tolokers will take your survey. Change this value if needed.

        You can also increase overlap when labeling is in progress or when it’s completed.

1. To save the settings and continue, click {% if locale == "en-com" %}**Create pool**{% endif %}.

## Upload data {#upload}

At this step, upload your task data to Toloka.

1. Click {% if locale == "en-com" %}**Upload data**{% endif %}.

1. Create the tasks for Tolokers:

    1. Download the [archive with the sample files](https://labs-images-testing.s3.yandex.net/presets/sidepanel/23_poll/EN/new/sample-files.zip) and unpack it.

    1. Choose a format that is convenient for you and open the file. Change the value of the `GOLDEN:check` parameter if needed.

    1. Click {% if locale == "en-com" %}**Drop file here or select**{% endif %}, and upload the file from the previous step.

    1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

    1. Tasks are shown to Tolokers in suites. A suite is a single page with multiple tasks.

        Go to the {% if locale == "en-com" %}**Set manually**{% endif %} tab. Set one task per suite, that is a Toloker will see only one task with your survey on the page:

        [![Upload data. Tasks per suite](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-number-tasks.png =570x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-number-tasks.png)

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. Go to the pool page and click the {% if locale == "en-com" %}**Preview**{% endif %} button to check your task. Answer the questions and submit the task.

    If the page reloaded successfully, your task works correctly.

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    [![Start labeling](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-start-labeling-toloka.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-start-labeling-toloka.png)

1. In the pop-up panel, review the budget and click {% if locale == "en-com" %}**Launch**{% endif %}.

## See the results {#results}

Track the progress of responses collection on the pool page. You can start the review when the first results are received.

If you’ve set the {% if locale == "en-com" %}**Control tasks**{% endif %} rule in step 4.5 of [creating the pool](#pool), most of the tasks may be already accepted.

Review the rest of the tasks during the time period specified in the {% if locale == "en-com" %}**Review period in days**{% endif %} field in step 4.1. After that period, all responses are automatically accepted, regardless of whether answers to an attention check are correct or not.

1. Go to the pool, and click {% if locale == "en-com" %}**Review assignments**{% endif %}.

    [![See the results. Review assignments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-review-results.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-review-results.png)

1. Choose an assignment.

1. Check the response to the attention check question, and click {% if locale == "en-com" %}**Accept**{% endif %} or {% if locale == "en-com" %}**Decline**{% endif %}. For rejected responses, enter a comment to specify the reason.

    To learn about other ways of review, see the [Reviewing Tolokers’ responses](../concepts/accept.md) section.

1. After checking all the assignments, сlick the {% if locale == "en-com" %}**Download results**{% endif %} button.

    [![See the results. Download results](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/questionnaire-download-results.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/questionnaire-download-results.png)

1. In the {% if locale == "en-com" %}**Download results**{% endif %} dialog, do the following:

    1. To download the accepted answers, select {% if locale == "en-com" %}**Accepted**{% endif %}.

    1. To make the further processing of the results more convenient, clear {% if locale == "en-com" %}**Separate assignments with empty row**{% endif %}.

    1. To download the answers given by not banned Tolokers only, select {% if locale == "en-com" %}**Exclude assignments by banned Tolokers**{% endif %}.

    1. Click {% if locale == "en-com" %}**Download results**{% endif %}.

    [![See the results. Download settings](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/questionnaire-download-settings.png =458x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/questionnaire-download-settings.png)

You will get the TSV file. To process the survey results, you can open the file in Excel and save it in the XLSX format.

## Helpful tips {#tips}

- You can conduct a survey in two stages. For example, it can be useful when the general filters of the {% if locale == "en-com" %}**Audience**{% endif %} section are not enough to select Tolokers you need. Use skills:

    - In the first survey, [assign the skill](../concepts/nav-assign.md) to the relevant Tolokers.

    - In the second survey, specify the skill in the {% if locale == "en-com" %}**Audience**{% endif %} section to make the survey available to the relevant Tolokers from the first stage.

    You can notify Tolokers about the second survey using [messages](../concepts/messaging.md) to those of them who have the necessary skill.

- Check the {% if locale == "en-com" %}**Messages**{% endif %} tab regularly to get Tolokers’ reports on problems with your survey.

## Troubleshooting {#troubleshooting}

{% cut "How do I create a simple survey with no options, where the user writes an arbitrary response?" %}

In the task interface settings, use the `field.text` or `field.textarea` component. Learn more in the [Template Builder Help](../../template-builder/templates/survey.md).

{% endcut %}

## See also {#seealso}

- [Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Template Builder — survey](../../template-builder/templates/survey.md)
- [Toloka-Kit — survey](https://github.com/Toloka/toloka-kit/blob/main/examples/7.survey/simplest_survey/simplest_survey.ipynb)

## Datasets and reference {#datasets}

- [Sample dataset file with tasks](https://tlk.s3.yandex.net/knowledge-base/tasks_for_survey.tsv)

{% include [contact-support](../_includes/contact-support-help.md) %}