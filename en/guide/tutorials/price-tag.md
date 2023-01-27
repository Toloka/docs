# Price monitoring

In this tutorial, you will learn how to run a price monitoring project in Toloka. We will use a project preset designed specifically for this type of data labeling.

Price monitoring is intended for field tasks in the Toloka mobile app. The preset is suitable for collecting information about products from stores and retail outlets. A Toloker chooses a point on the map where they should go to check something and take photos.

Use this preset when you need to:

- Check if prices are up-to-date at specific retail outlets.

- Compare competitors' pricing and stocking policies.

- Monitor promotions and special offers.

- Run out-of-stock (OOS) control.

{% note info %}

You may need additional projects for your task, such as [dataset](https://toloka.ai/datasets) pre-check or checking Tolokers' responses. Learn more about this in [Decomposition of the task](../concepts/solution-architecture.md).

{% endnote %}

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ price-tag-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Select the **Photos of product and price tag** preset.

1. Click **Choose this preset** in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - **Name to show Tolokers**: In 2–5 words, state the general idea of the project.

    - **Description for Tolokers**: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    [![Create a project. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-create-project-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-create-project-step-1.png)

1. In the **Task interface** section, set up what your tasks will look like.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Copy the code of the [example](https://tb.toloka.dev/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4AAoAFhB0EHxYEDBYTIYQACYArmB0WLpQKYmGcGBEWHS6CHgqSgC+vg5O4dIuISBwsBAV5jQ1lTj2dfTMTW5cXj49-iDcugBGRNyaIAAqEgbIwuM4AdZEtq59fk6DCym6pZytTGljnRYgTKfhC1C6Ui4bWFXj3TfKP5sDGlcWncnBScEIKSMHVU31U+yUh0BzW0nFG6z+tCms3mQJAAEEUilDEQ+Hw1qZ3lsgnZ3v9nMdTrpzlBLtc-P97nRHrjdITiaToQ5Pj9YUp4Y4AUNgVwwRCoSAvrUxOKJvTcSi0RSMXgsXMFgBJSRSLCQvhgApMOhwaDkpUI8CBHbBX7stRHXEnM4XK7o114Tnc5pJVIZEzvYUwu29SmShYo2VwSGGQViUXKmNq5Eg3hQADWvv6aUMOOa4TodCYZIA9FWGLoBKdCpwoEQ6FW+ABmKvRbgQXO6KtMKvEgCOaRJkkMVd0ADYZwAWACcACYAAwARgAHLp1x3VykAOwdjsHlIAVgPugPm4Pi4Pq5gJ5nnAAVkxylqDg7trtmgAZVpcxKCB8hDTIsDgKQyjeEUoxdfpM2GHRdEya0oAAWmmK5oigAtbl1EtaAAZXCXRiSwBgICLLBIAgQwwWeSRZE-foUKtaAaQxOl3WaNi0M4PhWzw-p7gYXteU411uKRWgAAE61yIhPHQns+wHT0mV7MBGw4hUuI+OCJQ0ySpMRKUQA0zgqIrH0WL9O4HgWEg6NzIwAH1aPo1pThJFMhXDQz2H0RMdNwvZaTdGStjBdioD0bgcUC-4rBitDmIoBR9OjLLVR42gUokfjRzSOBiRSYT7PCVpnTwABhXgwCArliiw8toGArA+FI8jKOozyGJ85ikvtYzwpyiVELwSzrNZCrTIcrknJc9z+u8pi-NdCMpLTdkVS-SaQHknJIWU1T+yrArYtBfhSigIo5q-Krf1oXrsnI6IQJgMjshIXQGCwGBkmNZqsC00LOAe-pAYgKQTKk3KosOhSTpUiBe3Oyywdijb2R2+zojh+HIvMyzvTZImOUc3FVsY3y9IpvH2TwKDPDYM9VwinAtr8ABdcNFXGPbibjEEEyTHHGaFsyRa4fQjHJ24rGpMb8byvB4DmFJOFanD0MMXlrXQhBkjSJhIf+AiFiIuYiHAkHSj4IDICkJgDFiuJLTQ20IrwCBPegdKsEy+GhfwmY9VxfUAHJ8GKGAqNyEoGnyQpilKBAAbopPimDdJMnN+18H0ccFj7HHI05+D4Z1cPCLwRZk9z0MINiZriSELBWuzlOihKMoW6wKR+D4VoP2GiUi+4EvcSgCA3KSVO3PT8vqnHqv5st3EG5z5I86yfgoCjrJ2pBrq5hgAuJ+L8zZ7ciRpBX1M19D+1N+abfOuicj+Bo3tBLyLOQ9SSj0vhMSe09mi3zoh+Su3MHA82GloYKno0KE32mrb8qVoCcGKqVIg5U7JMxAE9GqIBrYGHAtAYo8Ru5+1imSHuad+7xzSLkDus9GF9wQOwkCTdMgdwEHRYoYA-74IhvTXGiCLKMjQQhDB00rizUIV+AMcYjBgnzhIvwcCn4ZgaK8BYrR44SzglLWMuIGjcBYIYASJAJBgG5IFSw9Y6YZQii-ZK0AsFhQoB4hG5lLr8SIGOfQQ1K50naLiMuyiiGjV8eE-xDIzgzVsmvCUqj1TqMKGGcaHxYFrzwPyNI3BnR+OkuZFEvABCgP+PfGQ8gEnZQphNDBKIoKGFzCkCAJAwppPtErJ0CwABUQyIhRBiHEBIINrIj0hJM7ugjiQjMfkKPpTTmnlJljodpnTum9MaRMAZz08BDMWLoVyWBlyJEiNEWINDT5fyIFHWI0NrAAyBiaOAMAYBGCdNkKACADCxD4CBLkpwIJ0GBYgbAx0sDPFeG9YRBgyLcH+oQEe0wDCcCGSsiuuT1kbOluqbMgEan2iLHXYh5ZKzIBrFIOg6EjkMsuJipsnZODIyUs2VsVZWgCEMKGNK3Y0ZqTchrbgKQl7SFdoNQcBQihuWgW5dcbl5xuRnOhIecUmAArJRKJlCwACingXiuxghsxmroyn2gOuKrWrwwS6HQvAAweqwHINCrIimRLmiBOwbgsqbqJQkIWHicsKFwjXPGXcqZydFlEHEQcrmayJgoSKJaL1RN-Q3MiRQOgArWD4q6Cm-4cT16EvMc0BRNkFYbNoBk5okEEB8DFShXk5q62WvmlIYpVozVsHzSXItXa-DWpaYjNpZFdk9KDflR0xyQAjNCLvZuTAc3LK0UTEdDgx2JOJVwHZXSZ0xOrt+ZWzRTnnOKLoAGpAo23PmSDPhdBOBYAALJXs6kWNOpEsgg1eVkWZxQ7Fcm7vC69idISlDgNwWIP8RFEBRWi-gcBMUJpxZu+G264RJuFvunQOZ8wnvmhShYZYKzVirPSxl87mVpFZWAASHYOXHS5S2NsfLB2oQDsK9GugxXEAlVKl2UwmJysXkq5cmrWicB1WPXDVJBm4mNaa11mHtopt3Zs3EdrOAOrgE6l1LgS1BV4Cg3S8Si3joCV4wq-rgklUDcR09IbcRhtKA4+9Ez7mNxXZkRNVmDIKZAGmogGaVZ1o5DmgdBbcPYf6GWrTe6q2Misoo1JuHKaLVxE2ltdTcWrOCz2kpcB+2uEHYWi1mngsHUnR0o9+zAuKYXUu+VTCM5rvGRug58X0xNcrUhPTU6Guzua6Qy9Fyb0iJiEQdCpsvOPt82BOgzzOHp1fR-Bevd06dUiMUvIpQLnzakDEY+sa4761eBtxuObdtUQlYfLIsxO5T0MIYBgHdYUgydHgkoSlAN7YlZ3JFiHDBYB2FRBAkbohYGJLycH9YYMMGxQV3RRaks+sG4R0bIBSMWOpZR6jTL0IsoakxljilPDco41AflgqeNnX43a4TMqxNbaIIqwwCA3Idmk9q3VzmiEGuUyakTHaGbVf67awT9r8EGedTB4zwXJ4hWxhFyLmPop2bigG-Bs7-iueaO5iN2QFs+Z3qnLhAXIu9ftKF8LlnItRfGTFodNuTNTRkerutmvpHJPS7WitDbxBSGbfPNrqPV5Fd7aVtTebYvDoSXzHKOio-6T8VrtXjus0Dcz0EkJsGyVOFzbQW+7Ol5lCL373Qmb0GI2rUolN-oqbIiyZohJqe8WnqKSU2vNrWkkuqYLiUdTA7B2aRj3PBAQSHr2Tj4XF7Rk5pjbQq4QHFvFHjd14dkuNdT7q9Oxre+F+0Am8UK5nWH3m8-kI1bAH3kw0+d835byciApJJ1UFv6IVQoQDCxO4GiKv8oOqKWA6KqGWKGGPWu+Pu++JKeYOOeOpYBOtKVGDKxOpObKzGnKVO7GvKtOXG9CvGoqzORorOJI4mCqSqKqaqGqWqsmAuHuZ6SmzQKmYukeyaByk+0umsemcuhmiuOOKu5mPi5azSvufqOuDmeCBCJmBu1Uoa4anml+3m52N+xI1unaTB9upSmW9a0W5WCe7uwWiWehvuDeGWgWWWgYIeYeX02kkIHBxa0eJWZW8ebuzStuBK4hcBB6w2c+w+-QJ+JyoyfmWQKh2+VWXBNWA+fh9WARTBwRi6Zyk2t6JAXmK+T6bWXCWAkQEqRg-yB2yc9+6+1+z6WAIGkaEgsQgBsKUGugMGsQCGSGYBKGaGr6+oahz6sQZEOcUwRQeQrQnURAsc+s3AsO3SfAHcr0LY+CHUKhxsuga63cP25EvRTIUBO+0RUusRBGpKgRtwSBtA5GNKdK6BtGJO9GZO7KOB1O+BdO3GtOxB-YAmmsLOomFB5ekmfODB8m-WSRbBZW0B2xe+PBEqfBjqCuamTBwhnq3uFaB0khOC0hTmchxxChbmShkaKhmRS2e8mhUR-WOhfe9kKhrulWWhJhXu2eoJ8iqWKSgePhweeAuWd8RoThnB-WxWfaceJQRhnhSesCEU26GemC2uJJyWc6uQ2unADmoSVeBMM8c8+WBxtAphRa5h9JAebqze2WreXk7euSneae3eJIvaEp2mWYXAVSjJX4o+DS6OMRE6M+-hx6iRtGwyS+0aG+cQa+iY1CahW+mxhJGy3BuxQ28RbpwWSRZ+lyGRPp8ad+yQby0MxoYIz+xIr+AKQKn+Sc4K1RnU0KhRcKLw165EzRxYyGGKkBThXhYhp6tW8BRGTBRxeAJxhO5xP4dGDG5OtxeBnGAqjxfAzxTOMu7xsqXxXOyqqq6qPxcm8+HpIuqm4uW6MBCJGCum+mAh0JyuHqWe9ZOeiJtmV0uushZhxCGJRuWJ8Z1+8aBJnh2hYA6auhVh+hLuhhHhIZsB6pTueGKW-uNa+u9aLethLa9h7aHJQWXJMebhfJn5q5IJsBjZcRh+C5XZnpYyV+CQZ83AscdyYO+sjUfAkRD5iF65zpKFI2qp+qi5F6KROcy+8y+g4xOFeFxZhFuYsQlRoEe8cG2Ap8pZNEPkCAdEyOWAH84GuJO8y2wKgOeQz2FZoB4B7RWAAAQpvt+h1NpJaJpS2GRNMP9KxR-jDl1N0nmX+nic3D-HDglP9EAiPACijupptGuT4chXsQgdRRMK2VShRqgUThcZgYxjcaxrgTygOfTk8Yzq8UJmQR8cOZOdzgeHOYwdGbRbQICWpsCY6TsYjJufwVCUrv1rCfuUlpaVKd4siWODIUBW2ZebQMbsoYxTQkZfhbDihJxfeRLsFsSfCUyQYe4RSV+RWj+U7pqQBY3uecyS0KHi2jhRfM5Rpi4TyUMBVtlaGU6RUi6ZGUfrATGUMrVDDK8NYMRcGaRTlbSRRdsq6btRWjGYsO9h1PAInNZA-sDHGo8uDiJhAAwEQB-iQOEP9Fkcti3I9nEPxXGpYgkLCnwCwGAF8kDcnHDiCtgEMSDM7MdZClgAABTxxg5KTLkdzA17wDwgpA7WRE0fVCJwogS9gAoFGCQJStxVSxDPqU2-IVH1g00mhzDghGAfZxBg4gqvBcijzg6wZEAACUZ13VF1SFG5MuqI-26xOOo1l1JMWpgFXl6SIFAQUgmNkFxp2igpKewpw0opkhFpf5FVMpcpheqpxeTwc80CVeath5dJE1lhQeutBAbeOSDM+SlchSZpvefVdeW11pN0Ve9prg4+FMYZV1EZqF2tUp56p+9FN5ahWEMGDEGcWcMqvcANHNDy1Npl+2wOoMEA2kkgWsWAmFEyZdQOz2h2Owb12QCUhZpoWlyKlZd26RYK+8K2sQNloBs8FlvyTl61E+m1Cw+VkJRmQhe5qCYd7tiMSJp5tVF5C6jV2JzVgZRYJs0pAKfAXVCFRJT5YWL5v52a75g1cWTBbt5FGtnttpOe01rJZECcBC99y1seq1-JstG1uVEd11O1aFadJyGdN6KhPpvIRIJIrNHxgtEEbQhgUE7sI8f+FREg0OVNxIq2cD-IPR494O1g+sd06GtZrl3qvhHlzZwWPl7Z-lnZQQlxPZIVlOdxEVQ5I5MVkqcVE5bWnO3Om4KVfxx+6VeAmVK5WG1Dq95kc98uC9KdSCZmcJNJ8ta9x5RUKJeuKd8h29150Dt21+hDCDiQHxp9sjPVF9DuB5p6ZJH5Q151e+j9blHtTIDJm979s1bkZjAoi1Llv9sFa1WxctT9WySdVF7p6FuIIyH6uQpwolNER1Top1VDZF7jids+UZ-xkji6REcNCNFRgNCyn18GoiACYO9lYtuNWcBNYuHcrCSYsOYWDRhgHc02-8HcWcr0kA+2YNz1gxdAktk9YTQD6ts9itowKtKj1eVttwB0Fhr9DjPtGNSmP9xVS9Fm9j80R50pJ5ujZ5r5dVC6AA6gUJIKbus9YFY9tD1ibVhsKe8MnjCJUK81BRyFPAgHyg6X1osxgq7GkD83FIznNDXL1Fff0LmK0AQs0GaMkAlJDE4PWLmGc4mHqVgJuKuBzCKJUFtMnlUKYC0CyFcCgGgOgMmJ0HgOBgsIsP9m3egEyyALS8ywDDLusFSyPlBAgOZEwzWHWA2FaIxngZ2COYOMOA5hOEYNOHOEuGuFuDuHuIeMeKeBeFeDeHeA+E+K+O+Jy5UHgP44HPXAy6mbgMy0a0y3gOy5rPq9S3cGEXS6ax8law68tq6zaxKnazRXRANOtLiGeGeJwAeMuGeHeJuOzB2DOEeIG0ICeJwDOKuJuMuMuJuHeMeJuJuDOJuBUFS0S1UEAA&locale=en) and paste it to the **Config** section of your project. This code has validation and task layout pre-configured.

        [![Create a project. Config section](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-config-section.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-config-section.png)

    1. You can edit the code. For example, to change the description, replace the sample text with your value in the `content` property.

        [![Create a project. Config text](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-config-text.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-config-text.png)

    1. A Toloker will be able to submit a response when they are within 50 meters of the specified location. To change this condition, replace the value of the `max` property with the desired distance:

        [![Create a project. Config distance](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-config-distance.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-config-distance.png)

        {% note info %}

        To learn about other properties of the **Config** section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/reference/index.md).

        {% endnote %}

    1. {% include [toloka-requester-source-specification-definition](../_includes/toloka-requester-source/id-toloka-requester-source/specification-definition.md) %}

        {% include [toloka-requester-source-click-show-specifications](../_includes/toloka-requester-source/id-toloka-requester-source/click-show-specifications.md) %}

        - **Input data**: Parameters in the file with raw task data.

        - **Output data**: Parameters in the file with labeling results.

        {% include [toloka-requester-source-specification-match](../_includes/toloka-requester-source/id-toloka-requester-source/specification-match.md) %}

    1. In the **Settings for displaying field tasks** section, configure the settings which affect the task display on the map.

        - The **Title format** and **Short description format** are used to help a Toloker distinguish one task from another when they select a task on the map. These fields contain links to the input data fields to show the name of the point and its coordinates. You can leave these fields unchanged.

        - The **Map provider for tasks** field sets which map a Toloker will use when performing your tasks.

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

    Field task instructions should be easy to read on a mobile phone screen.

    {% include [toloka-requester-source-instruction-note](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-note.md) %}

1. To save your data and continue, click **Create a project**.

    {% include [tutorials-create-project-image](../_includes/tutorials/create-project-image.md) %}

## Create a pool {#pool}

{% include [toloka-requester-source-what-is-pool](../_includes/toloka-requester-source/id-toloka-requester-source/what-is-pool.md) %}

1. Click **Add a pool** on the project page.

1. {% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

1. {% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

1. Click **Create**.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. Clear **My tasks may contain shocking or pornographic content** if your project has none of those.

    1. {% include [toloka-requester-source-filters](../_includes/toloka-requester-source/id-toloka-requester-source/filters.md) %}

        [![Create a pool. Languages filter](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-language-filter.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-language-filter.png)

    1. Tasks in pools are available in the web version of Toloka and the mobile app by default. Make your tasks available in the mobile app only: add the **Client** filter and select the **Toloka for mobile** option.

    1. Use the **Speed/quality balance** slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. {% include [tutorials-quality-control](../_includes/tutorials/quality-control.md) %}

    1. Click the **Review task responses manually** toggle, and specify the number of days for checking the task in the **Review period in days** field (for example, 21).

        {% include [tutorials-na-acceptance](../_includes/tutorials/na-acceptance.md) %}

    1. Click **Add a quality control rule → Results of assignment review**, and enter the following values:

        [![Create a pool. Results of assignment review rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-results-rule.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-results-rule.png)

        This means that if more than 35% of a Toloker's responses are rejected, the Toloker is banned and can't access your tasks for 15 days. The rule takes effect after 3 responses of the Toloker are reviewed.

    1. Add the **Processing rejected and accepted assignments** rule.

        [![Create a pool. Processing rejected and accepted assignments rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-rejected.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-rejected.png)

        This means that if you reject assignments during the review, they’ll be sent for re-completion to another Toloker.

1. {% include [tutorials-time-per-task-suite](../_includes/tutorials/time-per-task-suite.md) %}

    It should be long enough to get to the place, find the specified point and product, and upload the photos. For field tasks, this time is usually 86,400 seconds (24 hours).

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In **Price per task suite**, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks.

        For this type of project, a task suite must contain only one task. You will set the number of tasks per suite later in this tutorial.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        For field tasks, it is usually 1. This means that each task will have 1 response.

1. {% include [tutorials-upload-tasks](../_includes/tutorials/upload-tasks.md) %}

    1. Create the tasks for Tolokers:

        1. To download a template, click one of the buttons:

            - **Template in XLSX**

            - **Template in TSV**

            - **Template in JSON**

            For this type of project, the file with tasks must contain seven parameters:

            - `INPUT:name`: A string with the store name.

            - `INPUT:image`: A string with the link to the product photo.

            - `INPUT:address`: A string with the store address.

            - `INPUT:product`: A string with the product name.

            - `INPUT:coordinates`: A string with the coordinates of the point that the Toloker should go to.

            - `AI:latitude`, `AI:longitude`: The latitude and longitude from the `INPUT:coordinates` parameter presented separately. The values of `INPUT:coordinates`, `AI:latitude` and `AI:longitude` should have the same accuracy, that is have the same number of digits after the decimal separator.

            ```json
            INPUT:name	INPUT:image	INPUT:address	INPUT:product	INPUT:coordinates	AI:latitude	AI:longitude
            Store-name-1	https://yastatic.net/s3/toloka/p/toloka-requester-page-project-preview/877a55555a5f199dff16.jpg	Address-1	Product-1	53.947516,27.669428	53.947516	27.669428
            Store-name-2	https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/048e5760fc5a46faa434922b2447a527.jpg	Address-2	Product-2	53.947517,27.669429	53.947517	27.669429
            Store-name-3	https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/05334365c060421ab25264166bbb4fd1.jpg	Address-3	Product-3	53.947518,27.669428	53.947518	27.669428
            ```

        1. Open the downloaded file, and replace the sample values with your data. You can use a service like Google Maps to get the coordinates.

        1. Click **Drop file here or select**, and upload the file you’ve just made.

        1. Click **Continue**.

    1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

        1. Go to the **Set manually** tab.

        1. In this type of project, the task suite must contain only one task:

            [![Upload data. Tasks in suite](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-number-tasks.png =570x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-number-tasks.png)

    1. Click **Combine tasks into suites**.

1. {% include [tutorials-upload-tasks](../_includes/tutorials/double-check.md) %}

    {% include [toloka-requester-source-step-enabled](../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

{% include [toloka-requester-source-pool-is-ready](../_includes/toloka-requester-source/id-toloka-requester-source/pool-is-ready.md) %}

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    [![Start labeling](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-start-labeling-step-2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-start-labeling-step-2.png)

1. In the pop-up panel, review the budget and click **Launch**.

## See the results {#results}

Track the labeling progress on the pool page. You can start the review when the first results are received.

After the time period specified in step 4.1 of [creating the pool](#pool), all responses are automatically accepted, regardless of their quality.

1. Go to the pool, and click **Review assignments**.

    [![See the results. Review assignments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-review-results.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-review-results.png)

1. Choose an assignment.

1. Check the responses, and click **Accept** or **Decline**. For rejected responses, enter a comment to specify the reason.

    {% note info %}

    To learn about other ways of review, see the [Reviewing Tolokers' responses](../concepts/accept.md) section.

    {% endnote %}

1. After checking all the assignments, click **Download results**.

    [![See the results. Download results](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-results-download.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-results-download.png)

    You will get the TSV file with the labeling results.

1. To download the files Tolokers attached to the tasks, click the arrow next to the **Download results** button. Choose **Download attachments** from the drop-down menu.

    [![See the results. Download attachments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-results-download-attachments.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/price-tag/price-tag-results-download-attachments.png)

## Troubleshooting {#troubleshooting}

{% cut "Can I limit the source of the photo to camera-only in a field task so that the Toloker can't upload a photo from anywhere else?" %}

The `accept` property of the `field.media-file` component adds different buttons for four types of uploads. To prohibit using any sources except of the camera, use the `"photo": true` property only, like it is done in the [example](https://tb.toloka.dev/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4AAoAFhB0EHxYEDBYTIYQACYArmB0WLpQKYmGcGBEWHS6CHgqSgC+vg5O4dIuISBwsBAV5jQ1lTj2dfTMTW5cXj49-iDcugBGRNyaIAAqEgbIwuM4AdZEtq59fk6DCym6pZytTGljnRYgTKfhC1C6Ui4bWFXj3TfKP5sDGlcWncnBScEIKSMHVU31U+yUh0BzW0nFG6z+tCms3mQJAAEEUilDEQ+Hw1qZ3lsgnZ3v9nMdTrpzlBLtc-P97nRHrjdITiaToQ5Pj9YUp4Y4AUNgVwwRCoSAvrUxOKJvTcSi0RSMXgsXMFgBJSRSLCQvhgApMOhwaDkpUI8CBHbBX7stRHXEnM4XK7o114Tnc5pJVIZEzvYUwu29SmShYo2VwSGGQViUXKmNq5Eg3hQADWvv6aUMOOa4TodCYZIA9FWGLoBKdCpwoEQ6FW+ABmKvRbgQXO6KtMKvEgCOaRJkkMVd0ADYZwAWACcACYAAwARgAHLp1x3VykAOwdjsHlIAVgPugPm4Pi4Pq5gJ5nnAAVkxylqDg7trtmgAZVpcxKCB8hDTIsDgKQyjeEUoxdfpM2GHRdEya0oAAWmmK5oigAtbl1EtaAAZXCXRiSwBgICLLBIAgQwwWeSRZE-foUKtaAaQxOl3WaNi0M4PhWzw-p7gYXteU411uKRWgAAE61yIhPHQns+wHT0mV7MBGw4hUuI+OCJQ0ySpMRKUQA0zgqIrH0WL9O4HgWEg6NzIwAH1aPo1pThJFMhXDQz2H0RMdNwvZaTdGStjBdioD0bgcUC-4rBitDmIoBR9OjLLVR42gUokfjRzSOBiRSYT7PCVpnTwABhXgwCArliiw8toGArA+FI8jKOozyGJ85ikvtYzwpyiVELwSzrNZCrTIcrknJc9z+u8pi-NdCMpLTdkVS-SaQHknJIWU1T+yrArYtBfhSigIo5q-Krf1oXrsnI6IQJgMjshIXQGCwGBkmNZqsC00LOAe-pAYgKQTKk3KosOhSTpUiBe3Oyywdijb2R2+zojh+HIvMyzvTZImOUc3FVsY3y9IpvH2TwKDPDYM9VwinAtr8ABdcNFXGPbibjEEEyTHHGaFsyRa4fQjHJ24rGpMb8byvB4DmFJOFanD0MMXlrXQhBkjSJhIf+AiFiIuYiHAkHSj4IDICkJgDFiuJLTQ20IrwCBPegdKsEy+GhfwmY9VxfUAHJ8GKGAqNyEoGnyQpilKBAAbopPimDdJMnN+18H0ccFj7HHI05+D4Z1cPCLwRZk9z0MINiZriSELBWuzlOihKMoW6wKR+D4VoP2GiUi+4EvcSgCA3KSVO3PT8vqnHqv5st3EG5z5I86yfgoCjrJ2pBrq5hgAuJ+L8zZ7ciRpBX1M19D+1N+abfOuicj+Bo3tBLyLOQ9SSj0vhMSe09mi3zoh+Su3MHA82GloYKno0KE32mrb8qVoCcGKqVIg5U7JMxAE9GqIBrYGHAtAYo8Ru5+1imSHuad+7xzSLkDus9GF9wQOwkCTdMgdwEHRYoYA-74IhvTXGiCLKMjQQhDB00rizUIV+AMcYjBgnzhIvwcCn4ZgaK8BYrR44SzglLWMuIGjcBYIYASJAJBgG5IFSw9Y6YZQii-ZK0AsFhQoB4hG5lLr8SIGOfQQ1K50naLiMuyiiGjV8eE-xDIzgzVsmvCUqj1TqMKGGcaHxYFrzwPyNI3BnR+OkuZFEvABCgP+PfGQ8gEnZQphNDBKIoKGFzCkCAJAwppPtErJ0CwABUQyIhRBiHEBIINrIj0hJM7ugjiQjMfkKPpTTmnlJljodpnTum9MaRMAZz08BDMWLoVyWBlyJEiNEWINDT5fyIFHWI0NrAAyBiaOAMAYBGCdNkKACADCxD4CBLkpwIJ0GBYgbAx0sDPFeG9YRBgyLcH+oQEe0wDCcCGSsiuuT1kbOluqbMgEan2iLHXYh5ZKzIBrFIOg6EjkMsuJipsnZODIyUs2VsVZWgCEMKGNK3Y0ZqTchrbgKQl7SFdoNQcBQihuWgW5dcbl5xuRnOhIecUmAArJRKJlCwACingXiuxghsxmroyn2gOuKrWrwwS6HQvAAweqwHINCrIimRLmiBOwbgsqbqJQkIWHicsKFwjXPGXcqZydFlEHEQcrmayJgoSKJaL1RN-Q3MiRQOgArWD4q6Cm-4cT16EvMc0BRNkFYbNoBk5okEEB8DFShXk5q62WvmlIYpVozVsHzSXItXa-DWpaYjNpZFdk9KDflR0xyQAjNCLvZuTAc3LK0UTEdDgx2JOJVwHZXSZ0xOrt+ZWzRTnnOKLoAGpAo23PmSDPhdBOBYAALJXs6kWNOpEsgg1eVkWZxQ7Fcm7vC69idISlDgNwWIP8RFEBRWi-gcBMUJpxZu+G264RJuFvunQOZ8wnvmhShYZYKzVirPSxl87mVpFZWAASHYOXHS5S2NsfLB2oQDsK9GugxXEAlVKl2UwmJysXkq5cmrWicB1WPXDVJBm4mNaa11mHtopt3Zs3EdrOAOrgE6l1LgS1BV4Cg3S8Si3joCV4wq-rgklUDcR09IbcRhtKA4+9Ez7mNxXZkRNVmDIKZAGmogGaVZ1o5DmgdBbcPYf6GWrTe6q2Misoo1JuHKaLVxE2ltdTcWrOCz2kpcB+2uEHYWi1mngsHUnR0o9+zAuKYXUu+VTCM5rvGRug58X0xNcrUhPTU6Guzua6Qy9Fyb0iJiEQdCpsvOPt82BOgzzOHp1fR-Bevd06dUiMUvIpQLnzakDEY+sa4761eBtxuObdtUQlYfLIsxO5T0MIYBgHdYUgydHgkoSlAN7YlZ3JFiHDBYB2FRBAkbohYGJLycH9YYMMGxQV3RRaks+sG4R0bIBSMWOpZR6jTL0IsoakxljilPDco41AflgqeNnX43a4TMqxNbaIIqwwCA3Idmk9q3VzmiEGuUyakTHaGbVf67awT9r8EGedTB4zwXJ4hWxhFyLmPop2bigG-Bs7-iueaO5iN2QFs+Z3qnLhAXIu9ftKF8LlnItRfGTFodNuTNTRkerutmvpHJPS7WitDbxBSGbfPNrqPV5Fd7aVtTebYvDoSXzHKOio-6T8VrtXjus0Dcz0EkJsGyVOFzbQW+7Ol5lCL373Qmb0GI2rUolN-oqbIiyZohJqe8WnqKSU2vNrWkkuqYLiUdTA7B2aRj3PBAQSHr2Tj4XF7Rk5pjbQq4QHFvFHjd14dkuNdT7q9Oxre+F+0Am8UK5nWH3m8-kI1bAH3kw0+d835byciApJJ1UFv6IVQoQDCxO4GiKv8oOqKWA6KqGWKGGPWu+Pu++JKeYOOeOpYBOtKVGDKxOpObKzGnKVO7GvKtOXG9CvGoqzORorOJI4mCqSqKqaqGqWqsmAuHuZ6SmzQKmYukeyaByk+0umsemcuhmiuOOKu5mPi5azSvufqOuDmeCBCJmBu1Uoa4anml+3m52N+xI1unaTB9upSmW9a0W5WCe7uwWiWehvuDeGWgWWWgYIeYeX02kkIHBxa0eJWZW8ebuzStuBK4hcBB6w2c+w+-QJ+JyoyfmWQKh2+VWXBNWA+fh9WARTBwRi6Zyk2t6JAXmK+T6bWXCWAkQEqRg-yB2yc9+6+1+z6WAIGkaEgsQgBsKUGugMGsQCGSGYBKGaGr6+oahz6sQZEOcUwRQeQrQnURAsc+s3AsO3SfAHcr0LY+CHUKhxsuga63cP25EvRTIUBO+0RUusRBGpKgRtwSBtA5GNKdK6BtGJO9GZO7KOB1O+BdO3GtOxB-YAmmsLOomFB5ekmfODB8m-WSRbBZW0B2xe+PBEqfBjqCuamTBwhnq3uFaB0khOC0hTmchxxChbmShkaKhmRS2e8mhUR-WOhfe9kKhrulWWhJhXu2eoJ8iqWKSgePhweeAuWd8RoThnB-WxWfaceJQRhnhSesCEU26GemC2uJJyWc6uQ2unADmoSVeBMM8c8+WBxtAphRa5h9JAebqze2WreXk7euSneae3eJIvaEp2mWYXAVSjJX4o+DS6OMRE6M+-hx6iRtGwyS+0aG+cQa+iY1CahW+mxhJGy3BuxQ28RbpwWSRZ+lyGRPp8ad+yQby0MxoYIz+xIr+AKQKn+Sc4K1RnU0KhRcKLw165EzRxYyGGKkBThXhYhp6tW8BRGTBRxeAJxhO5xP4dGDG5OtxeBnGAqjxfAzxTOMu7xsqXxXOyqqq6qPxcm8+HpIuqm4uW6MBCJGCum+mAh0JyuHqWe9ZOeiJtmV0uushZhxCGJRuWJ8Z1+8aBJnh2hYA6auhVh+hLuhhHhIZsB6pTueGKW-uNa+u9aLethLa9h7aHJQWXJMebhfJn5q5IJsBjZcRh+C5XZnpYyV+CQZ83AscdyYO+sjUfAkRD5iF65zpKFI2qp+qi5F6KROcy+8y+g4xOFeFxZhFuYsQlRoEe8cG2Ap8pZNEPkCAdEyOWAH84GuJO8y2wKgOeQz2FZoB4B7RWAAAQpvt+h1NpJaJpS2GRNMP9KxR-jDl1N0nmX+nic3D-HDglP9EAiPACijupptGuT4chXsQgdRRMK2VShRqgUThcZgYxjcaxrgTygOfTk8Yzq8UJmQR8cOZOdzgeHOYwdGbRbQICWpsCY6TsYjJufwVCUrv1rCfuUlpaVKd4siWODIUBW2ZebQMbsoYxTQkZfhbDihJxfeRLsFsSfCUyQYe4RSV+RWj+U7pqQBY3uecyS0KHi2jhRfM5Rpi4TyUMBVtlaGU6RUi6ZGUfrATGUMrVDDK8NYMRcGaRTlbSRRdsq6btRWjGYsO9h1PAInNZA-sDHGo8uDiJhAAwEQB-iQOEP9Fkcti3I9nEPxXGpYgkLCnwCwGAF8kDcnHDiCtgEMSDM7MdZClgAABTxxg5KTLkdzA17wDwgpA7WRE0fVCJwogS9gAoFGCQJStxVSxDPqU2-IVH1g00mhzDghGAfZxBg4gqvBcijzg6wZEAACUZ13VF1SFG5MuqI-26xOOo1l1JMWpgFXl6SIFAQUgmNkFxp2igpKewpw0opkhFpf5FVMpcpheqpxeTwc80CVeath5dJE1lhQeutBAbeOSDM+SlchSZpvefVdeW11pN0Ve9prg4+FMYZV1EZqF2tUp56p+9FN5ahWEMGDEGcWcMqvcANHNDy1Npl+2wOoMEA2kkgWsWAmFEyZdQOz2h2Owb12QCUhZpoWlyKlZd26RYK+8K2sQNloBs8FlvyTl61E+m1Cw+VkJRmQhe5qCYd7tiMSJp5tVF5C6jV2JzVgZRYJs0pAKfAXVCFRJT5YWL5v52a75g1cWTBbt5FGtnttpOe01rJZECcBC99y1seq1-JstG1uVEd11O1aFadJyGdN6KhPpvIRIJIrNHxgtEEbQhgUE7sI8f+FREg0OVNxIq2cD-IPR494O1g+sd06GtZrl3qvhHlzZwWPl7Z-lnZQQlxPZIVlOdxEVQ5I5MVkqcVE5bWnO3Om4KVfxx+6VeAmVK5WG1Dq95kc98uC9KdSCZmcJNJ8ta9x5RUKJeuKd8h29150Dt21+hDCDiQHxp9sjPVF9DuB5p6ZJH5Q151e+j9blHtTIDJm979s1bkZjAoi1Llv9sFa1WxctT9WySdVF7p6FuIIyH6uQpwolNER1Top1VDZF7jids+UZ-xkji6REcNCNFRgNCyn18GoiACYO9lYtuNWcBNYuHcrCSYsOYWDRhgHc02-8HcWcr0kA+2YNz1gxdAktk9YTQD6ts9itowKtKj1eVttwB0Fhr9DjPtGNSmP9xVS9Fm9j80R50pJ5ujZ5r5dVC6AA6gUJIKbus9YFY9tD1ibVhsKe8MnjCJUK81BRyFPAgHyg6X1osxgq7GkD83FIznNDXL1Fff0LmK0AQs0GaMkAlJDE4PWLmGc4mHqVgJuKuBzCKJUFtMnlUKYC0CyFcCgGgOgMmJ0HgOBgsIsP9m3egEyyALS8ywDDLusFSyPlBAgOZEwzWHWA2FaIxngZ2COYOMOA5hOEYNOHOEuGuFuDuHuIeMeKeBeFeDeHeA+E+K+O+Jy5UHgP44HPXAy6mbgMy0a0y3gOy5rPq9S3cGEXS6ax8law68tq6zaxKnazRXRANOtLiGeGeJwAeMuGeHeJuOzB2DOEeIG0ICeJwDOKuJuMuMuJuHeMeJuJuDOJuBUFS0S1UEAA&locale=en).

If you allow Tolokers to use the mobile device gallery, you can prohibit adding images without geotags to limit uploading photos taken from the Internet. To do that, specify the `"requiredCoordinates": true` property.

To learn more about setting up the `field.media-file` component, see the [Template Builder Help](../../template-builder/reference/field.media-file.md).

{% endcut %}

{% cut "How do I check the task display in the mobile Toloka app?" %}

To check the task's look-and-feel on the mobile phone screen, you can use the following buttons:

- **Preview task** on the project settings page.
- **Preview** on the pool settings page.

You can also use the mobile version of the sandbox. [Write to support](../troubleshooting/support.md#support-work-toloka) to get access to it.

{% endcut %}

## See also {#see-also}

- [Crowdsourcing concepts: Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Crowdsourcing concepts: Pricing](https://toloka.ai/knowledgebase/pricing/)

## For developers {#for-developers}

- [Toloka-Kit: Spatial crowdsourcing example](https://github.com/Toloka/toloka-kit/blob/main/examples/2.spatial_crowdsourcing/0.simplest_example/spatial_crowdsourcing.ipynb)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles.md) %}