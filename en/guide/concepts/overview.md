# How does Toloka work?

Toloka offers a data labeling platform where you can collect any amount of human-labeled data for AI and ML development.

Data labeling in Toloka relies on crowdsourcing and technologies for crowd management. In this section, we explain how it works.

@[youtube](https://www.youtube.com/watch?v=7RgoTib83EI)

## What is crowdsourcing?

Crowdsourcing is the practice of obtaining information or services from a large dispersed group of people. These people perform micro tasks, and their collective work provides valuable input. For example, they can classify images into categories, and the resulting data can be used later to improve search relevance or recommendation systems.

![Task example](../_images/other/task-example.png =430x)

Usually, there are three parties involved in crowdsourcing: requesters, crowd contributors or annotators, and a platform that brings them together.

Requesters are individuals or companies that use the crowdsourcing platform to collect or label data.  For example, they might post tasks to moderate comments, transcribe audio recordings, find road signs on images, or collect photos of local businesses.

Annotators (in Toloka, we call them Tolokers) are people from around the world who get paid for completing these tasks. These people are usually referred to as “the crowd”, which is where the word crowdsourcing comes from.

Toloka provides an open platform where requesters and the crowd can interact.

## Toloka workflow

The data labeling workflow in Toloka looks like this:

![Toloka workflow](../_images/other/how-toloka-works.svg)

1. First, you register in Toloka as a requester.

1. Then you create a project for data labeling. The project involves a specific task, like classifying images by category.

1. In the project, you explain what you want Tolokers to do. You set up the task interface (in our example, you assign categories to buttons for labeling images), and write detailed instructions.

1. For every set of data you want to label (in our example, this might be a batch of photos with traffic signs), you create a task pool. A project can have any number of pools.

1. You upload your data to a pool and launch the labeling.

1. Tolokers access their own Toloka interface, pick the tasks they want to do, and get paid for completed tasks.

1. After Tolokers complete all the tasks in a pool, you download the labeled data. You can process the data using aggregation or verification, or use it as is

No matter what type of data you intend to collect as a requester, you always need to create three main entities: a [project](#project), a [pool](#pool), and [tasks](#task).

![Toloka three main entities](../_images/other/toloka-overview.svg)

## Project {#project}

A project in Toloka represents a specific data labeling goal. This could be to moderate comments, to classify images, to transcribe audio recordings, or something else.

All tasks in a project share the same interface and instructions for Tolokers. You can upload new sets of tasks whenever you need to.

To learn about projects and settings, see [Project](project.md).

## Pool {#pool}

A pool represents a set of data to label in a project. You can use the pool settings to select Tolokers, set the price for tasks, and add various quality control rules.

Having multiple pools in the same project is useful because you can reuse the same project settings when you need more data labeled, and tweak the settings for each pool as needed.

To learn about pools and their settings, see [Pool](pool-main.md).

## Task {#task}

A task is created for a single data unit that requires labeling, like a photo to classify, or a comment to review.

In Toloka, there are three types of tasks: general, training, and control tasks. General tasks are the tasks with the actual data you want to get labeled. Training tasks have predefined answers and hints for Tolokers, which help them learn how to do the task correctly. Control tasks have predefined answers, used to check whether Tolokers answer correctly. You need to create training tasks and control tasks using actual data so that they are relevant to your project.

You upload task data to Toloka in a file. Toloka currently supports XLSX, TSV, and JSON file formats for uploading task data.

To learn about tasks, supported task files, and their structure, see [Task](pool_csv.md).

## Task suite {#tasks-page}

A task suite is a group of several tasks given to a Toloker to submit all at once. For example, you can show four images on the same page.

To learn about task suites and how to use them, see [Task suite](distribute-tasks-by-pages.md).

## What does it look like for Tolokers? {#appearance}

Tolokers have their own version of the platform with a browser interface and a mobile app. They see a list of tasks they can choose from. Your tasks become available to Tolokers when you launch a pool.

Note that Tolokers don't know the difference between projects, pools, tasks, or task suites — and they don't need to. They usually refer to all of it as “tasks”.

To learn more, see [How Tolokers see pools](pool-main.md).

## Toloka API and SDK {#api}

If you need to post similar tasks on a regular basis, you can automate working with Toloka by using the [Toloka API](../../api/index.md) and [Python SDK](../../toloka-kit/python-sdk.md).

The Toloka API has some features that are not yet available in the web interface. For example, you can use the API to specify overlap for individual tasks and add multiple correct responses to control tasks.

You can use the Python SDK to integrate the Toloka API into applications written in Python. It already contains all the API classes and methods and there's no need to write new functions for them.

## See also {#see-also}

- [Crowdsourcing concepts](https://toloka.ai/knowledgebase/crowdsourcing-concepts/)
- [What tasks can't be placed in Toloka?](unwanted.md)
- [Common mistakes made by requesters](frequent-customer-errors.md)
- [Where to store media files](cloud-storage.md)

## Troubleshooting {#troubleshooting}

{% include [faq-task-suitable](../_includes/faq/register-and-start/task-suitable.md) %}

{% include [faq-start-new-project](../_includes/faq/register-and-start/start-new-project.md) %}

{% include [contact-support](../_includes/contact-support.md) %}