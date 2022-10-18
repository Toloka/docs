# Protect your data

We make every effort to ensure the security of your data, but sometimes tasks are completed by cheaters. If your data is confidential, take additional measures to protect it.

## Protect your data from cheaters {#protect-from-them}

- [Decompose tasks](solution-architecture.md#ul_aqh_tbb_xlb). You can break your tasks down into several projects (steps). Each step contains only part of the data, and a malicious user won't be able to put the pieces together.
- If you use [input](../../glossary.md#input-output-data) fields to transmit data that Tolokers shouldn't see, make the fields with this data hidden. For instance, do this if you moderate comments and you need the authors' personal data in the results for further data processing.
- Use any name or pseudonym to identify yourself for the Tolokers — you don't have to disclose your company name. This is useful for requesters who don't want to attract unnecessary interest from Tolokers.
- You can use the [Completed tasks](submitted-answers.md#rule) quality control rule to limit the number of task suites each Toloker can complete. This lets you better protect your data from fraud and minimize your risks (scattered data has no commercial value).

## Store data on your own server {#keep-it-save}

Set up the process to avoid storing data on Yandex servers. To do this:
1. When uploading tasks to the pool, use IDs in the input data rather than content itself.
1. Set up a server to return the task content based on IDs.
1. In the task interface, add code that sends IDs to the server and displays the content received.

For instance, you can store text comments on your server and use the file with tasks to pass only the comment IDs. As a result, only the ID+result pairs are saved in the Toloka database, but these pairs don't have any commercial value in the absence of input data.

## Get more features on request {#help-by-request}

- We are always happy to sign an NDA (Non-Disclosure Agreement) with requesters. If that's critical for your company, please contact us at [customercare@toloka.ai](mailto:customercare@toloka.ai)

- You can send requests from Toloka tasks to your server. To get assistance in setting up the process, contact us at [customercare@toloka.ai](mailto:customercare@toloka.ai).

    This is useful if:
    - You need images or other files for your tasks, and you want to store them on your own server.
    - You need to load dynamic data in the tasks.
    - You want to log user actions.

{% include [contact-support](../_includes/contact-support-help.md) %}