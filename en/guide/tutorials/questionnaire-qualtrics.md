{% include [image-styles](../../../_includes/image-styles.md) %}

# Survey based on Qualtrics

In this tutorial, you will learn how to use Toloka to run an academic Qualtrics-based survey. 

Pick this solution, when:

* You have an IRB-approved Qualtrics survey.
* You do not want to spend time on getting onboard with the standard Toloka projects.

In Toloka, you can place a link to your Qualtrics-based survey. Each Toloker gets an automatically generated code which uniqueness is guaranteed by the [setup instruction](questionnaire-qualtrics.md#embed-a-code-code). After Tolokers enter the code, their responses are accepted or rejected automatically. 

{% note info %}

To learn about types of Qualtrics-based surveys, see [Choose a preset](questionnaire-qualtrics.md#choose-a-preset-preset).

To learn how to run a survey using other external platforms, see the [Survey on third-party platform](questionnaire-other.md) tutorial.

To learn how to create a survey form in Toloka, see the [Survey with Toloka template](questionnaire-toloka.md) tutorial.


{% endnote %}

## Prerequisites {#prerequisites}

Before you begin:

- create a survey on Qualtrics and get its approval by your institution's IRB.

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

- See the [What tasks can't be placed in Toloka?](../concepts/unwanted.md#requirements-for-survey) section. Remember that both Tolokers and requesters are anonymous.

    - You should not collect personal data: a full name, contacts, or any other information that can be used to identify a Toloker. To determine whether a Toloker belongs to your target audience, you can ask for their city, date of birth, and age category.

    - To communicate with Tolokers, use private messages in Toloka only.

## Choose a preset {#preset}

Pick a preset depending on your survey length:

* For short surveys that take 15 minutes or less — [Short survey](https://platform.toloka.ai/requester/templates?choosedCard=IuW9rwmVFAAB1ifPeFvJ&choosedTag=A3MdOlBKzWKcrpxg3JNQ). 

* For medium surveys that take 15-30 minutes — [Medium survey](https://platform.toloka.ai/requester/templates?choosedCard=IuW9rwmVFAAB1ifPeFvF&choosedTag=A3MdOlBKzWKcrpxg3JNQ).

* For long surveys that take 30-60 minutes — [Long survey](https://platform.toloka.ai/requester/templates?choosedCard=IuW9rwmVFAAB1ifPeFvv&choosedTag=A3MdOlBKzWKcrpxg3JNQ).

You may pick one of the three solutions manually:
1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}
   {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}
1. Select **Social science research** in the left menu.
![Social science research](../_images/tutorials/survey-qualtrics/social-science-research-menu.png "Social science research" =700x)
1. Pick short, medium, or long survey preset.


## Create a project {#project}

Set up how your tasks will look for Tolokers. Tolokers are people around the world who get paid for completing your tasks.
1. Add your project name, a link to your Qualtrics survey, and your project description.

    * **Project name visible to Tolokers**: In 2-5 words, state the general idea of the project.

    * **Link to your Qualtrics survey**: Add a link to your survey created on Qualtrics.

    * **Project description for Tolokers**: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. Tolokers will find your detailed instructions after starting the survey.  
![Qualtrics survey description](../_images/tutorials/survey-qualtrics/qualtrics-survey-description.png "Survey description" =700x)
1. Add survey audience.
Toloka does not share any user data. If you need data on respondents' country, age, or gender, make sure you ask this in your survey.

    * **Total number of Tolokers**: Add the required number of the survey participants.

    * **Countries of residence**: Specify the countries to sample from. If no selection is made Tolokers from 80 countries will see your survey.

    * **Gender**: Specify the gender of Tolokers if needed.

    * **Age**: Specify the age of Tolokers between 18 and 90 if needed.
![Survey audience](../_images/tutorials/survey-qualtrics/qualtrics-survey-audience.png "Survey audience" =700x)
1. Add your academic credentials.

    * **Affiliation**: Add the name of the university.

    * **Institution email**: Add your work email.

    * **IRB approval / exemption number**: Add a number of study approved by the institutional review board.
![Academic credentials](../_images/tutorials/survey-qualtrics/qualtrics-survey-approval.png "Survey approval" =700x)

1. To save your data click **Create**.

## Embed a code {#code}

After your project is created, add a completion code to your survey:

1. Open your survey in Qualtrics.
1. Create **Embedded data**.
![Embedded data](../_images/tutorials/survey-qualtrics/embedded-data.png "Embedded data" =700x)
1. Create a new field in embedded data, name it **TolokaCode**.
![Toloka code](../_images/tutorials/survey-qualtrics/toloka-code.png "Toloka code" =700x)
1. Move embedded data to the very top of the survey flow.
![Move data](../_images/tutorials/survey-qualtrics/move-embedded-data.png "Move data" =700x)
1. Add a new block in the end of the survey so that a respondent would see it only after the survey is fully complete.
![Add block 1](../_images/tutorials/survey-qualtrics/add-new-block1.png "Add block 1" =700x)
![Add block 2](../_images/tutorials/survey-qualtrics/add-new-block2.png "Add block 2" =700x)
1. Add a new question with **Text / Graphic type** in the created block.
![Add question](../_images/tutorials/survey-qualtrics/add-question.png "Add question" =700x)
1. Paste a message with a code to the question. A code should be printed exactly like this: $e{ e://Field/TolokaCode ^ a - b }, where a and b –numbers which you got after creating a project in Toloka. Please just copy and paste this formula and insert your a and b.
![Code message](../_images/tutorials/survey-qualtrics/add-code.png "Code message" =700x)

## Launch the survey {#launch}

After creating a project and adding a completion code, you may launch the survey:
1. Click **Start survey**.
![Startsurvey](../_images/tutorials/survey-qualtrics/start-survey.png "Start survey" =700x)
1. Check the parameters in the sidebar menu and click **Checkout and launch**. 
![Checkout and launch](../_images/tutorials/survey-qualtrics/checkout-launch.png "Checkout and launch" =700x)

## See the results {#results}

Track the progress of responses collection on the pool page, or in Qualtrics. You can start the review when the first results are received.
1. Go to the pool, and click {% if locale == "en-com" %}**Review assignments**{% endif %}.

    [![See the results. Review assignments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-review-results.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/survey-review-results.png)
1. After checking all the assignments, сlick the {% if locale == "en-com" %}**Download results**{% endif %} button.

    [![See the results. Download results](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/questionnaire-download-results.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/questionnaire/questionnaire-download-results.png)
1. Click **Download results**

You will get the TSV file. To process the survey results, you can open the file in Excel and save it in the XLSX format.

## Helpful tips {#tips}

- You can use questions with known answers to check that Tolokers pay attention. In that case, even if a Toloker answers incorrectly, it’s better to still provide them a special completion code, different from the correct one. When you see that special code in the results, you can reject the assignment. The Toloker won’t be dissatisfied that you didn't allow them to finish the task.

- Sometimes a survey may follow different scenarios depending on answers given to the previous questions. In this case, make sure that all scenarios have a completion code in the end.

- Check the {% if locale == "en-com" %}**Messages**{% endif %} tab regularly to get Tolokers’ reports on problems with your survey.

## See also {#seealso}

- [Toloka for social sciences](https://toloka.ai/toloka-for-social-sciences/)