# Yandex Object Storage

{% note info %}

{% if locale == "en-com" %}You can use any photo hosting service to add a small number of images, such as [wampi]({{ wampi }}), [imgbb]({{ imgbb }}), [ImageShack]({{ imageshack }}), or [imgur]({{ imgur }}). {% endif %} This way you can quickly get direct links to your images to add them to the task file or instructions.

{% endnote %}

To try out [Yandex Cloud]({{ object-storage }}), you can activate a [Free trial]({{ yandex-cloud-free-trial }}).

#### Trial terms

Length | Free storage size | Grant amount
----- | ----- | -----
60 days | 5 TB | $50

## Steps to follow {#concept_ebz_yz4_nlb}

To use files from Yandex Cloud:

1. Create a bucket in Object Storage. To learn how to do this, go to [Getting started]({{ object-storage }}).

    {% note info %}

    Create a bucket with public access. This way you won't need to generate a link to each file separately.

    {% endnote %}

1. Select a bucket and upload your files. Files will be accessible to anyone with a link. We recommend using hashed file names to keep your files secure. You can generate hashes using online tools (for example, [Online MD5 Hash Generator]({{ hash-function-wiki }})). Learn more about [hashing]({{ hash-function-wiki }}).

    {% note info %}

    You can set the lifetime of files in the bucket so that they are automatically deleted after a specified number of days. [Learn more]({{ yandex-tts }}).

    {% endnote %}

1. If you restricted access to the bucket, you need to get a separate link for each file by following the [instructions]({{ link-for-download }}).

    Select a file and click .

    All file links are created by the same template.

    Links look like this:

    {% if locale == "en-com" %}

    ```plaintext
    https://<bucket-name>.s3.<region-code>.amazonaws.com/<filename>
    ```

    {% endif %}

    The link in the folder looks like this:
    {% if locale == "en-com" %}

    ```plaintext
    https://<bucket-name>.s3.<region-code>.amazonaws.com/<path-to-file>/<filename>
    ```

    {% endif %}

    {% note info %}

    To quickly get links to other files, copy the link to one of them and replace `<filename>` with the names of other files.

    {% endnote %}

1. In the [file with tasks](pool_csv.md), paste the links in the column that matches the input data field to which this data is passed.

    For example, if you want to use images in the `image` field, specify the file links in the `INPUT:image` column:

    ```plaintext
    INPUT:image
    https://storage.yandexcloud.net/my-bucket/1.jpg
    https://storage.yandexcloud.net/my-bucket/2.jpg
    ```

{% include [contact-support](../_includes/contact-support-new.md) %}