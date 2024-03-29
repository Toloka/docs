# Survey on third-party platform

In this tutorial, you will learn how to use Toloka to run a survey created on a third-party platform.

You may need a third-party platform, when:

- Your survey form is too long and complicated to be created in Toloka.

- You are already conducting the survey using other channels to reach out to respondents, and would like to aggregate all the results in one place.

In Toloka, you can place a link to your survey in the task interface. To enable a Toloker to confirm survey completion, show a code to each respondent who takes the survey on the third-party platform. The respondent will need to copy the code and paste it to the task in Toloka. You will see this code in the results file and will be able to check if it is correct.

{% include [other-survey-solutions](../_includes/tutorials/other-survey-solutions.md) %}

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

- See the [What tasks can't be placed in Toloka?](../concepts/unwanted.md#requirements-for-survey) section. Remember that both Tolokers and requesters are anonymous.

    - You should not collect personal data: a full name, contacts, or any other information that can be used to identify a Toloker. To determine whether a Toloker belongs to your target audience, you can ask for their city, date of birth, and age category.

    - To communicate with Tolokers, use private messages in Toloka only.

## Create a project {#project}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ survey-other-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Click **Do it myself**.

    1. Select the **Survey on third-party platform** preset.

1. Click **Choose this preset** in the pop-up tab.

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - **Name to show Tolokers**: In 2–5 words, state the general idea of the project.

    - **Description for Tolokers**: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    ![Create a project. Step 1](../_images/tutorials/questionnaire/survey-create-project-step-1.png =700x)

1. In the **Task interface** section, set up what your tasks will look like. This preset has a task template with validation and task layout pre-configured.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. In the **Config** section, you can edit the pre-configured code. For example, to change the description, replace the sample text with your value in the `label` property.

        ![Create a project. Config question description](../_images/tutorials/questionnaire/survey-config-question-description.png =700x)

        {% note info %}

        To learn about other properties of the **Config** section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/templates/survey.md).

        {% endnote %}

    1. In the **Input data example** section, you can see a sample link.

        ![Create a project. Input example external](../_images/tutorials/questionnaire/survey-input-example-external.png =700x)

        It is only an example used to display the task interface preview on the right. You will add a link to your survey later while uploading a task file.

    1. Click **Data specification → Show specifications**. In the following sections, you will see the parameters which match the task interface you set up in **Template Builder**:

        - **Input data**: A parameter for a link to your survey.

        - **Output data**: Parameters for completion codes entered by Tolokers and for their comments if they have problems with getting a code.

        {% note info %}

        You can also display a survey form in an [iframe](https://ya.cc/t/kZoRrfTk3ttAFF) if a third-party platform allows it. To learn more about the `view.iframe` component, see the [Template Builder Help](../../template-builder/reference/view.iframe.md).

        {% endnote %}

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

    {% note info %}

    Do not add a link to your external survey form to the instructions. Specify the link only in the file with tasks. See the [section below](#upload) to learn how you can do that.

    {% endnote %}

1. {% include [save-project](../_includes/tutorials/save-project.md) %}

## Create a pool {#pool}

{% include [toloka-requester-source-what-is-pool](../_includes/toloka-requester-source/id-toloka-requester-source/what-is-pool.md) %}

You can create a pool using one of the ways:

- From a preset — a new pool with settings for survey:

    - Load one static link to the survey. To learn more, see the [Upload data](#upload) section.

    - Don't add correct completion codes to the file with tasks.

    - Indicate an [overlap](../../glossary.md#overlap) equal to the required number of Tolokers.

    - Use [manual review](../concepts/offline-accept.md).

    {% note info %}

    In this case, you need to adjust the overlap, the price of the survey, and the audience settings (including the skill by which the platform will exclude the Tolokers who have already completed the survey once). To learn more about pool settings, see the section below about creating a pool from scratch.

    {% endnote %}

- From scratch — a new pool with default settings.

{% list tabs %}

- Create a pool from the preset

  1. If there are no pools in the project, click **Create pool from preset for Survey on third-party platform** on the **Pools** tab. Otherwise, click **Add a pool → From Survey on third-party platform preset** at the right side of the project page.

  1. {% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

  1. {% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

  1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

  1. Clear **My tasks may contain shocking or pornographic content** if your project has none of those.

  1. At the **Setup quality control** step, check the quality control rules and correct them if necessary.

  1. {% include [tutorials-time-per-task-suite](../_includes/tutorials/time-per-task-suite.md) %}

  1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

      {% include [toloka-requester-source-set-price](../_includes/toloka-requester-source/id-toloka-requester-source/set-price.md) %}

  1. [Upload](#upload) your task data.

  1. {% include [tutorials-double-check](../_includes/tutorials/double-check.md) %}

      {% include [toloka-requester-source-step-enabled](../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

  {% include [toloka-requester-source-pool-is-ready](../_includes/toloka-requester-source/id-toloka-requester-source/pool-is-ready.md) %}

- Create a pool from scratch

  1. If there are no pools in the project, click **Create new pool from scratch** on the **Pools** tab. Otherwise, click **Add a pool → From scratch** at the right side of the project page.

  1. {% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

  1. {% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

  1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

      1. Clear **My tasks may contain shocking or pornographic content** if your project has none of those.

      1. Select Tolokers who knows the language of your survey:

          ![Create a pool. Languages filter](../_images/tutorials/questionnaire/survey-language-filter.png =700x)

          Additionally, you can select Tolokers based on their location, age, gender, and other parameters. Use the **Add filter** button and configure the filters you need.

      1. Tasks in pools will automatically be available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the **Client** filter and select the desired value: **Toloka web version** or **Toloka for mobile**.

      1. Filter out Tolokers who have already taken one survey. It helps prevent the situation when a Toloker completes your survey several times.

          1. Click the **Add skill** button. Enter the skill name and description, and leave the skill not public.

              ![Create a pool. Add skill](../_images/tutorials/questionnaire/survey-skill-add.png =405x)

          1. Click **Add filter → My skills** and select your skill from the previous step. Configure the filter to recruit Tolokers without the skill.

              ![Create a pool. My skills](../_images/tutorials/questionnaire/survey-skill-filter.png =700x)

          You will add a rule that assigns this skill to Tolokers who have already taken one survey later.

  1. {% include [tutorials-quality-control](../_includes/tutorials/quality-control.md) %}

      1. Click the **Review task responses manually** toggle, and specify the number of days for checking the task in the **Review period in days** field (for example, 7).

          {% include [tutorials-na-acceptance](../_includes/tutorials/na-acceptance.md) %}

      1. To filter out Tolokers who complete tasks too fast, edit the pre-configured **Fast responses** rule. Specify the following values:

          ![Create a pool. Fast responses rule](../_images/tutorials/questionnaire/survey-fast-responses.png =700x)

          These settings mean that a Toloker who completes a task suite in less than 15 seconds will be blocked and won’t be able to access your tasks anymore.

          A task suite is a page with a number of tasks. In survey projects, a task suite must contain only one task (one survey).

          {% note tip %}

          To determine the **Minimum time per task suite** value, complete your survey and record the time.

          {% endnote %}

      1. Delete the pre-configured **Majority vote** rule.

      1. To get the required number of responses, add the **Processing rejected and accepted assignments** rule. Enter the following values:

          ![Create a pool. Processing rejected and accepted assignments rule](../_images/tutorials/questionnaire/survey-rejected.png =700x)

          This means that if you reject a Toloker’s response during the review, a new survey task will be sent to another Toloker.

      1. Add the rule which assigns a skill after one submitted survey. As you’ve set the filter to select Tolokers without this skill in step 3.4, the rule allows you to filter out Tolokers who have already completed your survey.

          ![Create a pool. Submitted responses rule](../_images/tutorials/questionnaire/survey-accomplished.png =700x)

      1. To automatically accept tasks from those who entered a completion code correctly, use the **Control tasks** rule:

          ![Create a pool. Control tasks rule](../_images/tutorials/questionnaire/survey-control-rule.png =700x)

          The rule will work if you specify the correct completion code in the file with tasks. You will do that later in this tutorial.

  1. {% include [tutorials-time-per-task-suite](../_includes/tutorials/time-per-task-suite.md) %}

      {% note warning %}

      Time per task suite should be long enough to read the instructions, wait for the task data to load, give the answers on the third-party website, and copy and paste the completion code. Otherwise, Tolokers won’t be able to submit your tasks.

      {% endnote %}

  1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

      {% include [toloka-requester-source-set-price](../_includes/toloka-requester-source/id-toloka-requester-source/set-price.md) %}

  1. [Upload](#upload) your task data.

  1. {% include [tutorials-double-check](../_includes/tutorials/double-check.md) %}

      {% include [toloka-requester-source-step-enabled](../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

  {% include [toloka-requester-source-pool-is-ready](../_includes/toloka-requester-source/id-toloka-requester-source/pool-is-ready.md) %}

{% endlist %}

## Upload data {#upload}

1. Go to the **Prepare and upload data** step if you're creating a pool or click the **Upload** button on the pool page.

1. Create the tasks for Tolokers:

    1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

    1. Open the downloaded file. It must have one parameter which name equals `INPUT:survey_link`, and the values are links.

        1. Replace the sample links with your data. You can:

            - Specify one static link to your survey.

                In this case, the overlap you’ve set in step 6.2 of [creating the pool](#pool) should be equal to the number of respondents you need.

            - Provide many survey links to give each of them to one Toloker.

                In this case, the number of links in the file should be equal to the number of respondents you need. The overlap should be set to 1.

                You can use different survey links if it’s necessary to generate different codes for each Toloker. It’s also possible to specify the same link many times.

                {% note info %}

                - Different completion codes for each Toloker help minimize the risk of fraud.

                - If you provide many survey links, make sure that you’ve configured the **Submitted responses** rule and the **Time per task suite, sec** value is enough (see steps 4.5 and 5 of [creating the pool](#pool)).

                {% endnote %}

                For example, the XLSX file should look as follows:

                {% list tabs %}

                - One link (overlap > 1)

                  ```plaintext
                  INPUT:url
                  https://survey.com/mysurvey
                  ```

                - Many links (overlap = 1)

                  ```plaintext
                  INPUT:url
                  https://survey.com/mysurvey/OIN7YV2TP
                  https://survey.com/mysurvey/YUT9IJ3PL
                  https://survey.com/mysurvey/RDV3TG8OJ
                  ```

                {% endlist %}

        1. If you know the correct completion codes beforehand, add the `GOLDEN:code` parameter to the file and specify its values:

            {% list tabs %}

            - One link (overlap > 1)

              ```plaintext
              INPUT:url GOLDEN:code
              https://survey.com/mysurvey 123456
              ```

            - Many links (overlap = 1)

              ```plaintext
              INPUT:url GOLDEN:code
              https://survey.com/mysurvey/OIN7YV2TP 123456
              https://survey.com/mysurvey/YUT9IJ3PL 234567
              https://survey.com/mysurvey/RDV3TG8OJ 345678
              ```

            {% endlist %}

            In this case, you can automatically accept tasks from those who entered a completion code correctly. Use the **Control tasks** rule from step 4.6 of [creating the pool](#pool).

    1. Click **Drop file here or select**, and upload the file you’ve just made.

    1. Click **Continue**.

    1. Tasks are shown to Tolokers in suites. A suite is a single page with multiple tasks.

        Go to the **Set manually** tab. Set one task per suite, that is a Toloker will see only one task with your survey on the page:

        ![Upload data. Tasks per suite](../_images/tutorials/questionnaire/survey-number-tasks.png =570x)

    1. Click **Combine tasks into suites**.

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. Go to the pool page and click the **Preview** button to check your task.

    1. Follow the link to your survey to make sure that it works.

    1. Enter the code and submit the task.

    If the page reloaded successfully, your task works correctly.

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    ![Start labeling](../_images/tutorials/questionnaire/survey-start-labeling.png =700x)

1. In the pop-up panel, review the budget and click **Launch**.

## See the results {#results}

Track the progress of responses collection on the pool page. You can start the review when the first results are received.

If you’ve set the **Control tasks** rule in step 4.6 of [creating the pool](#pool), most of the tasks may be already accepted.

Review the rest of the tasks during the time period specified in the **Review period in days** field in step 4.1. After that period, all responses are automatically accepted, regardless of whether completion codes are correct or not.

1. Go to the pool, and click **Review assignments**.

    ![See the results. Review assignments](../_images/tutorials/questionnaire/survey-review-results.png =700x)

1. Choose an assignment.

1. Check the completion code, and click **Accept** or **Decline**. For rejected responses, enter a comment to specify the reason.

    To learn about other ways of review, see the [Reviewing Tolokers’ responses](../concepts/accept.md) section.

    {% note info %}

    - Do not rush to reject responses that have not passed automatic completion via codes. Some codes will be incorrect indeed, but often Tolokers add extra spaces accidentally or leave comments in a text field which is intended for a code.

    - If there were technical problems (for example, a Toloker had filled an external survey form, but didn’t have time to submit a task in Toloka), you still can pay the Toloker. To do this, use the [bonus system](../concepts/bonus.md).

    {% endnote %}

## Helpful tips {#tips}

- You can use questions with known answers to check that Tolokers pay attention. In that case, even if a Toloker answers incorrectly, it’s better to still provide them a special completion code, different from the correct one. When you see that special code in the results, you can reject the assignment. The Toloker won’t be dissatisfied that you didn't allow them to finish the task.

- You can conduct a survey in two stages. For example, it can be useful when the general filters of the **Audience** section are not enough to select Tolokers you need. Use skills:

    - In the first survey, [assign the skill](../concepts/nav-assign.md) to the relevant Tolokers.

    - In the second survey, specify the skill in the **Audience** section to make the survey available to the relevant Tolokers from the first stage.

    You can notify Tolokers about the second survey using [messages](../concepts/messaging.md) to those of them who have the necessary skill.

- Sometimes a survey may follow different scenarios depending on answers given to the previous questions. In this case, make sure that all scenarios have a completion code in the end.

- Check the **Messages** tab regularly to get Tolokers’ reports on problems with your survey.

## See also {#see-also}

- [Crowdsourcing concepts: Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Crowdsourcing concepts: Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Template Builder: Survey](../../template-builder/templates/survey.md)

## For developers {#for-developers}

- [Toloka-Kit: Survey](https://github.com/Toloka/toloka-kit/blob/main/examples/7.survey/simplest_survey/simplest_survey.ipynb)

## Datasets and reference {#datasets}

- [Sample dataset file with tasks](https://labs-images-testing.s3.yandex.net/presets/sidepanel/29_surveyThirdPartyPlatform/EN/sample-files.zip)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}