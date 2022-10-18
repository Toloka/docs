# Price monitoring

{% note info %}

Run the project in the [Sandbox](https://sandbox.toloka.yandex.com/) first. This helps you avoid making mistakes and spending money on a task that isn't working right.

{% endnote %}


Field tasks are completed in the Toloka mobile apps for [Android]({{ android-app }}) and [iOS]({{ ios-app }}). A Toloker chooses a point on the map where they need to go to check something and take photos.

You may need additional projects for your task, such as dataset pre-check or checking Tolokers' responses. Learn more about this in [Decomposition of the task](solution-architecture.md).

You may need additional settings for your project, like to add a new button with a particular scenario or a section for attaching files. Learn more in [Customization examples](advanced-features.md).

Use the “Product and price tag photo” template when you need to:
- Check if prices are up-to-date at specific retail outlets.
- Compare competitors' pricing and stocking policies.
- Monitor promotions and special offers.
- Run OOS (out-of-stock) control.

Let's say you need to find out the product price in a particular store.

To do this, create the following task: the Toloker needs to go to the location, take a picture of the store's front, and photograph the product and its price tag. If there is no product or price tag, provide photos as evidence. If there is no store at the address, take a photo of the building where it should be located.

To run tasks and get responses:

1. [Create a project](#project)
1. [Add a task pool](#pool)
1. [Upload tasks](#tasks-upload)
1. [Upload the pool and get results](#launch)

## Create a project {#project}

The project defines what the task will look like for a Toloker.

#### In the interface:

1. Choose a template:

    1. Click {% if locale == "en-com" %}**Create project**{% endif %}.

    1. Select the {% if locale == "en-com" %}**Photos of product and price tag**{% endif %} template.

1. Provide general information:

    1. Enter a clear name and a short description for the project. Tolokers will see this in the task list.

    1. Optionally add a **Private comment**.

    1. Click **Save**.

1. Edit the task interface in the editor you selected:

    #### Template Builder

    1. The task interface describes how the elements should be arranged in the task.

    Use the {% if locale == "en-com" %}[ready-made code](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4AAoAFhB0EHxYEDBYTIYQACYArmB0WLpQKYmGcGBEWHS6CHgqSgC+vg5O4dIuISBwsBAV5jQ1lTj2dfTMTW5cXj49-iDcugBGRNyaIAAqEgbIwuM4AdZEtq59fk6DCym6pZytTGljnRYgTKfhC1C6Ui4bWFXj3TfKP5sDGlcWncnBScEIKSMHVU31U+yUh0BzW0nFG6z+tCms3mQJAAEEUilDEQ+Hw1qZ3lsgnZ3v9nMdTrpzlBLtc-P97nRHrjdITiaToQ5Pj9YUp4Y4AUNgVwwRCoSAvrUxOKJvTcSi0RSMXgsXMFgBJSRSLCQvhgApMOhwaDkpUI8CBHbBX7stRHXEnM4XK7o114Tnc5pJVIZEzvYUwu29SmShYo2VwSGGQViUXKmNq5Eg3hQADWvv6aUMOOa4TodCYZIA9FWGLoBKdCpwoEQ6FW+ABmKvRbgQXO6KtMKvEgCOaRJkkMVd0ADYZwAWACcACYAAwARgAHLp1x3VykAOwdjsHlIAVgPugPm4Pi4Pq5gJ5nnAAVkxylqDg7trtmgAZVpcxKCB8hDTIsDgKQyjeEUoxdfpM2GHRdEya0oAAWmmK5oigAtbl1EtaAAZXCXRiSwBgICLLBIAgQwwWeSRZE-foUKtaAaQxOl3WaNi0M4PhWzw-p7gYXteU411uKRWgAAE61yIhPHQns+wHT0mV7MBGw4hUuI+OCJQ0ySpMRKUQA0zgqIrH0WL9O4HgWEg6NzIwAH1aPo1pThJFMhXDQz2H0RMdNwvZaTdGStjBdioD0bgcUC-4rBitDmIoBR9OjLLVR42gUokfjRzSOBiRSYT7PCVpnTwABhXgwCArliiw8toGArA+FI8jKOozyGJ85ikvtYzwpyiVELwSzvTZKSJQDJyXPc-rvKYvzXQjKS03ZFUv0mkB5JySFlNU-sqwK2LQX4UooCKCr2TwKrf1oXrsnI6IQJgMjshIXQGCwGBkmNZqsC00LOHur9AYgKQTLm6TzMOxSTogXszsssHYvW9ltvs6I4fhsyGS9FlbOG24FtxFbGN8vT4YMiKJSgzw2DPVdGY+CKAF1w0VcZdsi8z43BRN5T5n4BaJ9UQX0IxZtuKxqTGvG8rweA5hSThWpw9DDF5a10IQZI0iYSGJgIhYiLmIhwJB0o+CAyApCYAxYriS00NtCK8AgD3oHSrBMrmgX8JmPVcX1AByfBihgKjchKBp8kKYpSgQAG6MT4pg3STIzdufB9HHBY+2xyMOZD+0LdxRYk5z0MINiZriSELBWqz5OihKMpG6wKR+D4VoP3JiZC+4YvcSgCA3KSFO3LTsvqhHyuJWr5pa+z5Jc6yfgoEjrJ2pBrq5hgfP7THifmintyJGkRfU2Xjn-jX2gN866JyP4Gje0EvJM-70kQ8z4SgvuZa+dEPwc02n4Lmw0tDBU9GhAme1VbflStATgxVSpEHKnZB6IAno1RAFbAw4FoDFHiB3X2sUySd1Tj3OOaRcitynnQ7uCAWEgXrpkVuAg6LFDAD-HBEM6Y4zgRZRkyCEKoMstZVkwDaCU2REYMEedRF+GgUvDMDRXgLFaHHbGuN4K3H2g0bgLBDACRIBIMA3JAqWHrLTDKEUV75WgOgsKFBXEIwWBdfiRAxz6CGk-NQ7RcSlzwfZUaXiQk+I9IyKyVx5GRNMg5LkcYVGFDDONTmOUjG3H5GkbgzpvGCzjNma6Cj-i3xkPIWJxj6ZlOllwKChhcwpAgCQMKI8FaOmengAAVAMiIUQYhxASCDayg9ITjI7nw4kQz75Ch6TQUpE1UEolae0zp3T6nJT6UQgZixdCuSwMuRIkRoixEoUfD+RBI6xGhtYAGQMTRwBgDAIwTpshQAQAYWIfAQJclOBBOgALEDYCOlgZ4rw3oCIMGRbg-1CCD2mAYTgAylnlxydlRpuUooEAqXmKp9oiyEUeuWSsyAaxSDoOhRWTp0KXDRU2TsnAFLHWbK2KsrQBCGFDGlbsqM1JuXVtwFI89pAu0GoOAoRQ3IQLcuuNy843IznQv3OKTBfkkolAy-pIAACingXguxgni-JO09lNOaGKzWrwwS6HQvAAwurR4INClI+mUtmh+IwVgsqbqJSEIWHicsKFwgXNGdciZSd5lEBEday19kUJFEtF6wmdxLlhIoHQflrAcVdBWUZSRys8X4vMrIpJZNrUckcriSCCA+CipQryc15bk34KkEUq0Zq2B5uLoWztcJrU+qQpwLZHSulBrcT+Q5wyt4NyYNmxZ6j4bDrFKO2MzSdCTp2TOqkToFhHJOcUXQANSBRqubMkG3C6CcCwAAWVPZ1IsqdSJZBBk8rI0zijWK5B3GFZ6E6QlKHAbgsQv6CKIIi5F-A4BooTZitdc0N3pkLXErMXAcz5hSXNPAZKFhlgrNWKstL6UHKZWkFlYABIdnZUdJSXK2y8oHahf2Qq0a6FFcQcVkrnZTCYrKueirlwataJwbVw8t36qIca01rqUNbWLQ07127bW8ftTguATqXUuBU-8MeIUsZlvLTa2dHjMEBJKoGvDmaQ24jDaUWxV6xk3LrouzIiaMMMx83gVNRB02mfLf6bN-b81JoM7QaJqnGljqmgkuRNafN1vSQ2qQTab5Gixcsrd3bilwD7a4AdBaLUqbWRW8pLSyLbOnXZ+ysnj0LpTuw1zq76lodWVu-amyatTt2X578StmgntOeewRMQiDoRNq5m9HmwJ0AeWwtOD636zy7mnTqkQil5FKKcmbUgYgH1jbHPWrxVt12zVtqi4q95ZFmG3cehhDAMFblCkGTpsElCUj+7b4q27wpg4YLAOwqIIEjdELAxJeQg-rOBhgGKcsP3qRVzD46cMHpAIR3ExGqU0rpbJqjNG6MMeRsxnlUA+UCo46dbjdr+PSqE+togCrDAIDch2cTWqdX1fwY13E8mBPtvpp13FIX1O0DtRO7TunwP6a3UZxBukYkpfM9FQq-rrPYNwVF-4DnmhOYjdkWb7nN4tZW0jrRg2AtBZV2ZjkYXisRZ86LiYMXUeVfiWcJL8txdKPEBl5tzPLfI8G-l3tinc3O4tSEnmeSIqdtcerkzdvM37T9XFazQSSVOBzbQa+zP55lBzxI0oGaUEEqrTZX3+G0mBnYJktRITNEaJHngQpxTy-2h6xUgQJeakByDo0j38XCXVbaf1zH-ORvDOzTGqhVxf1zeKPG9rQ7yvdY2SCPddWouHoNaN4o5zl3RuX+-fhS3v0vJhm8j5Xznk5D+SSTqQKP2gvBQgSFCcgNwu-kDpFWAKKCG6KyGHWG+g2Pe2GgEmO2OpYlKpG5GhOzKDUJOHKTGLYLGlObGNCnGIq9ORojOJIwm8qiqyqqq6qmqkmPOe+Q2R6AuJqQuIevmeKI+Euasmm0ujqzqcumOiunqwWeKo+GeVmY42uM6eu1Uoa4aLmJ+16pu5+xI3mZmru-wNuJStaiijuUeg6yhNB7uGho+VeySuuii9azQjazaX02kkITBOAKhtA4ehWkeJQ0ejSrurBkBu6fW+6vOX40+tAQyoQnmWQshEAa+ZWKOm+BKvWE+PhNB-hgyxyY2F6JArm8+t6cq9C6ckQ4qRgPyu2ScV+S+8hd6WA-6kaEgsQP+UKoGug4GsQ0GsGgB8GiGD6+oJ2oE28sQZE2cUwRQeQrQnURAMces3AUOnSfArcr0LYOCHUoRRsugy6Hcn25EPRTIoB6+kREBW+UBxKvhhYxYRG8B1KZGBOlGyBrK9GaBng5OrG-K7GlOuB-YPGGsDOgmRBheomXOVB0mg2CRRqDBRWYBWxZmo+UuDqOm3BimNBfBKesWam6e7iGucUAaOC4htA+utAhuMhc+Z+d6ShHaNBahXe9koR4WOhhJW6+hquhhiW1aNecWdeeigeWWd8SmqGNBjhRW2hpWbhseUCCew0SeaCyJJJnuvqSJl0WeEGJe+Mk808NSJe1JghbBpeTIPubq-oZhDeXkTeOSLeuWOU7eJIPaYpaO0oOgvAfe+x1SRog+IJ4unhE63hu+MmByTWIychHRUyosZ+q+GxERhaHhOxXhsRrpfx7puIh+ZyaRfpdyl+yQzy0MxoYId+xID+vy-yL+icIKlRnUEK+R0KLwZ65EjRxYcGqKIBTB7hURQsRKuGNBsBGJxx+OFGc6ROKBbK1xtxWB9xOBtOLxfGBB7xfAxBLOpBKqaq3xUmU+kZzQguQJmxQZtZCw4JMuUJ8ug2sJSCAhjJiJuQyJIhNmaJNp-QmJeA2JkaoR6RcadyBJgZoJIAxJu5amZJTuFJD54uyp9utJ3u9J6JWpaW5hLJVhbathzB4uXJzhJWwJy52x0R2+LpA2j5-xgRuJlCx83AMc1ywOesjUfA4Rbh4Bj5TpO+yF4uqFSR2c6FCQ+gYxmF2FhZeFuYsQ5RnRoYkG2AR8xZNEPkCAdECOWAb8QGN5m8C2AKf2eQD2ZZABQBrRWAAAQivm+h1NpJaCpS2GRNMP9Axc-pDl1J0jmZ+vNtvL3NDglP9AAoPL8ojuyWIg6SqU6RjqeRKE2RSiRicYgecdRp2VcYxjcRgRTlTg8aOQOfgVKiOWOazuzgeNOdQW6XOgsAuYprBSwSubiGuVwXprwR6nCR7uaSKZdKiTrgYQQpIY5tIVeTRVtnMIxZnMxXwPeURVus+ano+W+TyZFlSaWm1Y6TInSdXgBUyelplphafHZRtJyT2k4UMDBUuWlfBXWePrVuRSqahQMrVDDK8NYARQGc1XBSRSGc6WGatYyZRS9h1PAAnNZNfsDLefwiDgJhAAwEQM-iQOEP9BkQto3HdnEFxXGmYrRQnHwCwGAO8p9UnNDoCtgIMSDE7NtWClgAABRxzA5KQKZECtxfWmVfyAr-bWRY33XkSsK9i-J5GCQJRNxVSxB3qE1fJlH1jQogSQi8AjGvZxDA6AqvBchDwg4QZEAACUe1IuxFfVBKUuowaxmO35h1leA1xhpV-uAQUgCN4FBpG0-J8e+kieHMyeO5vVKsBKwh0pwSOSueTw08ECSpPV8J+C+0RhyWKpStBAje2SIuUCbeIAHe6hZtqpKIVpDJX4A+dSB1YtS1oZK1s5iVUZVFsZ8hWE4GDE6cmc0qXc719NtyD1BlO2AOoMEA2kkgmsWAnpYy2d-2D2e2Owt12QCU+ZpoqlCK5Z12qRwKO8i2sQ5lABU8xlXytlqVw+6VGmGsnBkJ2VLl7qvASunittte+5lmxVQ155+IlVcdHRfARYxsB5vyjVatRJYAaaPt9umhoy5JvJn5KpMtYdxM6p-549802peAFhbkZE8cuCXVYe013JLhH566otjlR1ZFUdw2ARsd56oRZ+vIRIJINN7xHNEEbQhgUEbsg8n+ZREgEORN9y3RfI0D2QPdIO1gest0SG1Zf9e5R1zljZhxOOLZpxbZQQHZlxpOnKgVdx1OjxYVmmbxMqnxbObkm4cVvxKFc5tAyVwuv9Dl5D4tHBEJsu0JCuuV+tM9qSc9h5C9d9EwS9l5xu4D8hkD-IMDPkTVItLV+9gWh9P5WaJ975Z9+1j5l9-9ctf5g1GjqW9ej9LJ+j0Du9eWn90FrhJjodjj4dx1kdGj++86z6uQpwAlNEW1Tou1pDkjCJADSFQDdBI2REoN4NZRH1cydyvcE2v8cDVlvNKNmc6NQurcTCSYUOgWdRhgrcRTOCrcmcr0kAO2v1V1AxdAAtfd81A9i1q5HBkt0O0tNt+VauapiSLjJhgF7jDoKtdB79j525yuyjht5kwh6jczZVBqAA6gUJIMbvDU6MY+uh1prahgnu8HHjCJUHcxBf6OPAgLyiHehiYqgi7GkK83FLTvdDqH9NZBmngLmK0Lgs0GaMkAlGbE4PWLmPs4mEBVgJuKuOzCKJUJtHHlUKYC0KTHQCgGgOgMmJ0HgEBgsIsD9tXegDSyAOS7SwDJpusCSxKJBNBEcR5TWHWA2FaLRoFZ2E8QOEOMVBOEYNOHOEuGuFuDuHuIeMeKeBeFeDeHeA+E+K+O+My5UP5jgwKDXFS8mbgLS14wKAy3apq6S3cMERS-q68jS-6Fa6a0yxSCyxMNTINAsGeGeJwAeMuGeHeJuGzB2DOEeJ60ICeJwDOKuJuMuMuJuHeMeJuJuDOJuBUCSzi1UEAA){% endif %} for this project with pre-configured validation and task layout.

    The Toloker won't be able to submit the response until they:

    - Are within 50 meters of the specified location.
    - Select one of the four task completion options.
    - Upload the photos of the product, price tag, and store.

    - Write a comment if the store is closed or missing.

    Learn more about [setting up conditions]({{ tb-conditions }}) in the Template Builder Help.

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
    - `image` — A string with the link to the product photo.
    - `address` — A string with the task address.
    - `product` — A string with the store description.
    - `position` — The coordinates of the point that the Toloker should go to.

    - Output data fields:

    - `address` — A string with the task address.
    - `comment` — A string for the Toloker's comment.
    - `verdict` — The task status.
    - `imgs_item` — Array of files with product photos uploaded by the Toloker.
    - `imgs_price` — Array of files with price tag photos uploaded by the Toloker.
    - `imgs_shelf` — Array of files with photos of the shelf uploaded by the Toloker.
    - `coordinates` — The task coordinates.
    - `imgs_around` — Array of files with photos of the surrounding area uploaded by the Toloker.
    - `imgs_facade` — Array of files with photos of the store uploaded by the Toloker.
    - `imgs_address` — Array of files with photos of the address sign uploaded by the Toloker.
    - `woker_coordinates` — The Toloker's coordinates at the moment of task completion, with the **Current location** option turned on.

    1. The **Settings for displaying field tasks** block is used to help the Toloker distinguish one task from another when they select a task on the map. In this project, the **Header format** and **Short description format** fields contain links to the input data fields to show the point's name and address You can leave these fields unchanged or write something else in them.

    1. Click **Save**.

    #### HTML/CSS/JS editor

    1. The task interface describes how the elements should be arranged in the task.

    In the HTML interface, use the standard HTML tags and [special expressions](t-components.md) in double curly brackets for input and output data fields.

    For this project, leave the **HTML**, **JS**, and **CSS** blocks unchanged.

    **JS** is used to describe the task logic. In addition, the main content of this task is embedded in **JS** for ease of editing.

    The template logic specifies a minimum number of photos of the product, shelf, store's front, and the address sign. if there is no object, of the surrounding area. If you want to change these values, find all strings and change the minimum number of photos for each task completion option:

    ```html
    if (solution.output_values.imgs_item.length < 1)
    if (solution.output_values.imgs_shelf.length < 2)
    if (solution.output_values.imgs_facade.length < 2)
    if (solution.output_values.imgs_around.length < 4)
    ```

    In this project, the `texts` variable stores the texts for the information block and four task completion options: **I found the price tag**; **I found the product, but there is no price tag**; **The product isn't on the shelf**; **Store closed or missing**.

    The `MAX_DISTANCE` variable specifies the maximum distance from the designated point (in kilometers by default) that the Toloker must stay within during task completion. You can specify whatever value you prefer.

    1. Define which objects you are going to pass to the Tolokers and receive from them in response. To do this, add input and output fields in the **Data specification** section.

    #### What are input and output data?

    **Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

    **Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

    Learn more about [input and output data fields](incoming.md).

    In this project:

    - Input data fields:

    - `name` — A string with the store name.
    - `image` — A string with the link to the product photo.
    - `address` — A string with the task address.
    - `product` — A string with the store description.
    - `position` — The coordinates of the point that the Toloker should go to.

    - Output data fields:

    - `address` — A string with the task address.
    - `comment` — A string for the Toloker's comment.
    - `verdict` — The task status.
    - `imgs_item` — Array of files with product photos uploaded by the Toloker.
    - `imgs_price` — Array of files with price tag photos uploaded by the Toloker.
    - `imgs_shelf` — Array of files with photos of the shelf uploaded by the Toloker.
    - `coordinates` — The task coordinates.
    - `imgs_around` — Array of files with photos of the surrounding area uploaded by the Toloker.
    - `imgs_facade` — Array of files with photos of the store uploaded by the Toloker.
    - `imgs_address` — Array of files with photos of the address sign uploaded by the Toloker.
    - `woker_coordinates` — The Toloker's coordinates at the moment of task completion, with the **Current location** option turned on.

    1. Click ![](../_images/tutorials/image-segmentation/preview-button.png) to see the Toloker's view of the task.

    {% note info %}

    The project preview shows one task with standard data. You can define the number of tasks to show on the page later.

    {% endnote %}

    1. To exit preview mode, click **Exit** in the lower-left corner.

    1. Click **Save**.

1. Write short and clear instructions. Describe what needs to be done and give examples.

    You can prepare instructions in HTML format, then copy and paste into the editor. Click **<>** to switch to HTML mode.

    Field task instructions should be easy to read on a mobile phone screen.

1. To go back to the {% if locale == "en-com" %}**Projects**{% endif %} page, click {% if locale == "en-com" %}**Finish editing**{% endif %}.

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

    ![](../_images/tutorials/price-tag/price-tag-input-spreadsheet.png)

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
