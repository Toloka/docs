# Submission rate

This metric shows the percentage of successfully submitted tasks and helps identify issues related to incorrect settings:

- The metric does not show any value. Perhaps the set criteria for selecting Tolokers are too strict and your tasks are not available to them.
- A low percentage of submitted tasks indicates problems with the settings of individual fields.
- The percentage of submitting tasks is zero. In this case, check whether the field names specified in the task interface are correct.

#### How to calculate

$P_{subm} = \frac{T_{subm}+T_{accept}+T_{reject}}{T_{subm}+T_{accept}+T_{reject}+T_{expire}+T_{skip}}\times100$
where:








#### How to estimate

- A good indicator is `> 90%`.
- A low indicator is `< 90%`.

{% include [contact-support](../../_includes/contact-support-help.md) %}