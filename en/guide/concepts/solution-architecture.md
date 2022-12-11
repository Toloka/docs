# Decomposition of the task

Before you start creating a [project](../../glossary.md#project), consider dividing it into several smaller projects. This is called _decomposition_.

For example, in the [Business information (example with decomposition)](data-collection.md) section, the task can be divided into four projects:

- [Project 1. Does the photo contain a particular item?](contain_item.md) — This is data preparation (filtering).

- [Project 2. Find a similar item in the online store](find_an_item_in_store.md) — This is the original task.

- [Project 3. Does the item found look similar to the original?](item_look_similar.md) — Checking the responses.

- [Project 4. Which of the found items is most similar to the original?](item_more_similar.md) — Choosing the best response.

![](../_images/other/main-1.svg)

## Benefits of decomposition {#concept_l2j_phn_nlb}

We recommend that you think through the architecture of a solution consisting of several projects in advance, since projects can be linked:

- The result from one project can be the [input](../../glossary.md#input-output-data) for another project.

- You can assign a skill to Tolokers in one project and filter Tolokers by this [skill](../../glossary.md#skill) in another project.

After you decompose your project:

- Tasks become easier and faster to perform.

- Tasks require fewer skills.

- It is easier to set up shortcuts in the [task interface](../../glossary.md#task-interface), which also speeds up the work of Tolokers.

- Task [instructions](../../glossary.md#instructions) will be shorter, clearer, and more Toloker-friendly.

- You can make tasks cheaper for the reasons above.

- The quality of results is higher and easier to control.

- It may be easier to design a few simple tasks than a single large task. You'll have less difficulty creating the interface and writing instructions.

## When should I use decomposition? {#concept_vd5_4zb_nlb}

Usually, you can make a separate project with tasks to prepare data and check Tolokers' responses. Sometimes you can also divide the main part of a task into several projects.

### Preparing data within a separate project {#concept_l4v_h4g_nlb}

- Do you have data to be used as the basis for completing your task?

    You can entrust the collection of data for analysis to Tolokers as part of a separate project.

- Do I need to filter my data?

    Let's say you want to create a task titled “Select road signs in an image”, but you aren't sure that all images contain road signs. Create a separate project with a task titled “Are there road signs in an image?” to filter out unnecessary images.

    A data filtering task is usually cheap and can help you save on the most important task and simplify the task instructions and interface.

### Reviewing responses in a separate project {#concept_vxt_h4g_nlb}

- You can set up a separate project where other Tolokers check responses in submitted assignments. For example, if you want to create a project titled “Find similar products”, enable [assignment review](../../glossary.md#assignment-review) in this project and create a separate project with the “Are these items similar?” task to review responses, reject incorrect responses, and avoid paying for them.

    {% note alert %}

    In the assignments review, specify the [review period](../../glossary.md#review-period) after which the tasks are accepted automatically. You need to make sure that this timeframe allows enough time to complete the project for checking responses and then reject tasks in the general task project.

    {% endnote %}

- If the responses cannot be combined automatically, you can set up a separate project where you ask Tolokers to choose the most appropriate response. An example is if the responses are images of similar items and you only need one image like that.

{% note tip %}

Assign a skill to Tolokers who completed tasks in the main project. For checking responses, you can assign the review task only to Tolokers who don't have this skill.

{% endnote %}

### Decomposing tasks {#concept_o3r_h4g_nlb}

The easier the task, the better the results. If your task contains more than one question, it may be worth dividing it into several projects. Here are some examples of when decomposition is necessary:

- If some questions in the task need additional filtering.

    For example, if you show a Toloker a photo of a cat and ask them to answer questions like “What color is the cat?” and “Is the cat asleep?”, it's better to divide this task into two projects. To answer the second question, you'll need an additional data filtering stage, since the cat's eyes should be visible in the photo.

- If different Toloker skills are required to answer different questions of the task.

    Let's say that, in addition to the questions from the previous step, you want to find out the cat's breed. To answer this question, you need Tolokers who have sufficient knowledge in this area.

- If a Toloker must provide a general answer based on multiple criteria.

    For example, the task is to review multiple parameters of an ad and decide which category of buyers will be interested in it. It's better to ask specific questions about the ad and make a decision based on combinations of answers yourself. This way the results will be more accurate.

Some tasks consist of several questions, but they don't need any decomposition. For example:

- Surveys: It's important that all questions are answered by the same Toloker.

- Field tasks: If you need to verify various data about the same organization, it doesn't make sense to ask one Toloker to check whether the organization is open and another one to take a look at its business hours on the door.

## Examples {#concept_fwm_xlg_nlb}

Examples where decomposition is used:

- [Business information (example with decomposition)](data-collection.md)
- [Object recognition and area selection (example with decomposition)](image-segmentation-overview.md)

## What's next {#what_next}

- [Create a new project](project.md) to post your task.

## Troubleshooting {#problem-solution}

{% cut "I have a complex task. How do I break it down to get high-quality results?" %}

If your task contains many objects of different types, you should break it down. For example, you can ask users to select numbers in the first project, doorways and windows in the second project, walls in the third project, and plumbing in the fourth project.

The simpler the task, the cheaper it is and the better the quality of the final result. Set the cost of labeling a single class of objects in photos at about $0.01.

[Use](../tutorials/selection.md) the **Object selection in an image** template. You can open this template in the editor and add a drop-down list for labeling the selected object. See how to do this in the editor [description](t-components/image-annotation.md#annotation) (**Dropdown list** tab).

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}