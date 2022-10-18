# Data collection: Organizations

{% note info %}

Run the project in the [Sandbox](https://sandbox.toloka.yandex.com/) first. This helps you avoid making mistakes and spending money on a task that isn't working right.

{% endnote %}


Field tasks are completed in the Toloka mobile apps for [Android]({{ android-app }}) and [iOS]({{ ios-app }}). A Toloker chooses a point on the map where they need to go to check something and take photos.

You may need additional projects for your task, such as dataset pre-check or checking Tolokers' responses. Learn more about this in [Decomposition of the task](solution-architecture.md).

You may need additional settings for your project, like to add a new button with a particular scenario or a section for attaching files. Learn more in [Customization examples](advanced-features.md).

Let's say you need to check whether an organization has certain facilities.

To do this, create the following task: the Toloker needs to go to the location, take a picture of the outside of the organization, and photograph the facilities inside from different angles. If the facilities are not available, photos are needed as proof. If there is no organization at the address, the Toloker should take a photo of the building where it should be located.

To run tasks and get responses:

1. [Create a project](#project)
1. [Create a task pool](#pool)
1. [Upload tasks](#tasks-upload)
1. [Start the pool and get the results](#launch)

## Create a project {#project}

The project defines what the task will look like for a Toloker.

#### In the interface:

1. Choose a template:

    1. Click {% if locale == "en-com" %}**Create project**{% endif %}.

    1. Select the {% if locale == "en-com" %}**Monitoring items at businesses **{% endif %} template in the {% if locale == "en-com" %}**Spatial Crowdsourcing**{% endif %} block.

1. Provide general information:

    1. Enter a clear name and a short description for the project. Tolokers will see this in the task list.

    1. Optionally add a **Private comment**.

    1. Click **Save**.

1. Edit the task interface in the editor you selected:

    #### Template Builder

    1. The task interface describes how the elements should be arranged in the task.

    Use the {% if locale == "en-com" %}[ready-made code](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4ALLQEhCGcFAIWBLSfFi6dFgARgCufDFEfHy5eCpKAL6+Dk4AFtIuISAxMBCF5jSlRTj25fTMNW5cXj5t-iDcumlE3JogAMIQUky6UAxYULpSRMjCgzgB1kS2rh1+Tt2TACYpupwxTBkDzRYg83QVkytrTX7Fg633yr-bXQ0ri07k4pzghFORg+JTKYkOSmOQNq2k4-U2-1oIzGE2BIAAgqdToZcnwNqYtrQrEE7JSAc4zhcrlAbnc-ACni88boiSS8jDVF9fj9VAjHICeiCuODIdCQN84TQxUMGXjUeiKZi8NjxpMAJKSKRYKF8MDRJh0ODQcmK8XUvbBP7stQnPHnOiXa63DHOvCcyZMQwQU4ZMAmSlCwW2p2dVUo0EyuBQwwClrR5X013xri8KAAax9nQyhlxtQqdDoTDJAHpqwxdAIUnAwJwoEQ6NW+ABmat0CDcCB53TVpjVkkARwyuUkhmrugAbPOACwATgATAAGACMAA5dFuuxvTgB2Ltd4+nACsx90x53x5Xx43MHP884ACsmAhCw97ftagAMjEeZYH2WCBsGoapHAUi6AgLgKoMGYusivQ6LoYZWlAAC0mQVtAP6IsMoy6niADKFS6CSWAMBAxZYJAUTgiskiyJqRwgBhloEQcdIoZKnGYdAnD5Gy7J+roDADjytKYuKca0AAAvWUBQp42F9gOQ7Vu6lwDmATY8XxIriSAumyc6maoXgumcHRlbeuxlkSc8kwkFEeZGAA+oxhjMSkBTynJWCRg4JkPPg+hJoZUAWaZCk7OC3FQHo3C4tGdrQElWFsRQCjBe0fHyVmVJZRIWGcBOGRwCSpyEb6IAVDEjp4FMvBgCBYF8JR1G0fRvn+ax9WmeZvEFURCVmUy9mssNDX+ni7mGJ5hg+RATExAFbFFS0O3heyyEPJNykLGpGn9oOw5WNlwngo2UBgC4GWdE1-60H1yTUX2EBYDAVHJCQkm-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-npkJuql-EZtqpbqZibofLwBZrouHhHm1k7u-Fap-N-Nbu7s1A6k6h5hDoOu3ifnyATilAXgzt2qHmEtZrTFHuXjHimv3omgnrQUXsnslhmjtt9jmllgWrAUQGfF5HwaSEIWWhQUVtWmXtGtnH3oztXoRrXpkvXq-pgcUmUpDrPpesWGbOarEG0rfhYVXhQUPjYR2qPvYTrniFPj7u3mJugiQFUF9M7KnJehUiEuvGMHXCjvoNwJeg9iBjjjctBHQEfivM+pvLkcOs3PwFgCSOkUsP3PeicoHpVpYX4RrGbsQRblbmZrbs1gPt9pNAwSlC7iweIXgB7rQF7lwc4U9q4YYO4cxPmvUTIa-qIfbqZNwcTNHuYbHq-vFkMY-mmhNkwjseodnroTMTliPJpjhq-sYaXj0BXj4fflYZtidrYUERgSESukUjMFIGsNYF4bgY0YoTXrOiPgukXg4SABMoYEsGBPAEnPZFgNEdCT5u+IesvNvB3HEE8ggBCHAs7JUVctgDEJXO7D8akOBg0JvOjOpkQFgqkNAAcnwGJgwHXIDHwFANHKkFCLwLNl-PBrUQiW8okfkPBknFct7FADBnThcRQgCUns0YQWiOjB6JUYDjZPId0YPhrOmpNmnulrZrMKSQYXVlpj0jVjhsZMwlou1jossTZi-EYhVF1twBYj0r1q8APOskNtsXGm1tqQcT6Y8BnnLN4pwtKYKEtuNEErkFWraUdhCjmIBkNntq4IkjTPgUCW2i8aCQVuCautMqsV5i4ZkJbrMRvIvhhODNEScrvhhhvokXSukNDvsukZkSaDkXesnI+h8iWK+hUiQE3AUZUWlNUZUsnAHt4Q0b4YCaqgqebqQe0RQeZnbonikvQQ6YwZOMwbqY1Owa5pwS6gWb7uDHwG4XRB4XMUaYsWACGmIYupHm6lFhsQsd2t6RHnGX6Zmneenq5EIscVRGefSp6WGTKd2tcaVlIU+SzLKaubscdv9q8RQbmWEboDPpMXoQvloWWavuvkhpvgiRIC6msgjkjslAUehcfvyZfgsI9FKXfiCo8XLJCvmKqW-iWBRtzl-rznRvzgxoLgAaxqLsAeLqStxtLpAQJtAYykvrxvAefIgcgagRropm8SpniNgaVnRUkumTOdrAZq0fOeQUXkuV0YdnaYYuavZkwY5qwbQCMXgGMQeRMZXORZkYTvMZORQUsSuUkhFg+esRVs+RQa+XQbBcNsoTqWPhxEcdlloToeRZeaBSXuBWYQFVBVOXKdYcCVmSxbmUUqEKdCkFEI+gaQ6H8cBfVqTNpU8fBdmTBbmVKmJkSYiTWfvrsuUcQu6l-GWeibvFgOSVEFgFSfrnXInMmBUSFroDVKBiQqcHXANR9JAEkeyUejEOvBIJKROYbtBT5aFfpv0G8roCxcFdOQJB+aoeGjmiScDgFq-sZUat5T0Y7uuf0VZa7pFS9LubUAAOrRCSDJAMQlXWDuWG4NqmmXwEyUhmklBFBQ0mR+hZzYkob7bNDKhtZMoZCI1ohUqHV2LaiST2Rhp4B5irWTCmhBhpQwxOCuxfVJg-kUA7gbjczChFChQ1bFCmB1Asi3AoBoDoApjND9YvKTAzxKl7JGjoAS0gAk4S14C-SEGbD83igwRwQCRc6Iq1j1iNhAZi7dgy7aSjhVTThGBziLiribi7j7iHgnhngXjXi3j3iPjPivgfhfgK1FAh7z4hyzyi0o4y2cSe1+1y3axu0C2PBBi4L-wi3eBi24CS04JQSB1qoh2ZQbQsTqK0CXiXicDHhriXiPg7hcxdjziniZ1CDnicDzgbg7hrhrg7iPhng7g7jzg7iFD83s3FBAA){% endif %} for this project with pre-configured validation and task layout.

    The Toloker won't be able to submit the response until they:

    - Are within 50 meters of the specified location.

    - Select one of the three task completion options.

    - Upload the required photos.

    - Write a comment if the business is closed or missing.

    1. To specify what data you will pass to the Toloker and receive in response, create input and output data fields.

    #### What are input and output data?

    **Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

    **Output data** is types of objects that you receive after the task is completed. For example, this could be one of several response options, typed text, or an uploaded file.

    Input data fields are created from the code on the **Example of input data** tab.

    The output data fields depend on the components that use `data.output` and values supported by it.

    Click **Show specifications** to see the input and output data fields.

    Learn more about [input and output data fields]({{ tb-create-specs }}) in the Template Builder Help.

    In this project:

    - Input data fields:

    - `name` — A string with the name of the organization.

    - `image` — A link to the photo of the object.
    - `address` — A string with the task address.
    - `product` — A string with the object description.
    - `coordinates` — Coordinates of the point that the Toloker should go to.

    - Output data fields:

    - `address` — A string with the task address.
    - `comment` — A string for the Toloker's comment.
    - `verdict` — A string with the task completion status.
    - `photo` — An array of files with photos of the object uploaded by the Toloker.
    - `coordinates` — A string with the task coordinates.
    - `imgs_facade` — Array of files with photos of the building uploaded by the Toloker.
    - `imgs_around_obj` — Array of files with photos of the object surroundings uploaded by the Toloker.
    - `imgs_around` — Array of files with photos of the area around the building uploaded by the Toloker.
    - `worker_coordinates` — The Toloker's coordinates at the moment of task completion, with the **Current location** option turned on.
    - `imgs_address` — Array of files with photos of the address sign uploaded by the Toloker.

    1. The **Settings for displaying field tasks** block is used to help the Toloker distinguish one task from another when they select a task on the map. In this project, the **Header format** and **Short description format** fields contain links to the input data fields to show the point's name and address. You can leave these fields unchanged or write something else in them.

    1. Click **Save**.

    #### HTML/CSS/JS editor

    1. The task interface describes how the elements should be arranged in the task.

    In the HTML interface, use the standard HTML tags and [special expressions](t-components.md) in double curly brackets for input and output data fields.

    For this project, leave the **HTML**, **JS**, and **CSS** blocks unchanged.

    **JS** is used to describe the task logic. In addition, the main content of this task is embedded in **JS** for ease of editing.

    The template logic specifies a minimum number of photos of the organization's front, the item, surroundings, address sign, and, if the item isn't there, photos of the area around the building. If you want to change these values, find all strings and change the minimum number of photos for each task completion option:

    ```html
    if (solution.output_values.imgs_facade.length < 2)
    if (solution.output_values.imgs_obj.length < 2)
    if (solution.output_values.imgs_around_obj.length < 4)
    ```

    In this project, the `texts` variable stores the texts for the information block and three task completion options:**I found the object**; **I'm at the business, but the item is missing**; **The business is closed or missing**.

    The `MAX_DISTANCE` variable specifies the maximum distance from the designated point (in kilometers by default) that the Toloker must stay within during task completion. You can specify whatever value you prefer.

    1. In the **Data specification** section, you can configure the input and output data fields.

    #### What are input and output data?

    **Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

    **Output data** is types of objects that you receive after the task is completed. For example, this could be one of several response options, typed text, or an uploaded file.

    In this project:

    - Input data fields:

    - `name` — A string with the name of the organization.

    - `image` — A link to the photo of the object.
    - `address` — A string with the task address.
    - `product` — A string with the object description.
    - `coordinates` — A string with the coordinates of the point that the Toloker should go to.

    - Output data fields:

    - `address` — A string with the task address.
    - `comment` — A string for the Toloker's comment.
    - `verdict` — A string with the task completion status.
    - `photo` — An array of files with photos of the object uploaded by the Toloker.
    - `coordinates` — A string with the task coordinates.
    - `imgs_facade` — Array of files with photos of the building uploaded by the Toloker.
    - `imgs_around_obj` — Array of files with photos of the object surroundings uploaded by the Toloker.
    - `imgs_around` — Array of files with photos of the area around the building uploaded by the Toloker.
    - `worker_coordinates` — The Toloker's coordinates at the moment of task completion, with the **Current location** option turned on.
    - `imgs_address` — Array of files with photos of the address sign uploaded by the Toloker.

    1. The **Settings for displaying field tasks** block is used to help the Toloker distinguish one task from another when they select a task on the map. In this project, the **Header format** and **Short description format** fields contain links to the input data fields to show the point's name and address. You can leave these fields unchanged or write something else in them.

    1. Click ![](../_images/tutorials/image-segmentation/preview-button.png) to see the Toloker's view of the task.

    {% note info %}

    The project preview shows one task with standard data. You can define the number of tasks to show on the page later.

    {% endnote %}

    1. To exit preview mode, click **Exit** in the lower-left corner.

    1. Click **Save**.

1. Write short and clear instructions. Describe what needs to be done and give examples.

    You can prepare instructions in HTML format, then copy and paste into the editor. Click **<>** to switch to HTML mode.

    Field task instructions should be easy to read on a mobile phone screen.

1. To go back to the {% if locale == "en-com" %}**Projects**{% endif %}page, click {% if locale == "en-com" %}**Finish**{% endif %}.

Learn more in the [Project](project.md) section

## Add a task pool {#pool}

A pool is a set of paid tasks sent out for completion at the same time.

1. Open the project and click **Add pool**.
1. Give the pool any convenient name and description. The pool info is only available to you. Tolokers can view only the project name and description.
1. In the **Audience** block, add **Filters** to select Tolokers. To make your tasks available in the Toloka mobile app to English-speaking Tolokers located in Moscow, set the language and region.
1. In the **Price** block, set the price per task (for example, $0.2). For field tasks, always add one task per suite.
    #### What is a task suite?

    A task suite can contain one or several tasks that are shown on the same page. If the tasks are simple, you can add 10-20 tasks per suite. Don't make task suites too long because it slows down loading speed for Tolokers.

    Tolokers get paid for completing the entire task suite.

    The number of tasks per suite is set when [uploading tasks](#tasks-upload).

    #### What is a fair price for a task suite?

    The general rule of pricing is the more time the Toloker spends to complete the task, the higher the price is.

    You can register in Toloka as a Toloker and find out how much other requesters pay for tasks.

1. In the **Quality control** block, set **Overlap**, which is the number of Tolokers to complete the same task. For field tasks, it is usually 1.
1. In the **Quality control** block, enable the **Non-automatic acceptance** option and specify the number of days for checking the task in the **Review period** parameter. (for example, 7).
    #### What is non-automatic acceptance (assignment review)?

    The [non-automatic acceptance](offline-accept.md) option allows you to review [completed assignments](../../glossary.md#submitted-answers) before accepting them and paying for them. If the Toloker didn't follow instructions, you can reject the assignment. The maximum allowed period for the review is set in the **Deadline** field.

1. In the **Additional settings** block, specify the **Time** allowed for completing a task suite. It should be enough to get to the place, find the specified point and upload photos. For field tasks, we recommend allocating a day — 86,400 seconds.
1. Save the pool.

## Upload tasks {#tasks-upload}
 {% if locale == "en-com" %}
Download the sample upload file. You can find it on the pool page. There are links to **files** with regular, control, and training tasks. Use it to prepare your own [file](../../glossary.md#tsv-file-definition) with tasks.
{% endif %}
1. Click **Upload**. In the window that opens, you can also download a sample file.
1. Add input data in it. The header of the input data column contains the word `INPUT`. For field tasks, you also need to specify the latitude `AI:latitude` and longitude `AI:longitude` of the point. You can use a service like [Yandex.Maps]({{ ya-maps-object-search }}) to get the coordinates.
1. Upload the tasks by choosing **Set manually** and set 1 task per suite.

## Start the pool and get the results {#launch}

1. Start the pool by clicking ![](../_images/other/b-start-pool.png).
1. Track the completion of tasks in the **Pool statistics** section.
1. When the first results come in, you can start reviewing.
    To review assignments, go to the pool and click **Download results**. To download attachments, click the button next to ![](../_images/drop-down.svg) and choose **Download attachments**.

    {% note info %}

    After the specified time period, all responses are automatically accepted, regardless of their quality.

    {% endnote %}


{% include [contact-support](../_includes/contact-support-help.md) %}
