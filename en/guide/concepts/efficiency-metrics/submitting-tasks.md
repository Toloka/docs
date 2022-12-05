# Submission rate

This indicator shows the percentage of successfully submitted tasks and helps identify issues related to incorrect settings:

- The indicator does not show any value. Perhaps the set criteria for selecting Tolokers are too strict and your tasks are not available to them.

- A low percentage of submitted tasks indicates problems with the settings of individual fields.

- The percentage of submitting tasks is zero. In this case, check whether the field names specified in the task interface are correct.

#### How to calculate

$P_{subm} = \frac{T_{subm}+T_{accept}+T_{reject}}{T_{subm}+T_{accept}+T_{reject}+T_{expire}+T_{skip}}\times100$

where:

- $P_{subm}$ is the percentage of submitted tasks.

- $T_{subm}$ is the number of submitted tasks.

- $T_{accept}$ is the number of accepted tasks.

- $T_{reject}$ is the number of rejected tasks.

- $T_{expire}$ is the number of tasks that were not submitted within the allowed time.

- $T_{skip}$ is the number of skipped tasks.

#### How to estimate

- A good indicator is `> 90%`.

- A low indicator is `< 90%`.

{% include [contact-support](../../_includes/contact-support.md) %}