# AB Experiments in Toloka

A\/B experiments are used:

* To find out how changes in the instructions\/training/interface affect the responces of Tolokers.

* Assess the markup quality. If your pool is small, it's hard to track how Toloker's markup quality changes over time (for example, if the Toloker passed the exam but then for some reason his performance got worse). The experiments allow you to filter out such Tolokers even if your pool has few tasks.

## How it works {#ab-how-it-works}

* Each Toloker has an id number ranging from 1 to 100 (100 independent groups of Tolokers). Parameter is set to a Toloker like a skill and Tolokers will always be placed into the the same group.
* Use the **AB experiment** filter in pool settings to select Tolokers from one or several groups with the specified numbers.
* You can use these filters to launch pools\/projects with different settings on independent groups of performers.
* In order to create an AB test you have to create 2 projects with 2 pools.

## Troubleshooting {#troubleshooting}

{% cut "Can I select two filters at once?" %}

Yes. For example, if you set the ID value = 1 \+ English language, you will get all the Tolokers with id = 1 who speak English.

{% endcut %}

{% cut "Can I do the experiments within one project?" %}

To do A\/B experiments within one peoject, it must have at least 2 pools.

{% endcut %}

{% cut "Can part of the Tolokers perform tasks from both pools?" %}

{% note alert %}

If you set the **AB experiment** filter = 1 in one pool and **AB experiment** filter = 2 in another pool, then \~98% of the Tolokers will not see your tasks.

{% endnote %}

There might be an overlap if you, for example, select more than 50 Tolokers for each pool. 

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}
