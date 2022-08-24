# Product monitoring

{% note info %}

Run the project in the [Sandbox]({{ sandbox }}) first. This helps you avoid making mistakes and spending money on a task that isn't working right.

{% endnote %}


Field tasks are completed in the Toloka mobile apps for [Android]({{ android-app }}) and [iOS]({{ ios-app }}). a Toloker chooses a point on the map where they need to go to check something and take photos.

You may need additional projects for your task, such as dataset pre-check or checking Tolokers' responses. Learn more about this in [Decomposition of the task](solution-architecture.md).

You may need additional settings for your project, like to add a new button with a particular scenario or a section for attaching files. Learn more in [Customization examples](advanced-features.md).

Let's say you need to check how products are displayed in a store.

To do this, create the following task: the Toloker needs to come to the store, take a photo of the outside of the building, find the relevant section inside, and photograph the rack with a certain brand of products. If there are no products of this brand, photos are needed as proof. If there is no store at the address, the Toloker needs to take a photo of the address sign and the building where it should be located.

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

    1. Select the {% if locale == "en-com" %}**Audit of the planogram of products displayed in the store**{% endif %} template in the {% if locale == "en-com" %}**Spatial Crowdsourcing**{% endif %} block.

1. Provide general information:

    1. Enter a clear name and a short description for the project. Tolokers will see this in the task list.

    1. Optionally add a **Private comment**.

    1. Click **Save**.

1. Edit the task interface in the editor you selected:

    #### Template Builder

    1. The task interface describes how the elements should be arranged in the task.

    Use the {% if locale == "en-com" %}[ready-made code](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4AIIArgAmElgQMFh0ABZEWEzculAQCIa6UrHxTIYQkeFgdHxY0XxpugxEkVhw2EkpAhCGLipKAL6+Dk7JUi4hIE0wEHhdOL1TyuZKTszDblxePrM4eOkARkTcmiAAynTtKVC5RMjCG7RWQXY3m-RLB5G6dLqcTUzh6-MWICY70SB3OQ0m-xo3VmM0h9n6zw0ri07k40UIkSMENUsNU8IBzgO2k4a2ukKeOz2B1CkUiHT4fCuphuAWsRFsrnxCMJyJAbw+XygPz+fieQKSB10tPpshAN2hkNxSi5jkRyxRXHRcExhmxPT6YhV-jVRNRpOZ5NolP2vIACkUSmUsGB3kQEO0GEyDQtwIF2cE5qK1C9efzPt9fmSg3hxSDeYViqUTPKYd6cEanjyRsStTq9WIlYaWSbecTeFAANZRhHhQw2kaJOh0JiMgD0rYYugE7zgYE4UCIdFbfAAzK2TtwIBXdK2mK2OgBHcJEARGVu6ABsG4ALABOABMAAYAIwADl0x5Hh8iAHYRyOb5EAKw33Q30833c3w8wB8bzgAFZMAg1YAnc-oHAAMk0FYJBAqTpJk2S5PmUJpoG3IhtmqK6GUcDQAAtNsvwnFAoE+taByHIkugdFgDAQLWzoQO00TnJIsroU8uF0PhZGco8wZIiMPF8ZwfCDuRAJAgwk5Sg8lqqlmtAAAKdlAmKeARE5TjOYY8BALq8dAqE4lxxphgpQaZlhtD6YxzaRha1m0LGBwkO0FZGAA+pArFNK6sqCQqfiFj6+D6NqPYmQJilCeqvoaRIYn6Da5lPFY0TGVAsoUAocXpoJSm2ayWViYu4RwB0kRSaKeCJE0AZ4AAwrwYCwScWB8DRdEMUxfmGGxgW1X4eCWbFLnFcJdnvJ8DnCiNdWAsC7meT5A1DRxpmiiF1lhX4GaYdNeBqRkmnaRAk7Tq2mXJdAaL8B8UBgC46U+g1HIjH1WC0SkJzwTAtE-SQtRYDARR5C0WCTkZYmLQC4MQFIVmTTZx0gKdGlEFpOnXfpMPRfxRVocTmYTBNqPxa8s2CgtzmUzGK28htAVbXKBUkxzTxSLonhsE+h7E7tfgALopoq6GHYs6M5nAGJYuzZmzFLJbYVw+hGCKCLgZ9GGjartDwHskScMRTaETk0QQAR2SMUw8NWrouz1rQhx7EQTpQx8fCwZAUhpIOfGxEw2VeoJeAQCHfG5Vg+UuYdAKUbyACSYOMRpCTJFghiII2XXJNwMAO6qEXcMuBxTttSscwnFFO1SvKhKkDpJlgJASIkmf8Fg2w5Bn-BQAA5HQsTNFn3V7EX9MuVo+jl7ymTeRI0hV-qxO16qScjAAKuPJx0d3YCThJDTtFgUj8HwTQgdP1mz2XCWL+0N9C4JItvffUXZSj0YG6Vd1QE4BVKq9Ri60A+k1I47snTQBSHETOcCo7QEZM3Xsf1dAIDTuEDSQgsCZFQS9BIGDcH4ITI6OguC2h0SPhAE+nBV7TA-nyWaP8lrKTGjTeaTk3piiZtmIw0QygMKwMLNeloBjSASmMcmqZlbFnYSAAuLBDDiXbnQMAcZzKWC7CueQgkN63GgGVGKFADFowSrdbKnAiBLn0JxUmahyYjErrfX+41TEOPMdTAUXCtao0ZhKUsAjezJi5iIoWPDaD0nCNwAMZiqallRLwAQYCnjLxkHosJhUsnGgUcSHmhgKyRAgCQfikSwJ+l1ngAAVNU20iQIAnAqPAqGDkr6YnyAgrq+8iC1OEdXSmesGZ-wIKiApRSSllM8caHWkDqnb10F5LA+5UgNKaZ0qGVCiCDwqIjawYMIaVDgDAGARh-Q-SgAgAwFQ+DwSSO8Ro5QuqIGwGdPBFwfrUIMLRbgDAsCECvtsAwnBqn9LEYM+JU0Eplhgqkn0tYXb1SbC2ZA7YpB0AIrMgiPwgW9nEiOTg6lNL9kHK2JoAhDBJmjuOS6ulvJG24JEbykh-bpA4rOHOL1vLP28seby25vIbgIhfQBTBLlwtVLMg4ABRTwuQA5goLOUmgkLcklRAAyk2Qxoi6AIvAAwErjSly-nxVhgzpYWKMQAoBNjKrVUNaqCB1Imy4U7kwNZtCNl71OPQxWgyRHKtVLhF6IczXDPdY0pxCRKWsByYw6ZTx3FDPNSM+yvw6aBp9G5XkcApAID4PS3CUpOhxoDQm2gUgYm8QVa4OgMbpn7WsqqrxiSuDjOKaUh1hi2RVJALU+pkbmnxChkZN0Ho+l+tRo2oMzaElqx0O2yZXbWT3F5PMxZKRdBg1IM6Y+RACLhCYKswdXqUg5HahUJoXSOgGAivsiSeFoBdTuTREeUM9kj3aXA4dWde5vLIUmCoajO4tCqu8oYFyGiYg+HAbgl6KhHyID8v5AK4BAqICCxVnMIXlotaaLg5YqyuMmngBFBxGzNjbK2dFmLKkYpxW1fFhKzrYxJUOcldaqXIJpVdXQ9LiCMuZdIGo7KahP0MAgby+5+XCqaJwMVN9M0ZTozKuVrKS2DOnaKWdeHeSas4NquAur9WvVwwQSK-JTUU39XO7txjAHAPtcR-xijGrOo+Bo496yWlZ1He6QwDBfXlq07-YNRBQ3Wf9TGD1bBOOxpsyFpaSbZ0tpGGmxyfiovLUCSMXN+bfKun8wwLDSqzOVtiXAGtFA4sNszTpkZ+TaITM7c5u+iVV0jFqc1JGQxrB8AnbV6Z9W8ljKax2qZpaV0QTXcneIfVDBec9cUoeI87i6CvalLpA4XoMlon86RhgebZVwVKKDg51twawMkDomHJ2TUS3iMzCj9NrF+roZdzCPhhpcwo9LGby28Jy4YqQvXQkJYbQ4sWHNREDO08Tf+39Iu-wUZYsStq7FwqcFGvAi90mY8++9pHbXfucPTdw6ZAS4z8MGiErDMOHAPaiSuKt32jrQqSY9fH6SY5x0psN9VjXCnjY+1KtddSPVDq6W07U36ulbIGzkxnRZJsNdG0LpdrXf6i86wspZKyI3eZ-a0HpOyDmBDN3kaIJyzn7IyFclcz7M4PIkDcl5kHwObq+UhusKH+BoeBaCu7LklcqqewLjnlYPtkd5BRlFaKMVYoY3i0czGsaeDY2SnKnHH05R43SzVQnWWBQ5Wg7lEneX8sFbJ0V4rNdLW17QWV8qDVB72nVsP6N9OGeM7B0zKvjWWZMcm4ZKOrVWMc6Auvv8nWNxdZ5g3nqfPG59SV7DWWwsRY8aWsUMXa31tLSH1UyWAe2Y4T4snmWU3Zty3mgtgMXSYlX-GlX5Xq0t+q-vzT7eVcjbbWNjXSm3aHWtA-aEup6zohW46geg2OS-OMsauzWE2NmU2va66SyC+kum2E83A+ADuby56FYQGHczciYZQl6Y8rQHyfmHonAWAu8ZwFwkuUMAGZB+cjEjKPcKQiGyG-yfu6GtBAAQq0LWH9PBC6CHCIVtkQLnNsO0NfPnHsLgRUJ1N1CUk7m+lnCwSPN3B0KlH8hfAyNfLdjAThj-uHgRrClPjWHWORsilRjRonuELin2CnkSqxgOOxlnpSjnnwHntOPxsbIXiJiuLOIhBAGXpJtJtuNXvJrXoASgZAk3upqvofsPjPCMl3vUEZnqr3h9gPoTKzukaPklOPraiAjVFYfrDPiMKEHPm6mAUvhAZIEVkFgfvESABvnEiftFpGrFp-v6qkYmiwkTj9uqn9uTtvq5HwuILfgVs0R6E-mWi-lWpVu-tGuXIrt-sgarn-uri1u0Q3jUtUt1iDv6P1tAZsUNh3uzrsYgSLipmutvAFnBGDE0KfL8BbnLj0lgMJpOHUA7iQIkH8swS3E6APMPKPHLgXPEG8ggHLH9FnLobctgFeiOj1mcVgAABTjALbYzN5EC4IgmkHaE3KXTvEUJfGnB4LwSTiXJGBdR7CXZJDdxaGEnXYpAgwVD4KYi8C4EBa4Jny3JDDMmXI-FwZEAACUxhlxsB1xBwL22MHwuhH2x+kxumaWpOGWXagOVOwOoOix9OQYhpDgUOwewUb0BiCOVmW+ox6MqO906OcG+OJwoI4Rz8+OqpKaJO5+WplRxo1+7AwSQireoUES8OIA0SsShRPov+OgySl+S03OmSph2xsZBm-++xZmhxfauuKQGB4BxEsGbEmCZ8NQhCgJZyUuEmGQcAAAXoTGwTEg0LsJ8VgTLqSeoQgn8twT7mwSQI8qbrodwL8tSRoWctKV-lcWYZ3gJlqlkT3i3u0fkYjjaTZqfolPZjakuOUdqeAm5rPh5vUSeo0XwLWEUNgsWXwK0Qlu0Z0dGb-Avn0RsTeWZp6WueqTND6f9mqdlrqXgHlgWrROnBUcFu0a-qscsDVjKSmVlmmYupmSrtmWgZuotuAadjKAhK6LEAtgdkdkHFfAgNgMBlWQgDWfWdlKbuhSuBUA8lDP6H3C9BOZTKkXATcXGZYe0dHg2HYaitRgnnRtik4Yxq4Sxunh4ZnhSlxrnrjHxgXiysEb4YUKXjyqeDEQpvcT2okWpjWiYXznKXprOQZvOTkYuWZsudaWkSRiMvaQ5mUU5oAU8NUbQLUYeT9KhY0VRQyJhZINeQMbeWACGl0T+Y+Xvs+X5a+cMauamWMZqd+WuVMUDv+bMZ5UFG0WVisVVusfFsxVsbBeYQuhmUgVlkhdUgALJnTvAejMSnF9YK6TmynTlsXpl7FFUppIWyo1BXqAnAlZzPxkUNmHx7qnwLYGFXyinYlnx4nqa4IXn0kdBAhVS4I0InwCkLbfSQBNkravH9x0BSkXH1UwVenqoKneBvYqmRWWVFExVfkTHxWU4HB+z6khlt5mUWYFEjFWXFGbkT4VEOV7m9oADqOckgblj1-ovlmmEOYSppe0wUNwMNBYXQMNSoMYZccJOUyZoekIH5qN4Q6NJItK04tUWwtQDkrOeAFYbxBwfAYARQw5i0TgXYFYAN2oQOp4h4gsioXQu0UO3QpgowQovwKAaA6Auo8wOOFwBw28ipnx6ActIAYIrA8trxxs1wYtqouaGCCUseVGnY3YvEfY4lo4fhM4c4FUK4kghg64W4e4R4Z4F4V4t494j4L4b4H4X4P4f4gEwEatXQeAKVUtMtiMeQct-t0o1FodIAKtjKvt4tgIoJkC0t3gst8tWhkd0dv1otftvo-k7EuivIT4T4nAN4+4T4X4p4AsI4G4d4hdQgD4nAG4h4p4+4+4p4X494p4p4G4p4kwYtfN3QQAA){% endif %} for this project with pre-configured validation and task layout.

    The Toloker won't be able to submit the response until they:

    - Are within 50 meters of the specified location.
    - Select one of the three task completion options.
    - Upload the required photos.
    - Write a comment if the store is closed or missing.

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
    - `name` — A string with the store name.
    - `image` — A link to the product photo.
    - `address` — A string with the task address.
    - `product` — A string with the object description.
    - `coordinates` — Coordinates of the point that the Toloker should go to.

    - Output data fields:

    - `address` — A string with the task address.
    - `comment` — A string for the Toloker's comment.
    - `verdict` — A string with the task completion status.
    - `coordinates` — A string with the task coordinates.
    - `imgs_around` — Array of files with photos of the surrounding area uploaded by the Toloker.
    - `imgs_facade` — Array of files with photos of the store uploaded by the Toloker.
    - `imgs_category` — Array of files with photos of the rack uploaded by the Toloker.
    - `worker_coordinates` — The Toloker's coordinates at the moment of task completion, with the **Current location** option turned on.
    - `imgs_address` — Array of files with photos of the address sign uploaded by the Toloker.

    1. The **Settings for displaying field tasks** block is used to help the Toloker distinguish one task from another when they select a task on the map. In this project, the **Header format** and **Short description format** fields contain links to the input data fields to show the point's name and address. You can leave these fields unchanged or write something else in them.

    1. Click **Save**.

    #### HTML/CSS/JS editor

    1. The task interface describes how the elements should be arranged in the task.

    In the HTML interface, use the standard HTML tags and [special expressions](t-components.md) in double curly brackets for input and output data fields.

    For this project, leave the **HTML**, **JS**, and **CSS** blocks unchanged.

    **JS** is used to describe the task logic. In addition, the main content of this task is embedded in **JS** for ease of editing.

    The template logic specifies a minimum number of photos of the store's front, the object, address sign, and, if there is no object, of the surrounding area. If you want to change these values, find all strings and change the minimum number of photos for each task completion option:

    ```html
    if (solution.output_values.imgs_facade.length < 2)
    if (solution.output_values.imgs_category.length < 2)
    if (solution.output_values.imgs_around.length < 4)
    ```

    In this project, the `texts` variable stores the texts for the information block and three task completion options: **I found the rack**; **There are no brand products**; **Store closed or missing**.

    The `MAX_DISTANCE` variable specifies the maximum distance from the designated point (in kilometers by default) that the Toloker must stay within during task completion. Set whatever value you prefer.

    1. In the **Data specification** section, you can configure the input and output data fields.

    #### What are input and output data?

    **Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

    **Output data** is types of objects that you receive after the task is completed. For example, this could be one of several response options, typed text, or an uploaded file.

    Learn more about the **Specification** parameters in [Input and output data](incoming.md).

    In this project:

    - Input data fields:

    - `name` — A string with the store name.
    - `image` — A link to the product photo.
    - `address` — A string with the task address.
    - `product` — A string with the object description.
    - `coordinates` — A string with the coordinates of the point that the Toloker should go to.

    - Output data fields:

    - `address` — A string with the task address.
    - `comment` — A string for the Toloker's comment.
    - `verdict` — A string with the task completion status.
    - `coordinates` — A string with the task coordinates.
    - `imgs_around` — Array of files with photos of the surrounding area uploaded by the Toloker.
    - `imgs_facade` — Array of files with photos of the store uploaded by the Toloker.
    - `imgs_category` — Array of files with photos of the rack uploaded by the Toloker.
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

    The [non-automatic acceptance](offline-accept.md) option allows you to review [completed assignments](../../glossary.md#submitted-answers-ru) before accepting them and paying for them. If the Toloker didn't follow instructions, you can reject the assignment. The maximum allowed period for the review is set in the **Deadline** field.

1. In the **Additional settings** block, specify the **Time** allowed for completing a task suite. It should be enough to get to the place, find the specified point and upload photos. For field tasks, we recommend allocating a day — 86,400 seconds.
1. Save the pool.

## Upload tasks {#tasks-upload}
 {% if locale == "en-com" %}
Download the sample upload file. You can find it on the pool page. There are links to **files** with regular, control, and training tasks. Use it to prepare your own [file](../../glossary.md#tsv-file-definition-ru) with tasks.
{% endif %}
1. Click **Upload**. In the window that opens, you can also download a sample file.

1. Add input data in it. The header of the input data column contains the word `INPUT`. For field tasks, you also need to specify the latitude `AI:latitude` and longitude `AI:longitude` of the point. You can use a service like [Yandex.Maps]({{ ya-maps-object-search }}) to get the coordinates.

    ![](../_images/tutorials/audit-place/audit-download.png)

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