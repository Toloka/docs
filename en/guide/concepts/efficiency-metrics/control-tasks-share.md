# Control tasks

This indicator shows the average ratio of control tasks to other tasks within per [task suites](../../../glossary.md#task-suite). A large percentage of control tasks lets you improve the quality but, at the same time, it may make labeling more expensive.

#### How to calculate

$P_{control} = \frac{T_{control}}{T_{total}}\times100$

where:

- $P_{control}$ is the percentage of control tasks.

- $T_{control}$ is the number of control tasks.

- $T_{total}$ is the total number of tasks.

The indicator estimation criteria depends on the pool type.

{% list tabs %}

- Pool with general tasks

    - A good indicator is `30%`.

    - A low indicator is `< 30%`.

- Exam pools

    - A good indicator is `100%`.

    - A low indicator is `> 90%`.

{% endlist %}

{% include [contact-support](../../_includes/contact-support-help.md) %}