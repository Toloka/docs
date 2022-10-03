# Common mistakes made by requesters

Using crowdsourcing can be challenging. It's difficult to get it right when launching your first project. In this section, you will learn what mistakes requesters make most often and how to avoid or fix them.

Depending on the stage of using Toloka, requester mistakes can be related to: project design, task interface, uploading tasks, or setting up [quality control](../../glossary.md#quality-control-ru).


## Mistakes related to project architecture {#mistakes-architecture}

- No decomposition: the requester creates a large task without dividing it into projects and expects Tolokers to infer final conclusions.
- The project instructions are long and complicated.
- High entry threshold: at the beginning of the project, there is complex [training](../../glossary.md#training-pool-ru) and strict selection of Tolokers.

{% cut "Solutions" %}

#### Decompose tasks

- Vertical decomposition: divide tasks into several projects.
- Horizontal decomposition: use [non-automatic acceptance](../../glossary.md#left-off-acceptance-ru) with verification by other Tolokers.
- For greater efficiency, combine both methods.

    Example: in the first project, Tolokers identify the class of objects in an image, and in the second project, they select areas that have these objects. Other Tolokers check if their responses are correct.

    [Learn more](solution-architecture.md) about decomposition.


#### Improve instructions

- Write simple and short instructions for Tolokers — no longer than a single standard page.
- Ask Tolokers to do a simple task. Don't expect results to provide the final conclusions.

    Incorrect: "Does this image match the instructions?"

    Correct: "Are there people in this image?"


[Learn more](instruction.md) about how to write clear instructions.

{% endcut %}

## Errors related to the task interface {#interface-mistakes}

- The task doesn't work correctly: buttons are not clickable or images are not displayed.
- Inconvenient interface: too many questions or unnecessary elements, empty spaces, non-obvious task design, or instructions inside the interface.
- The Toloker's actions are not checked: users can submit incorrectly filled or empty output data fields for verification or they can submit a response with no video or audio in media content tasks.

{% cut "Solutions" %}

#### Check the tasks before launching your project

- Create tasks in the [Sandbox](../../glossary.md#sandbox-ru) and try to do them yourself.
- Launch the project for a limited audience of Tolokers and analyze their feedback.

#### Develop a user-friendly interface

{% note info %}

You can try creating a task interface in the [Template Builder]({{ tb-quickstart }}).

{% endnote %}


- Use preset project templates.
- Create tasks with a simple interface and use space efficiently. Remove optional and duplicate elements.
- Add [keyboard shortcuts](t-components/image-annotation.md#hotkeys). For example, you can assign them for playing or pausing a video.
- If you launch tasks that need to be performed in mobile apps, adapt the interface to them.
    [Learn more](mobile.md) about adapting tasks for mobile devices.


#### Configure checking the Toloker's actions and data format

- To do this, use [validation](incoming.md#manual-setting). For example, make sure that the Toloker started playing media content or played it to the end.
- Use regular expressions to make sure that the output data is in the correct format. For example, check the format of a link or phone number.
- Minimize user interaction with external resources.

    {% note warning %}

    There are [restrictions](unwanted.md) on tasks that link to external websites.

    {% endnote %}

    If you use links to external resources, make sure the Toloker followed them.

{% endcut %}

## Mistakes related to uploading tasks {#loading-tasks-mistakes}

- Incorrect format, encoding, or structure of the file with tasks.
- Too many tasks on a page, which reduces the quality of task completion.
- Incorrect distribution of [control tasks](../../glossary.md#control-task-ru).

{% cut "Solutions" %}

- Use the correct [file](../../glossary.md#tsv-file-definition-ru) format and UTF8 encoding.
- Use file templates. You can find them on the pool page.
- Place tasks so that it takes no more than 5 minutes, preferably 1-2 minutes, to complete a single task suite. You can usually place 20-40 simple tasks, 5-10 tasks of medium difficulty, or 1-2 complex tasks on a single page.
- Use [smart mixing](../../glossary.md#smart-mixing-ru). The algorithm will distribute training, control tasks, and general tasks across the page on its own.
- Check the tasks in the pool preview. Make sure they are displayed correctly and it doesn't take too long to complete a single task suite.

{% endcut %}

## Mistakes in quality control settings {#quality-control-mistakes}

- There are no Toloker filters and tasks are available even to users who can't complete them.
- [Quality control rules](../../glossary.md#quality-control-rules-ru) are not used, or they are configured incorrectly.

{% cut "Solutions" %}

#### Select Tolokers

Using [filters](../../glossary.md#filtering-ru), you can filter out Tolokers who are not fit for your tasks.

- Use targeting by language and region. Toloka users are located in different countries.
- Select users based on their profile data, device specifications, or skills.

[Learn more](filters.md) about filters.

#### Set quality control rules

- Consider what type of acceptance you'll use:
    For tasks with auto acceptance, the best quality control rules are captchas, control tasks, majority vote, fast responses, and recompletion of assignments from banned users.

    For tasks with non-automatic acceptance, the best methods are fast responses and review results.

    [Learn more](control.md) about quality control rules.

- Choose and combine the rules depending on the content of your project. See examples of how to choose quality control rules in the [tutorials for popular tasks](usecases.md).
- Specify the reason for [banning Tolokers](../../glossary.md#banned-worker-ru) (it is only visible to you) and the reason for rejecting tasks (the Tolokers will see it).

#### Set up quality control rules

- Avoid choosing mutually exclusive settings.

    Let's say a pool has an overlap of 3, and the **Majority vote** quality control rule says that 5 responses to a task should be considered the majority. With an overlap of 3, the number of responses required to estimate the majority vote will never be achieved.

- Check whether the rule works as you intended. To do this, run a small pool with sample data or practice in the [Sandbox](../../glossary.md#sandbox-ru).
- See examples of settings on the pages from the [list](control.md) of quality control rules.

{% endcut %}

## Examples of problems {#examples-of-errors}

### New users aren't joining the project

#### Reason
The project has a pool that can only be accessed through [training](train.md), but the training itself is closed.

{% cut "Solutions" %}

- If you disabled the training on purpose or you plan to open it periodically because you don't need a large flow of users, then everything is fine.
- When labeling has stopped for the project and you are no longer selecting users for the [exam pool](../../glossary.md#exam-ru), just close it.
- If you don't need regular labeling and you don't want users to go through training for no reason, close the pool that the training is associated with.
- If you didn't plan to close the training or didn't know that the training should be open, make the necessary changes to the project settings.

{% endcut %}

### Tolokers are leaving the project

#### Reasons

- Tasks don't match the [requirements](unwanted.md), and users refuse to complete them.

- Tasks are too complex.
- The instructions are complicated and confusing.
- The tasks are not displayed or are displayed incorrectly.

{% cut "Solutions" %}

- Reread the [Requester Agreement]({{ customeragreement }}) to make sure that your project meets the requirements.
- Decompose the task.
- Rewrite the instructions to make them clear and easy to understand.
- Try to complete your task in the pool preview, or even better, in the Sandbox. Make sure everything is working correctly.

{% endcut %}

See also:

- [Detailed video course for requesters]({{ videocourse-about-decomposition }}). Designed for those who want to use Toloka for creating projects and for those who want to become a Toloka partner.
- [Toloka blog]({{ toloka-blog-index }}). Read our blog for useful tutorials and information about new Toloka features.

{% include [contact-support](../_includes/contact-support-help.md) %}
