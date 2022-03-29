# Yandex Object Storage

{% note info %}

{% include [photo-hosting](_includes/cloud-storage/photo-hosting.md) %}

{% endnote %}

To try out [Yandex.Cloud](https://cloud.yandex.com/docs/storage/quickstart), you can activate a [Free trial](https://cloud.yandex.com/en-ru/docs/free-trial/).

#### Trial terms

Trial length | Free storage size | Grant amount
------------ | ----------------- | ------------
60 days | 5 TB | $50

## Steps to follow {#concept_ebz_yz4_nlb}

To use files from Yandex.Cloud:

1. Create a bucket in Object Storage. To learn how to do this, go to [Getting started](https://cloud.yandex.com/docs/storage/quickstart).

    {% note info %}

    Create a bucket with public access. This way you won't need to generate a link to each file separately.

    {% endnote %}

1. Select a bucket and upload your files.

    {% include [storage-hash](_includes/cloud-storage/hash.md) %}

    {% note info %}

    You can set the lifetime of files in the bucket so that they are automatically deleted after a specified number of days. [Learn more](https://cloud.yandex.com/en-ru/docs/storage/operations/buckets/lifecycles).

    {% endnote %}

1. If you restricted access to the bucket, you need to get a separate link for each file by following the instructions.

    Select a file and click **Get a link → Copy**.

    All file links are created by the same template.

    Links look like this:

    ```
    https://storage.yandexcloud.net/<bucket-name>/<file-name>
    ```

    The link in the folder looks like this:

    ```
    https://storage.yandexcloud.net/<bucket-name>/<path-to-file>/<file-name>
    ```

    {% note info %}

    To get links to other files quickly, copy the link to one of them and replace `<file-name>` with the names of other files.

    {% endnote %}

1. {% include [tsv-create-create-tsv](_includes/cloud-storage/id-tsv-create/create-tsv.md) %}

    {% include [markup-images-yandex](_includes/cloud-storage/markup/markup-images-yandex.md) %}

{% include [contact-support](_includes/contact-support.md) %}