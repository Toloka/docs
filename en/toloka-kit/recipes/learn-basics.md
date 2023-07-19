# Sample project recipe

[![Open In Colab](../../../_images/colab-badge.svg)](https://colab.research.google.com/github/Toloka/toloka-kit/blob/main/examples/0.getting_started/0.learn_the_basics/learn_the_basics.ipynb) | [Source code](https://github.com/Toloka/toloka-kit/blob/main/examples/0.getting_started/0.learn_the_basics/learn_the_basics.ipynb)

## Before you start

Before you start using the Toloka-Kit library in your own Python code, you need to:

- [Register](../registration.md) in the web version of Toloka.
- [Top up](../registration.md#top-up) your account.
- [Install Toloka-Kit](../quick-start.md).

## Label data

To use Toloka-Kit for data labeling, follow the steps below.

### First steps {#first-step}

First, you need to import the necessary libraries into your Python script and set up logging:

```python
import datetime
import time
import logging
import sys
import getpass

import pandas

import toloka.client as toloka
import toloka.client.project.template_builder as tb

logging.basicConfig(
    format='[%(levelname)s] %(name)s: %(message)s',
    level=logging.INFO,
    stream=sys.stdout,
)
```

Now, create a [Toloka client](../reference/toloka.client.TolokaClient.md) instance. All API calls will go through it:

```python
toloka_client = toloka.TolokaClient(getpass.getpass('Enter your OAuth token: '), 'PRODUCTION') # Or switch to 'SANDBOX'
# Lines below check that the OAuth token is correct and print your account name
print(toloka_client.get_requester())
```

{% note tip "The code portion above uses" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_requester()](../reference/toloka.client.TolokaClient.get_requester.md) method_

{% endnote %}

The response to the above request will look like this:

```bash
Requester(_unexpected={}, id='6c6c50dce62ca4aef87dfcbc6e9de162', balance=Decimal('1.0000'), public_name={'EN': 'John Smith'}, company=None)
```

### Project

A [project](../../guide/concepts/overview.md#project) is a top-level object. It contains instructions, task interface settings, input and output data specification, and default quality control rules for this project pools. Projects make it easier for you to post similar tasks in the future, because you don't have to re-configure the interface.

The easier the task, the better the results. If your task contains more than one question, you should divide it into several projects.

In this tutorial you will create a project with tasks that ask Tolokers to specify the type of animal depicted in a photo:

```python
new_project = toloka.Project(
    public_name='Cat or Dog?',
    public_description='Specify the type of animal depicted in a photo.',
)
```

{% note tip "The code portion above uses" %}

- _[Project](../reference/toloka.client.project.Project.md) class_

{% endnote %}

The code above creates an object in your device memory. This is not all, the project must also contain:

- [Input and output data specification](../../guide/concepts/incoming.md)
- [Task interface settings](../../guide/concepts/spec.md)
- [Instructions for Tolokers](../../guide/concepts/instruction.md)

{% note alert "Important" %}

Code samples below will add changes to the object stored in your device memory. The data will only be sent to the server after calling one of the `toloka_client` methods.

{% endnote %}

#### Input and output data

The `image` input field contains URLs of images that need to be labeled.

The `result` output field will receive `cat` and `dog` labels.

```python
input_specification = {'image': toloka.project.UrlSpec()}
output_specification = {'result': toloka.project.StringSpec()}
```

{% note tip "The code portion above uses" %}

- _[UrlSpec](../reference/toloka.client.project.field_spec.UrlSpec.md) class_
- _[StringSpec](../reference/toloka.client.project.field_spec.StringSpec.md) class_

{% endnote %}

#### Interface

The task interface displays the main task elements to Tolokers. It's important because it is how Tolokers see your tasks. If it's too complicated and unclear, the labeling results might be poor.

There are two editors available in Toloka:

- [HTML/CSS/JS editor](../../guide/concepts/spec.md#interface-section)
- [Template Builder](../../template-builder/index.md)

Template Builder configures task interface at the entity level. We recommend it for your projects, especially for the first ones.

The code below creates a task interface for our project:

```python
# This component shows images
image_viewer = tb.ImageViewV1(tb.InputData('image'), ratio=[1, 1])

# This component allows to select a label
radio_group_field = tb.RadioGroupFieldV1(
    tb.OutputData('result'),
    [
        tb.fields.GroupFieldOption('cat', 'Cat'),
        tb.fields.GroupFieldOption('dog', 'Dog')
    ],
    validation=tb.RequiredConditionV1(),
)

# Allows to set a width limit when displaying a task
task_width_plugin = tb.TolokaPluginV1(
    'scroll',
    task_width=400,
)

# How Tolokers will see the task
project_interface = toloka.project.TemplateBuilderViewSpec(
    view=tb.ListViewV1([image_viewer, radio_group_field]),
    plugins=[task_width_plugin],
)

# This block assigns task interface and input/output data specification to the project
# Note that this is done via the task specification class
new_project.task_spec = toloka.project.task_spec.TaskSpec(
    input_spec=input_specification,
    output_spec=output_specification,
    view_spec=project_interface,
)
```

{% note tip "The code portion above uses" %}

- _[ImageViewV1](../reference/toloka.client.project.template_builder.view.ImageViewV1.md) class_
- _[InputData](../reference/toloka.client.project.template_builder.data.InputData.md) class_
- _[RadioGroupFieldV1](../reference/toloka.client.project.template_builder.fields.RadioGroupFieldV1.md) class_
- _[OutputData](../reference/toloka.client.project.template_builder.data.OutputData.md) class_
- _[GroupFieldOption](../reference/toloka.client.project.template_builder.fields.GroupFieldOption.md) class_
- _[RequiredConditionV1](../reference/toloka.client.project.template_builder.conditions.RequiredConditionV1.md) class_
- _[TolokaPluginV1](../reference/toloka.client.project.template_builder.plugins.TolokaPluginV1.md) class_
- _[TemplateBuilderViewSpec](../reference/toloka.client.project.view_spec.TemplateBuilderViewSpec.md) class_
- _[TaskSpec](../reference/toloka.client.project.task_spec.TaskSpec.md) class_

{% endnote %}

#### Instructions

The first thing the Tolokers see when they select a task are the [instructions](../../guide/concepts/instruction.md) that you wrote. Describe what needs to be done in simple and clear language, and give examples.

Good instructions help the Tolokers complete the task correctly. The clarity and completeness of the instructions affect the response quality and the project rating. Unclear or too complex instructions, on the contrary, will scare off Tolokers.

Create the instructions for your project with the following code:

```python
new_project.public_instructions = 'Look at the picture. Determine what is on it: a <b>cat</b> or a <b>dog</b>. Choose the correct option.'
```

#### Create project

Now, use `toloka_client` [defined at the beginning](#first-step) to create the project.

The data is only sent to the server after calling one of the `toloka_client` methods, the code below actually creates a project:

```python
new_project = toloka_client.create_project(new_project)
```

{% note tip "The code portion above uses" %}

- _[create_project()](../reference/toloka.client.TolokaClient.create_project.md) method_

{% endnote %}

You will get an output which looks like this:

```bash
[INFO] toloka.client: A new project with ID "120798" has been created. Link to open in web interface: https://platform.toloka.ai/requester/project/120798
```

This means that you successfully created the project with the parameters that you defined at the previous steps.

#### Preview project

1. Go to the project page to make sure the task interface works correctly. To do this, click the link in the output of the code above.

1. In the upper-right corner of the project page click ![Project actions](../../guide/_images/drop-down.svg) → **![Preview](../../guide/_images/preview.svg) Preview**:

    ![What the project interface might look like](../_images/learn-basics/project_look.png =700x)

1. In the upper part of the preview page click **Change input data**, and insert an image URL into the `image` field, then click **Apply**:

    ![What the task interface might look like and how to insert images in the preview](../_images/learn-basics/task_look.png =700x)

1. In the upper part of the preview demonstration click **Instructions**. Make sure the instructions are shown and that they say what you want them to.

1. Select an option in your task. In the lower-left corner of the preview demonstration click **Submit**, then **View responses**. In the appeared result window, check that your results are written in expected format and that the entered data is correct:

    ![What the results might look like](../_images/learn-basics/results_preview.png =700x)

{% note info %}

- We strongly recommend **checking the task interface and instructions** every time you create a project. This will help you to ensure that the Tolokers will complete the task and that your results will be useful.

- Do a **trial run** with a small amount of data. Make sure that after running the entire pipeline you get the data in the expected format and quality.

{% endnote %}

### Pool

A [pool](../../guide/concepts/overview.md#pool) is a set of tasks that share common pricing, start date, selection of Tolokers, overlap, and quality control configurations. All task in a pool are processed in parallel. One project can have several pools. You can add new tasks to a pool at any time, as well as open or stop it.

The code below will create a pool as an object in your device memory. You will send it to Toloka with `toloka_client` method a bit later.

```python
new_pool = toloka.Pool(
    project_id=new_project.id,
    private_name='Pool 1',  # Only you can see this information
    may_contain_adult_content=False,
    reward_per_assignment=0.005,  # Sets the minimum payment amount for one task suite in USD
    assignment_max_duration_seconds=60*5,  # Gives Tolokers 5 minutes to complete one task suite
    will_expire=datetime.datetime.utcnow() + datetime.timedelta(days=365),  # Sets that the pool will close after one year
)
```

{% note tip "The code portion above uses" %}

- _[Pool](../reference/toloka.client.pool.Pool.md) class_

{% endnote %}

#### Overlap

To minimize the risk of getting wrong answers, you can ask several Tolokers to complete the same task. This is called _overlap_.

In this example we set the overlap to `3`. This means that **every** task will be completed by **three** different Tolokers.

```python
new_pool.defaults = toloka.pool.Pool.Defaults(
    default_overlap_for_new_tasks=3,
    default_overlap_for_new_task_suites=0,
)
```

{% note tip "The code portion above uses" %}

- _[Defaults](../reference/toloka.client.pool.Pool.Defaults.md) class_

{% endnote %}

#### Task suite

A [task suite](../../guide/concepts/overview.md#tasks-page) is a set of tasks that are shown on a single page.

An important part of configuring pools is to decide how many tasks will be assigned to a Toloker at once. For example, if you set 3 tasks for a task suite, a Toloker will see three images at once on one page.

{% note info %}

The `reward_per_assignment` and `assignment_max_duration_seconds` fields in pool settings set the price and time for one **task suite**, not task.

{% endnote %}

Why you should combine tasks in a task suite:

- To set a more precise price for a single task.

- To calculate a Toloker's skill and use it to determine the correct answer more accurately. Learn more in the [Aggregation](#aggregation) section.

- To better apply quality control settings that improve the final quality of the response. Learn more in the [Quality control rules](#quality_control_rules) section.

```python
new_pool.set_mixer_config(
    real_tasks_count=10,  # The number of tasks per page.
)
```

{% note tip "The code portion above uses" %}

- _[set_mixer_config](../reference/toloka.client.pool.codegen_setter_for_mixer_config.md) setter for the [Pool](../reference/toloka.client.pool.Pool.md) class_

{% endnote %}

#### Filters

[Filters](../../guide/concepts/filters.md) help you select Tolokers for your project.

There may be different reasons to use filters, for example:

- You require some specific group of Tolokers for your pool.

- You want to exclude a certain group of Tolokers.

Tasks will only be shown to matching Tolokers, rather than to all of them.

This example requires English-speaking Tolokers, because the project instructions are in English:

```python
new_pool.filter = toloka.filter.Languages.in_('EN')
```

{% note tip "The code portion above uses" %}

- _[Languages](../reference/toloka.client.filter.Languages.md) class_

{% endnote %}

#### Quality control rules {#quality_control_rules}

[Quality control rules](../../guide/concepts/check-performers.md) regulate task completion and Toloker access.

Quality control lets you get more accurate responses and restrict access to tasks for cheating users. All rules work independently. Learn more about [settting up quality control](../../guide/concepts/qa-pool-settings.md).

This example uses the captcha rule. It is the simplest way to exclude fake users (robots) and cheaters:

```python
# Turns on captchas
new_pool.set_captcha_frequency('MEDIUM')
# Bans Tolokers by captcha criteria
new_pool.quality_control.add_action(
    # Type of quality control rule
    collector=toloka.collectors.Captcha(history_size=5),
    # This condition triggers the action below
    # Here overridden comparison operator actually returns a Condition object
    conditions=[toloka.conditions.FailRate > 20],
    # What exactly should the rule do when the condition is met
    # It bans the Toloker for 1 day
    action=toloka.actions.RestrictionV2(
        scope='PROJECT',
        duration=1,
        duration_unit='DAYS',
        private_comment='Captcha',
    )
)
```

{% note tip "The code portion above uses" %}

- _[set_captcha_frequency](../reference/toloka.client.pool.codegen_setter_for_quality_control_captcha_frequency.md) setter for the [Pool](../reference/toloka.client.pool.Pool.md) class_
- _[Captcha](../reference/toloka.client.collectors.Captcha.md) class_

{% endnote %}

#### Create pool

The code below creates a pool with all the information above which was stored in your device memory:

```python
new_pool = toloka_client.create_pool(new_pool)
```

{% note tip "The code portion above uses" %}

- _[create_pool()](../reference/toloka.client.TolokaClient.create_pool.md) method_

{% endnote %}

You will get an output which looks like this:

```bash
[INFO] toloka.client: A new pool with ID "36502086" has been created. Link to open in web interface: https://platform.toloka.ai/requester/project/120798/pool/36502086
```

Open your project page. You will see your new pool:

![Project interface with a pool](../_images/learn-basics/project_with_pool.png =700x)

The pool interface looks like this:

![Pool interface](../_images/learn-basics/pool_preview.png =700x)

Right now the pool is empty and closed. It has no tasks or task suites.

### Upload tasks

A [task](../../guide/concepts/overview.md#task) is the smallest portion of data you need to mark up.

This example uses a small data set with images. This dataset is collected by the Toloka team and distributed under a [Creative Commons Attribution 4.0 International license](https://creativecommons.org/licenses/by/4.0/).

Download the data set

```bash
curl https://tlk.s3.yandex.net/dataset/cats_vs_dogs/toy_dataset.tsv --output dataset.tsv
```

Use the code below to parse the downloaded TSV file:

```python
dataset = pandas.read_csv('dataset.tsv', sep='\t')

print(f'Dataset contains {len(dataset)} rows\n')

dataset = dataset.sample(frac=1).reset_index(drop=True)
```

Create tasks. One task will be created from one image.

Toloka will automatically create task suites and show the tasks depending on a project overlap:

1. One task suite will consist of 10 tasks.

2. Toloka will let 3 different Tolokers to complete the tasks.

We configured these settings while creating the pool.

```python
tasks = [
    toloka.Task(input_values={'image': url}, pool_id=new_pool.id)
    for url in dataset['url']
]
# Add tasks to a pool
toloka_client.create_tasks(tasks, allow_defaults=True)
print(f'Populated pool with {len(tasks)} tasks')
print(f'To view this pool, go to https://toloka.dev/requester/project/{new_project.id}/pool/{new_pool.id}')
# print(f'To view this pool, go to https://sandbox.toloka.dev/requester/project/{new_project.id}/pool/{new_pool.id}') # Print a sandbox version link

# Opens the pool
new_pool = toloka_client.open_pool(new_pool.id)
```

{% note tip "The code portion above uses" %}

- _[Task](../reference/toloka.client.task.Task.md) class_
- _[create_tasks()](../reference/toloka.client.TolokaClient.create_pool.md) method_

{% endnote %}

When you open your pool, Tolokers will see your tasks in their mobile app or in Toloka web version, and start working on them.

In small pools like this, it usually takes up to 10 minutes for all the tasks to be performed.

With big pools, we recommend that you set up automatic waiting. See the example below:

```python
pool_id = new_pool.id

def wait_pool_for_close(pool_id, minutes_to_wait=1):
    sleep_time = 60 * minutes_to_wait
    pool = toloka_client.get_pool(pool_id)
    while not pool.is_closed():
        op = toloka_client.get_analytics([toloka.analytics_request.CompletionPercentagePoolAnalytics(subject_id=pool.id)])
        op = toloka_client.wait_operation(op)
        percentage = op.details['value'][0]['result']['value']
        print(
            f'   {datetime.datetime.now().strftime("%H:%M:%S")}\t'
            f'Pool {pool.id} - {percentage}%'
        )
        time.sleep(sleep_time)
        pool = toloka_client.get_pool(pool.id)
    print('Pool was closed.')

wait_pool_for_close(pool_id)
```

{% note tip "The code portion above uses" %}

- _[get_pool()](../reference/toloka.client.TolokaClient.get_pool.md) method_
- _[get_analytics()](../reference/toloka.client.TolokaClient.get_analytics.md) method_
- _[CompletionPercentagePoolAnalytics](../reference/toloka.client.analytics_request.CompletionPercentagePoolAnalytics.md) class_
- _[wait_operation()](../reference/toloka.client.TolokaClient.wait_operation.md) method_

{% endnote %}

The response to the above request will look like this:

```bash
Dataset contains 202 rows

100%|████████████████████████████████████████████| 100/100 [00:23<00:00,  4.34it/s]
Populated pool with 202 tasks
To view this pool, go to https://toloka.dev/requester/project/120798/pool/36502086
100%|████████████████████████████████████████████| 100/100 [00:01<00:00, 51.91it/s]
   19:08:35     Pool 36502086 - 0%
100%|████████████████████████████████████████████| 100/100 [00:00<00:00, 157.34it/s]
   19:09:36     Pool 36502086 - 74%
100%|████████████████████████████████████████████| 100/100 [00:01<00:00, 51.10it/s]
   19:12:42     Pool 36502086 - 100%
Pool was closed.
[WARNING] toloka.client: Experimental method
answers count: 606
```

### Complete code

{% cut "The complete code for creating a project, adding a pool, uploading tasks, and starting labeling" %}

```python
import datetime
import time
import logging
import sys
import getpass

import pandas

import toloka.client as toloka
import toloka.client.project.template_builder as tb

logging.basicConfig(
    format='[%(levelname)s] %(name)s: %(message)s',
    level=logging.INFO,
    stream=sys.stdout,
)

toloka_client = toloka.TolokaClient(getpass.getpass('Enter your OAuth token: '), 'PRODUCTION') # Or switch to 'SANDBOX'
# Lines below check that the OAuth token is correct and print your account name
# print(toloka_client.get_requester())

new_project = toloka.Project(
    public_name='Cat or Dog?',
    public_description='Specify the type of animal depicted in a photo.',
)

input_specification = {'image': toloka.project.UrlSpec()}
output_specification = {'result': toloka.project.StringSpec()}

# This component shows images
image_viewer = tb.ImageViewV1(tb.InputData('image'), ratio=[1, 1])

# This component allows to select a label
radio_group_field = tb.RadioGroupFieldV1(
    tb.OutputData('result'),
    [
        tb.fields.GroupFieldOption('cat', 'Cat'),
        tb.fields.GroupFieldOption('dog', 'Dog')
    ],
    validation=tb.RequiredConditionV1(),
)

# Allows to set a width limit when displaying a task
task_width_plugin = tb.TolokaPluginV1(
    'scroll',
    task_width=400,
)

# How Tolokers will see the task
project_interface = toloka.project.TemplateBuilderViewSpec(
    view=tb.ListViewV1([image_viewer, radio_group_field]),
    plugins=[task_width_plugin],
)

# This block assigns task interface and input/output data specification to the project
# Note that this is done via the task specification class
new_project.task_spec = toloka.project.task_spec.TaskSpec(
    input_spec=input_specification,
    output_spec=output_specification,
    view_spec=project_interface,
)

new_project.public_instructions = 'Look at the picture. Determine what is on it: a <b>cat</b> or a <b>dog</b>. Choose the correct option.'

new_project = toloka_client.create_project(new_project)

new_pool = toloka.Pool(
    project_id='120798',
    private_name='Pool 1',  # Only you can see this information
    may_contain_adult_content=False,
    reward_per_assignment=0.005,  # Sets the minimum payment amount for one task suite in USD
    assignment_max_duration_seconds=60*5,  # Gives Tolokers 5 minutes to complete one task suite
    will_expire=datetime.datetime.utcnow() + datetime.timedelta(days=365),  # Sets that the pool will close after one year
)

new_pool.defaults = toloka.pool.Pool.Defaults(
    default_overlap_for_new_tasks=3,
    default_overlap_for_new_task_suites=0,
)

new_pool.set_mixer_config(
    real_tasks_count=10,  # The number of tasks per page.
)

new_pool.filter = toloka.filter.Languages.in_('EN')

# Turns on captchas
new_pool.set_captcha_frequency('MEDIUM')
# Bans Tolokers by captcha criteria
new_pool.quality_control.add_action(
    # Type of quality control rule
    collector=toloka.collectors.Captcha(history_size=5),
    # This condition triggers the action below
    # Here overridden comparison operator actually returns a Condition object
    conditions=[toloka.conditions.FailRate > 20],
    # What exactly should the rule do when the condition is met
    # It bans the Toloker for 1 day
    action=toloka.actions.RestrictionV2(
        scope='PROJECT',
        duration=1,
        duration_unit='DAYS',
        private_comment='Captcha',
    )
)

new_pool = toloka_client.create_pool(new_pool)

dataset = pandas.read_csv('dataset.tsv', sep='\t')

print(f'Dataset contains {len(dataset)} rows\n')

dataset = dataset.sample(frac=1).reset_index(drop=True)

tasks = [
    toloka.Task(input_values={'image': url}, pool_id=new_pool.id)
    for url in dataset['url']
]
# Add tasks to a pool
toloka_client.create_tasks(tasks, allow_defaults=True)
print(f'Populated pool with {len(tasks)} tasks')
print(f'To view this pool, go to https://toloka.dev/requester/project/{new_project.id}/pool/{new_pool.id}')
# print(f'To view this pool, go to https://sandbox.toloka.dev/requester/project/{new_project.id}/pool/{new_pool.id}') # Print a sandbox version link

# Opens the pool
new_pool = toloka_client.open_pool(new_pool.id)

pool_id = new_pool.id

def wait_pool_for_close(pool_id, minutes_to_wait=1):
    sleep_time = 60 * minutes_to_wait
    pool = toloka_client.get_pool(pool_id)
    while not pool.is_closed():
        op = toloka_client.get_analytics([toloka.analytics_request.CompletionPercentagePoolAnalytics(subject_id=pool.id)])
        op = toloka_client.wait_operation(op)
        percentage = op.details['value'][0]['result']['value']
        print(
            f'   {datetime.datetime.now().strftime("%H:%M:%S")}\t'
            f'Pool {pool.id} - {percentage}%'
        )
        time.sleep(sleep_time)
        pool = toloka_client.get_pool(pool.id)
    print('Pool was closed.')

wait_pool_for_close(pool_id)
```

{% endcut %}

## Get responses

When all the tasks are completed, look at the responses from Tolokers:

```python
answers_df = toloka_client.get_assignments_df(pool_id)
# Prepare dataframe for aggregation
answers_df = answers_df.rename(columns={
    'INPUT:image': 'task',
    'OUTPUT:result': 'label',
    'ASSIGNMENT:worker_id': 'worker',
})

print(f'answers count: {len(answers_df)}')
```

{% note tip "The code portion above uses" %}

- _[get_assignments_df()](../reference/toloka.client.TolokaClient.get_assignments_df.md) method_

{% endnote %}

An `assignment` value is one Toloker's responses to all the tasks on a task suite.

If a Toloker completed several task suites, then `toloka_client.get_assignments_df` will contain several `assignment` values.

### Aggregation {#aggregation}

You should run the [results aggregation](../../guide/concepts/result-aggregation.md) only if you set the overlap for the tasks to 2 or higher.

The [majority vote](../../guide/concepts/mvote.md) method is a quality control method based on matching responses from the majority of Tolokers who complete the same task. For example, if 2 out of 3 Tolokers selected the `cat` label, then the final label for this task will be `cat`.

Majority vote is easily implemented, but you can also use our crowdsourcing [Crowd-Kit library](../../crowd-kit/index.md). It contains a lot of new aggregation methods.

Install it using the command below:

```bash
$ pip install crowd-kit
```

And include it into your script:

```python
from crowdkit.aggregation import MajorityVote

# Run majority vote aggregation
predicted_answers = MajorityVote().fit_predict(answers_df)

print(predicted_answers)
```

{% note tip "The code portion above uses" %}

- _[fit_predict()](../../crowd-kit/reference/crowdkit.aggregation.classification.majority_vote.MajorityVote.fit_predict.md) method of the Crowd-Kit [MajorityVote](../../crowd-kit/reference/crowdkit.aggregation.classification.majority_vote.MajorityVote.md) class_

{% endnote %}

Run the code and look at the results.

The output might look like this:

```bash
answers count: 606
task
https://tlk.s3.yandex.net/dataset/cats_vs_dogs/cats/052a05203748432a882ed886a74a3ef7.jpg    cat
https://tlk.s3.yandex.net/dataset/cats_vs_dogs/cats/0bc36c831807421b8aef030586e4e585.jpg    cat
https://tlk.s3.yandex.net/dataset/cats_vs_dogs/cats/0ddcd307bb7e4cceb10ccc5bd9ccecc8.jpg    cat
https://tlk.s3.yandex.net/dataset/cats_vs_dogs/cats/0e0ddb3281784fa7986bde033266fc6e.jpg    cat
https://tlk.s3.yandex.net/dataset/cats_vs_dogs/cats/0e290f523d554f0b82b494827b2d9b39.jpg    cat
                                                                                           ...
https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/f2cf0283882e4c738e0fb7bd429b967b.jpg    dog
https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/f50b73a7c9ec4f4d9b6f60c97b1d5aff.jpg    dog
https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/f5b0f1f8357849cca75a0995701a682c.jpg    dog
https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/fb9fc4a4788442eb891c86cc7a609750.jpg    dog
https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/ffb6ceff76d348bfb9d448d4e90f9daf.jpg    dog
Name: agg_label, Length: 202, dtype: object
```

If you prefer to run the code using [Jupyter Notebook](https://colab.research.google.com/github/Toloka/toloka-kit/blob/main/examples/0.getting_started/0.learn_the_basics/learn_the_basics.ipynb), you will have a visual preview for the images from your tasks:

![Possible results](../_images/learn-basics/possible_results.png =700x)

### Complete code

{% cut "The complete code for getting results" %}

```python
from crowdkit.aggregation import MajorityVote
import getpass

import toloka.client as toloka

toloka_client = toloka.TolokaClient(getpass.getpass('Enter your OAuth token: '), 'PRODUCTION') # Or switch to 'SANDBOX'

# Get the ID of the pool with the tasks (pool_id) from the web version of the Toloka platform or from the previous script results
answers_df = toloka_client.get_assignments_df(pool_id)
# Prepare dataframe for aggregation
answers_df = answers_df.rename(columns={
    'INPUT:image': 'task',
    'OUTPUT:result': 'label',
    'ASSIGNMENT:worker_id': 'worker',
})

print(f'answers count: {len(answers_df)}')

# Run majority vote aggregation
predicted_answers = MajorityVote().fit_predict(answers_df)

print(predicted_answers)
```

{% endcut %}

## Useful links

- [Toloka-Kit recipe list](use-cases.md)
- [Toloka documentation](../../index.md)
- [Toloka API documentation](https://toloka.ai/docs/api/api-reference/)
- [Toloka homepage](https://toloka.ai/)

{% include [image-styles](../../../_includes/image-styles-internal.md) %}