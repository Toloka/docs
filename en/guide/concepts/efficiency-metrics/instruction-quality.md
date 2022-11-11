# Quality of instructions

After completing a task, Tolokers rate different aspects of it. In particular, they indicate whether the instructions were clear to them. Based on these ratings, an instruction quality indicator is generated.

{% note info %}

If no Toloker has yet given a rating, the indicator value will be missing.

{% endnote %}

#### How to calculate

$Q_{i} = {H_{i}}\times{CSI}$

where:

- $Q_{i}$ is the instruction quality indicator.

- $H_{i}$ is the availability of instructions (0 means available and 1 means not available).

- $CSI$ is the Tolokers' rating, which shows how satisfied they are with the instructions.

#### How to estimate

- A good indicator is `> 4.5`.

- A low indicator is `< 4.5` or missing.

{% include [contact-support](../../_includes/contact-support-help.md) %}