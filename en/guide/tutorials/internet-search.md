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

- Make sure you are [registered](../concepts/access.md) in Toloka as a requester.
- [Top up](../concepts/refill.md) your Toloka account. If you are unsure about the budget, you can do that later in this tutorial. Toloka will display the budget estimate for your project.

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}


1. Follow [this link]({{ internet-search-preset }}), or create a project manually:
    1. In the main menu, choose the {% if locale == "en-com" %}**Projects**{% endif %} tab, and click {% if locale == "en-com" %}**Create a project**{% endif %}.
    1. Select the {% if locale == "en-com" %}**Mining business contacts**{% endif %} preset.

1. Click {% if locale == "en-com" %}**Choose solution**{% endif %} in the pop-up tab.

## Create a project {#project}

{% include [toloka-requester-source-who-are-tolokers](../_includes/toloka-requester-source/id-toloka-requester-source/who-are-tolokers.md) %}


1. {% include [toloka-requester-source-add-name-description](../_includes/toloka-requester-source/id-toloka-requester-source/add-name-description.md) %}

    - {% if locale == "en-com" %}**Name to show performers**{% endif %}: In 2–5 words, state the general idea of the project.
    - {% if locale == "en-com" %}**Description for performers**{% endif %}: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

1. In the {% if locale == "en-com" %}**Task interface**{% endif %} section, set up what your tasks will look like.
    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. In the {% if locale == "en-com" %}**Config**{% endif %} section, you can edit the code to change the appearance and layout of the task elements. For example, to configure the field label which specifies the object Tolokers should find information about, replace the sample text with your value in the `label` property.
    1. To configure the sources where Tolokers should search for information, edit the `view.link-group` component.
    - The first `url` component contains the `"path": "site"` property. The `site` is a parameter for a link where Tolokers should seek information. You will specify the list of these links in the file with tasks later in this tutorial.
    - The second and third `url` components contain the links to the search queries. You can change the [search engines](https://toloka.ai/en/docs/template-builder/reference/helper.search-query) Tolokers will use in your tasks.

    {% note info %}

    To learn about other properties of the {% if locale == "en-com" %}**Config**{% endif %} section, their possible values and the impact on the task interface, see the [Template Builder Help](https://toloka.ai/en/docs/template-builder/templates/data-search).

    {% endnote %}

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

    1. Use the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.
    1. Click the {% if locale == "en-com" %}**Add skill**{% endif %} button. Enter the skill name and description, and leave the skill not public.
    1. Click {% if locale == "en-com" %}{% endif %} and select your skill from the previous step. Configure the filter to recruit Tolokers without the skill or those whose skill value is 65 and higher.
    Later in this tutorial, you will add a rule that assigns this skill to Tolokers according to how accurate their responses are.

1. Under {% if locale == "en-com" %}**Quality control**{% endif %}, set quality control rules for more accurate results.
    1. To filter out Tolokers who complete tasks too fast, edit the pre-configured {% if locale == "en-com" %}**Fast responses**{% endif %} rule. Specify the following values:
    These settings mean that a Toloker who completes a task suite in less than 10 seconds will be suspended and won't be able to access tasks of the project for 1 day.

    A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 4–6 tasks per suite.

    1. Delete the pre-configured {% if locale == "en-com" %}**Majority vote**{% endif %} rule.
    1. Click {% if locale == "en-com" %}{% endif %}, and enter the following values:
    This means that a Toloker who gives 3 or more responses to the control tasks will be assigned the skill you’ve created before. The skill value is equal to the percent of correct responses. As you’ve set the filter to select Tolokers whose skill value is 65 or more in step 3.5, the rule allows you to filter out Tolokers who have shown poor results.

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In {% if locale == "en-com" %}**Price per task suite**{% endif %}, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks. It can contain one or several tasks.
    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

    The default value (`3`) means that each task will have 3 responses.

1. Click {% if locale == "en-com" %}**Show advanced settings**{% endif %}. In {% if locale == "en-com" %}**Additional settings**{% endif %}, specify the {% if locale == "en-com" %}**Time per task suite, sec**{% endif %}.

    This time should be enough to read the instructions, load the task, search information online, and respond (for example, 600 seconds).

1. To save the settings and continue, click {% if locale == "en-com" %}**Create pool**{% endif %}.

## Upload data {#upload}

At this step, upload your task data to Toloka.

1. Click {% if locale == "en-com" %}**Upload data**{% endif %}.
1. Create the tasks for Tolokers:
    1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

    For this type of project, the file with tasks must have two parameters:

    - `INPUT:name`: The names of the objects you ask Tolokers to find information about.
    - `INPUT:site`: The links where you ask Tolokers to search data.

    ```json
    INPUT:name	INPUT:site
    Restauracja Basniowa	https://basniowa.rybnik.pl/
    Ristorante Pizzeria Zia Caterina	https://www.ristorantepizzeriaziacaterina.it/
    De Vijf Sinnen	http://www.devijfsinnen.nl/
    ```

    1. Open the downloaded file, and replace the sample data with your information.
    1. Click {% if locale == "en-com" %}**Drop file here or select**{% endif %}, and upload the file you’ve just made.
    1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

    - {% if locale == "en-com" %}**General tasks**{% endif %}: These are tasks for Tolokers to label.
    - {% if locale == "en-com" %}**Control tasks**{% endif %}: These are tasks with predefined answers used to control the quality of responses. You will create them in the next step.
    - {% if locale == "en-com" %}**Training tasks**{% endif %}: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

    For example, you can add 2 general tasks and 1 control task per suite:

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.
1. {% include [toloka-requester-source-add-control-tasks](../_includes/toloka-requester-source/id-toloka-requester-source/add-control-tasks.md) %}

    1. Click {% if locale == "en-com" %}**Edit**{% endif %}.
    1. {% include [toloka-requester-source-create-control-button](../_includes/toloka-requester-source/id-toloka-requester-source/create-control-button.md) %}

    1. Select the {% if locale == "en-com" %}**email**{% endif %} and {% if locale == "en-com" %}**phone**{% endif %} checkboxes, and enter the correct answer for a task. Then, click the {% if locale == "en-com" %}**Save and go to next**{% endif %} button. Add several control tasks this way.
    {% include [toloka-requester-source-control-percent](../_includes/toloka-requester-source/id-toloka-requester-source/control-percent.md) %}

    1. When you are done adding control tasks, click the pool name in the menu.


## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).
1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

1. In the pop-up panel, review the budget and click {% if locale == "en-com" %}**Launch**{% endif %}.

## See the results {#results}

1. {% include [toloka-requester-source-labeling-progress](../_includes/toloka-requester-source/id-toloka-requester-source/labeling-progress.md) %}

1. Click the arrow next to the {% if locale == "en-com" %}**Download results**{% endif %} button and choose {% if locale == "en-com" %}**Run Dawid-Skene model**{% endif %} from the drop-down menu. Click {% if locale == "en-com" %}**Yes**{% endif %} in the pop-up window.
1. Open the same drop-down menu again, and click {% if locale == "en-com" %}**View aggregations list**{% endif %}.
1. Wait until the aggregation is complete, and click {% if locale == "en-com" %}**Download**{% endif %}. You will get the TSV file with the labeling results:
    - {% if locale == "en-com" %}**INPUT**{% endif %}: The data you uploaded for labeling.
    - {% if locale == "en-com" %}**OUTPUT**{% endif %}: The results of labeling (information found by Tolokers).
    - {% if locale == "en-com" %}**CONFIDENCE**{% endif %}: The response significance according to the [Dawid-Skene model](../concepts/result-aggregation.md#dawid-skene).



## See also {#seealso}

- [Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Template Builder — search for information online](https://toloka.ai/en/docs/template-builder/templates/data-search)
- [Toloka-Kit — search relevance](https://github.com/Toloka/toloka-kit/blob/main/examples/8.search_relevance/search_relevance.ipynb)


## Datasets and reference {#datasets}

- [Sample dataset files with tasks](https://labs-images-testing.s3.yandex.net/presets/sidepanel/19_search/EN/sample-files.zip)
