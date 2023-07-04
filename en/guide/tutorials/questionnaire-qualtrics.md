# Survey based on Qualtrics

In this tutorial, you will learn how to use Toloka to run an academic Qualtrics-based survey.

Choose this solution if you have a Qualtrics survey approved by an institutional review board (IRB), and you don't want to spend time on getting onboard with the standard Toloka projects. In this type of project, Toloka sets up your project and accepts responses automatically.

A task in Toloka provides a link to your Qualtrics survey. A Toloker takes the task and follows the link to start the survey on Qualtrics. At the end of the survey, they get a confirmation code (you will learn how to embed the code to your survey later in this tutorial). Then the Toloker confirms completing the survey by entering the code into the Toloka task. The Tolokers who provided the valid completion codes are paid.

Tasks are rejected, accepted and paid automatically in Toloka. Survey responses are gathered and stored on Quatrics.

{% note info %}

To learn about other Toloka solutions for surveys, see the tutorials:

- How to run a survey using other external platforms — [Survey on third-party platform](questionnaire-other.md).

- How to create a survey form in Toloka instead of using a third-party platform — [Survey with Toloka template](questionnaire-toloka.md).

The comparison of all the three kinds of the survey presets is provided in the [Overview](questionnaire-overview.md) section.

{% endnote %}

## Prerequisites {#prerequisites}

Before you begin:

- Clone your Qualtrics survey first. We recommend copying the survey to keep its initial version.

  Then prepare the link to the cloned survey, and the IRB approval number.

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

- See the [What tasks can't be placed in Toloka?](../concepts/unwanted.md#requirements-for-survey) section.

   Remember that both Tolokers and requesters are anonymous. You should not collect personal data: a full name, contacts, or any other information that can be used to identify a Toloker. To determine whether a Toloker belongs to your target audience, you can ask for their city, date of birth, and age category.

{% note alert "Restriction" %}

For now, all surveys conducted using this type of project must be in English and will be offered to Tolokers with verified English language skills.

{% endnote %}

## Create a project {#project}

1. Pick a preset depending on your survey length:

    * For short surveys that take 15 minutes or less — [Short survey]({{ survey-qualtrics-short }}).

    * For medium surveys that take 15–30 minutes — [Medium survey]({{ survey-qualtrics-medium }}).

    * For long surveys that take 30–60 minutes — [Long survey]({{ survey-qualtrics-long }}).

    Another way to choose a preset is to do the following:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        ![Create project button](../_images/tutorials/survey-qualtrics/qualtrics-survey-create-project.png =700x)

    1. In the left menu, click **Social science research**. Select the **Short survey**, **Medium survey**, or **Long survey** preset.

        ![Social science research](../_images/tutorials/survey-qualtrics/qualtrics-survey-social-science.png =700x)

1. Click **Choose solution** in the pop-up tab.

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    * **Project name visible to Tolokers**: In 2–5 words, state the idea of the project.

    * **Link to your Qualtrics survey**: Add the link to your Qualtrics-based survey.

    * **Project description for Tolokers**: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. Tolokers will find the detailed instructions after they start the survey.

    ![Qualtrics survey description](../_images/tutorials/survey-qualtrics/qualtrics-survey-description.png =700x)

    Note that the task interface and detailed instructions are preconfigured: they are standard for all the Qualtrics survey projects.

    {% cut "How your task will look for Tolokers" %}

    ![Social science research](../_images/tutorials/survey-qualtrics/qualtrics-survey-task-interface.png =400x)

    {% endcut %}

1. Set up the filters to select Tolokers for your survey.

    * **Total number of Tolokers**: Add the required number of respondents.

    * **Countries of residence** (optional): Select the countries to sample from. If no selection is made, your survey will be available to Tolokers from 80 countries specified in the [Countries available in this release](https://toloka.ai/toloka-for-social-sciences/#table) list.

    * **Gender** (optional): Set the gender of Tolokers.

    * **Age** (optional): Enter the age of Tolokers between 18 and 90.

    ![Survey audience](../_images/tutorials/survey-qualtrics/qualtrics-survey-audience.png =700x)

    {% note info %}

    Toloka does not share any user data. If you need data on respondents' country, age, or gender, make sure you ask this in your survey.

    {% endnote %}

1. Add your academic credentials.

    * **Affiliation**: The name of the university.

    * **Institution email**: Your email on the university domain.

    * **IRB approval / exemption number**: The study number approved by the IRB.

    ![Survey approval](../_images/tutorials/survey-qualtrics/qualtrics-survey-approval.png =700x)

1. Revise the settings carefully. You will not be able to change them later.

1. To save your data and continue, click **Create**.

## Embed a completion code {#code}

Toloka controls the data collection completion by exchanging a unique code with Qualtrics. Embed the code to your survey.

1. Follow the step-by-step guide provided on the **Finish setup and launch survey** page.

1. After you embed the code to your survey, select **My Qualtrics survey has an embedded completion code from Toloka**.

    ![Embed code](../_images/tutorials/survey-qualtrics/qualtrics-survey-embed-code.png =700x)

1. Click **Launch survey**.

## Launch the survey and get the results {#launch}

In the pop-up tab, check the parameters and click **Launch**.

![Launch survey](../_images/tutorials/survey-qualtrics/qualtrics-survey-launch.png =700x)

Responses are stored on Quatrics. Go there to track the progress of data collection and get the results.

## Helpful tips {#tips}

- If you need additional quality control, add attention checks and forced responses directly in your Qualtrics survey.

- Check the **Messages** tab regularly to get Tolokers’ reports on problems with your survey.

## See also {#seealso}

- [Toloka for social sciences](https://toloka.ai/toloka-for-social-sciences/)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}