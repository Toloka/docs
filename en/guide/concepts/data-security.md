# Data security

Toloka cares about the security of your data and data labeling results. This section describes the key principles of working with data in Toloka.

## Key principles {#key-principles}

- The rights to the results with labeled data belong to the requester, and no one else.

- The data that the requester sends to Toloka is strictly confidential. Support staff have access to this data. The list of employees granted this access is regularly reviewed and their activities are monitored by our team.

    {% note warning %}

    If necessary, the requester may grant [access](multiple-access.md) to their account to other users, for example, to their employees.

    {% endnote %}

- According to the [User Agreement]({{ useragreement }}), Tolokers must treat the requester's data as confidential. We make sure that no fraudulent users get access to Toloka: cheaters get a warning or [ban](../../glossary.md#banning-tolokers).

## Personal data {#personal-data}

By transmitting data to Toloka, you automatically agree to this data being processed by third parties, namely, Tolokers in Toloka.

To avoid transmitting personal data, you can anonymize the data yourself. For example, you can cover up people's faces in photos and change the pitch of the voice in speech recordings.

For [tasks](../../glossary.md#task) that use recognition of passports or questionnaires with personal information, you can cut out data fields and use separate tasks for them. For example, you can send the last name, first name, and middle name separately for recognition.

## Protect your data

We make every effort to ensure the security of your data, but sometimes tasks are completed by cheaters.
If your data is confidential, take additional measures to protect it.

### Protect your data from cheaters {#protect-from-them}

{% include [toloka-requester-source-anti-fraud](../_includes/toloka-requester-source/id-toloka-requester-source/anti-fraud.md) %}

To protect your data:

- [Decompose tasks](solution-architecture.md#concept_o3r_h4g_nlb). You can break your tasks down into several [projects](../../glossary.md#project) (steps). Each step contains only part of the data, and a malicious user won't be able to put the pieces together.

- If you use [input](../../glossary.md#input-output-data) fields to transmit data that Tolokers shouldn't see, hide the fields that contain this data. For instance, do this if you moderate comments and you need the authors' personal data in the results for further data processing.

- Use any name or pseudonym to identify yourself for the Tolokers — you don't have to disclose your company name. This is useful for requesters who don't want to attract unnecessary interest from Tolokers.

- You can use the [Submitted responses](submitted-answers.md#rule) quality control rule to limit the number of task suites each Toloker can complete. This lets you better protect your data from fraud and minimize your risks (scattered data has no commercial value).

### Store data on your own server {#keep-it-save}

Set up the process to avoid storing data on Toloka servers. To do this:

1. When uploading tasks to the [pool](../../glossary.md#pool), use IDs in the input data rather than content itself.

1. Set up a server to return the task content based on IDs.

1. In the [task interface](../../glossary.md#task-interface), add code that sends IDs to the server and displays the content received.

For instance, you can store text comments on your server and use the file with tasks to pass only the comment IDs. As a result, only the ID+result pairs are saved in the Toloka database, but these pairs don't have any commercial value in the absence of input data.

### Request more features {#help-by-request}

- We are always happy to sign an NDA (Non-Disclosure Agreement) with requesters. If that's critical for your company, please contact us at [customercare@toloka.ai](mailto:customercare@toloka.ai)

- You can send requests from Toloka tasks to your server. To get assistance in setting up the process, contact us at [customercare@toloka.ai](mailto:customercare@toloka.ai).

    This is useful if:

    - You need images or other files for your tasks, and you want to store them on your own server.

    - You need to load dynamic data in the tasks.

    - You want to log user actions.

## What's next {#what-next}

- [Learn how to post tasks](first-project.md)

- See the documents governing interaction with Toloka

    - For the requester:

        - [Agreement for requesters registered in the USA]({{ customeragreement-usa }})

        - [Customer Service Agreement]({{ customeragreement }})

    - For Tolokers:

        - [User Agreement]({{ useragreement }})

        - [License agreement for use of the Toloka app for mobile devices]({{ mobile-agreement }})

    - [Privacy Policy]({{ confidential }})

## See also {#see-also}

- [{#T}](cloud-storage.md)

## Troubleshooting {#troubleshooting}

{% include [troubleshooting-trusted-user-banned](../_includes/troubleshooting/users/trusted-user-banned.md) %}

{% include [faq-give-access](../_includes/faq/project-settings/give-access.md) %}

{% include [faq-ban-and-reject](../_includes/faq/users/ban-and-reject.md) %}

{% include [faq-change-account-type](../_includes/faq/register-and-start/change-account-type.md) %}

{% include [contact-support](../_includes/contact-support.md) %}