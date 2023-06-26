# Searching for product characteristics

In this tutorial, you will learn how to run searching for product characteristics in Toloka. We will use a project preset designed specifically for this type of data labeling.

Searching for product characteristics is a type of data labeling task with a text specifying what is required to find, and an input area for collected information.

Tolokers read what and where they should find, search for the required data, and enter it to the task interface.

Use this preset for the following purposes:

- Searching for an item, such as a product or service, by its description.

- Searching for information on a specific website, such as cities where products can be delivered on a store's website.

- Searching for information about an item online, such as a company's contact information.

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

## Create a project {#project}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ internet-search-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Click **Do it myself**.

    1. Select the **Mining business contacts** preset.

1. Click **Choose this preset** in the pop-up tab.

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - **Name to show Tolokers**: In 2–5 words, state the general idea of the project.

    - **Description for Tolokers**: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    ![Create a project. Step 1](../_images/tutorials/internet-search/internet-search-create-project-step-1.png =700x)

1. In the **Task interface** section, set up what your tasks will look like.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. In the **Config** section, you can edit the code to change the appearance and layout of the task elements. For example, to configure the field label which specifies the object Tolokers should find information about, replace the sample text with your value in the `label` property.

        ![Create a project. Config text](../_images/tutorials/internet-search/internet-search-config-text.png =700x)

    1. To configure the sources where Tolokers should search for information, edit the `view.link-group` component.

        - The first `url` component contains the `"path": "site"` property. The `site` is a parameter for a link where Tolokers should seek information. You will specify the list of these links in the file with tasks later in this tutorial.

        - The second and third `url` components contain the links to the search queries. You can change the [search engines](../../template-builder/reference/helper.search-query.md) Tolokers will use in your tasks.

            ![Create a project. Config links](../_images/tutorials/internet-search/internet-search-config-links.png =700x)

            {% note info %}

            To learn about other properties of the **Config** section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/templates/data-search.md).

            {% endnote %}

    1. {% include [toloka-requester-source-specification-definition](../_includes/toloka-requester-source/id-toloka-requester-source/specification-definition.md) %}

        {% include [toloka-requester-source-click-show-specifications](../_includes/toloka-requester-source/id-toloka-requester-source/click-show-specifications.md) %}

        - **Input data**: Parameters in the file with raw task data.

        - **Output data**: Parameters in the file with labeling results.

        {% include [toloka-requester-source-specification-match](../_includes/toloka-requester-source/id-toloka-requester-source/specification-match.md) %}

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

    {% include [toloka-requester-source-instruction-note](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-note.md) %}

1. {% include [save-project](../_includes/tutorials/save-project.md) %}

## Create a pool {#pool}

{% include [toloka-requester-source-what-is-pool](../_includes/toloka-requester-source/id-toloka-requester-source/what-is-pool.md) %}

1. Click **Create new pool** on the project page.

1. {% include [toloka-requester-pool-type](../_includes/toloka-requester-source/id-toloka-requester-source/pool-type.md) %}

1. {% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

1. {% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

1. Click **Create**.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. Clear **My tasks may contain shocking or pornographic content** if your project has none of those.

    1. {% include [toloka-requester-source-filters](../_includes/toloka-requester-source/id-toloka-requester-source/filters.md) %}

        ![Create a pool. Languages filter](../_images/tutorials/internet-search/internet-search-language-filter.png =700x)

    1. Use the **Speed/quality balance** slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

    1. Click the **Add skill** button. Enter the skill name and description, and leave the skill not public.

        ![Create a pool. Add skill](../_images/tutorials/internet-search/internet-search-skill-add.png =458x)

    1. Click **Add filter → My skills** and select your skill from the previous step. Configure the filter to recruit Tolokers without the skill or those whose skill value is 65 and higher.

        ![Create a pool. My skills filter](../_images/tutorials/internet-search/internet-search-skill-filter.png =700x)

        Later in this tutorial, you will add a rule that assigns this skill to Tolokers according to how accurate their responses are.

1. {% include [tutorials-quality-control](../_includes/tutorials/quality-control.md) %}

    1. To filter out Tolokers who complete tasks too fast, edit the pre-configured **Fast responses** rule. Specify the following values:

        ![Create a pool. Fast responses rule](../_images/tutorials/internet-search/internet-search-fast-responses.png =700x)

        These settings mean that a Toloker who completes a task suite in less than 10 seconds will be suspended and won't be able to access tasks of the project for 1 day.

        A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 4–6 tasks per suite.

    1. Delete the pre-configured **Majority vote** rule.

    1. Click **Add a quality control rule → Control tasks**, and enter the following values:

        ![Create a pool. Control tasks rule](../_images/tutorials/internet-search/internet-search-control-rule.png =700x)

        This means that a Toloker who gives 3 or more responses to the control tasks will be assigned the skill you’ve created before. The skill value is equal to the percent of correct responses. As you’ve set the filter to select Tolokers whose skill value is 65 or more in step 3.5, the rule allows you to filter out Tolokers who have shown poor results.

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In **Price per task suite, $**, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks. It can contain one or several tasks.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        The default value (`3`) means that each task will have 3 responses.

1. {% include [tutorials-time-per-task-suite](../_includes/tutorials/time-per-task-suite.md) %}

    This time should be enough to read the instructions, load the task, search information online, and respond (for example, 600 seconds).

1. {% include [tutorials-upload-tasks](../_includes/tutorials/upload-tasks.md) %}

    1. Create the tasks for Tolokers:

        1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

            For this type of project, the file with tasks must have two parameters:

            - `INPUT:name`: The names of the objects you ask Tolokers to find information about.

            - `INPUT:site`: The links where you ask Tolokers to search data.

            ```plaintext
            INPUT:name	INPUT:site
            Restauracja Basniowa	https://basniowa.rybnik.pl/
            Ristorante Pizzeria Zia Caterina	https://www.ristorantepizzeriaziacaterina.it/
            De Vijf Sinnen	http://www.devijfsinnen.nl/
            ```

        1. Open the downloaded file, and replace the sample data with your information.

        1. Click **Drop file here or select**, and upload the file you’ve just made.

        1. Click **Continue**.

    1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

        - **General tasks**: These are tasks for Tolokers to label.

        - **Control tasks**: These are tasks with predefined answers used to control the quality of responses. You will create them in the next step.

        - **Training tasks**: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

            For example, you can add 2 general tasks and 1 control task per suite:

            ![Upload data. Tasks per suite](../_images/tutorials/internet-search/internet-search-upload-data.png =700x)

    1. Click **Combine tasks into suites**.

1. {% include [toloka-requester-source-add-control-tasks](../_includes/toloka-requester-source/id-toloka-requester-source/add-control-tasks.md) %}

    1. Select the **email** and **phone** checkboxes, and enter the correct answer for a task. Then, click the **Save and go to next** button. Add several control tasks this way.

        {% include [toloka-requester-source-control-percent](../_includes/toloka-requester-source/id-toloka-requester-source/control-percent.md) %}

1. {% include [tutorials-double-check](../_includes/tutorials/double-check.md) %}

    {% include [toloka-requester-source-step-enabled](../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

{% include [toloka-requester-source-pool-is-ready](../_includes/toloka-requester-source/id-toloka-requester-source/pool-is-ready.md) %}

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    ![Start labeling](../_images/tutorials/internet-search/internet-search-start-labeling-step-2.png =700x)

1. In the pop-up panel, review the budget and click **Launch**.

## See the results {#results}

1. {% include [toloka-requester-source-labeling-progress](../_includes/toloka-requester-source/id-toloka-requester-source/labeling-progress.md) %}

    ![See the results. Step 1](../_images/tutorials/internet-search/internet-search-see-results-step-1.png =700x)

1. Click the arrow next to the **Download results** button and choose **Run Dawid-Skene model** from the drop-down menu. Click **Yes** in the pop-up window.

    ![See the results. Step 2](../_images/tutorials/internet-search/internet-search-see-results-step-2.png =700x)

1. Open the same drop-down menu again, and click **View aggregations list**.

1. Wait until the aggregation is complete, and click **Download**. You will get the TSV file with the labeling results:

    - **INPUT**: The data you uploaded for labeling.

    - **OUTPUT**: The results of labeling (information found by Tolokers).

    - **CONFIDENCE**: The response significance according to the [Dawid-Skene model](../concepts/result-aggregation.md#dawid-skene).

## See also {#see-also}

- [Crowdsourcing concepts: Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Crowdsourcing concepts: Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Template Builder: Search for information online](../../template-builder/templates/data-search.md)

## For developers {#for-developers}

- [Toloka-Kit: Search relevance](https://github.com/Toloka/toloka-kit/blob/main/examples/8.search_relevance/search_relevance.ipynb)

## Datasets and reference {#datasets}

- [Sample dataset files with tasks](https://labs-images-testing.s3.yandex.net/presets/sidepanel/19_search/EN/sample-files.zip)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}