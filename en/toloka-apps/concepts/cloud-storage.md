# Where to store files

[Photo hosting](#image-hosting)

[Cloud storage](#cloud)

[Creating a markup element](#tsv-create)

If your task requires images, audio, or video files, upload them to [photo hosting](#image-hosting) or [cloud storage](#cloud) and provide links to them in the TSV, CSV, JSON, or XLSX-file.

If you need to add less than 10 images, use photo hosting. If you need to add more images, or audio and video files, use cloud storage.

{% cut "TSV" %}

TSV (tab-separated values) is a text file format, in which data is separated by tab symbols, and strings — with the newline symbol.

{% endcut %}

## Photo hosting {#image-hosting}

Some photo hosting services are free and don't require registration. This way you can quickly and easily upload your files and get links to them. But they have limitations. For example, [wampi](https://wampi.ru/?lang=en) doesn't allow people to use their service for commercial purposes. Images uploaded without creating an account can be deleted if they are not accessed for a year. We recommend you to read the terms of use before using photo hosting services.

{% note info %}

The information about the terms is provided here for informational purposes.

The terms may be changed by the service unilaterally. You can view changes on the photo hosting website.

Toloka is not responsible for such changes or for placing them in this section within a certain timeframe.

{% endnote %}

#### Terms of use

Photo hosting | Maximum image size | Registration | Trial period
------------- | ------------------ | ------------ | ------------
[wampi](https://wampi.ru/?lang=en) | 10 MB | No | &mdash;
[imgbb](https://imgbb.com/) | 32 MB | No | &mdash;
[ImageShack](https://imageshack.com/) | 25 MB | Yes | 30 days
[imgur](https://imgur.com/) | 20 MB | Yes | &mdash;

#### How to upload an image to photo hosting

For example, wampi:

1. Go to the photo hosting website.
1. Click **Start uploading**.
1. Select files from your device. Before uploading, you can change the image size and add a title or description.
1. Click **Upload**.
1. Copy the links and add them to the TSV file.

## Cloud storage {#cloud}

In Object Storage terms, files and folders are _objects_. All objects are stored in buckets. A _bucket_ is a logical entity that helps organize object storage.

Cloud storage enables users to store large amounts of data. You need to pay to use it. To try out a service, use a free trial.

{% note info %}

The information about the terms is provided for informational purposes.

The terms of use and rates may be changed unilaterally by the service. You can view changes on the cloud storage website.

Toloka is not responsible for such changes or for placing them in this section within a certain timeframe.

{% endnote %}


#### Trial terms

Storage type | Trial length | Free storage size | Grant amount | Additional information
------------ | ------------ | ----------------- | ------------ | ----------------------
[Amazon S3](amazon-cloud-storage.md) | 12 months | 5 GB | &mdash; | [Free access level](https://aws.amazon.com/free)
[Azure Blob Storage](azure-cloud-storage.md) | 12 months | 5 GB | $200 within 30 days | [Free account](https://azure.microsoft.com/en-us/free/)
[Google Cloud Storage](google-cloud-storage.md) | 90 days | 5 GB | $300 | [Trial period](https://cloud.google.com/free)
[Yandex Object Storage](use-object-storage.md) | 60 days | 5 TB | $50 | [Trial period](https://cloud.yandex.com/en-ru/docs/free-trial/)

#### How to upload an image to cloud storage

For example, Amazon S3:

1. Sign up for [Amazon Web Services](https://aws.amazon.com/getting-started/hands-on/backup-files-to-amazon-s3/?nc1=h_ls).
1. Enter the [console](https://console.aws.amazon.com/console/home?nc2=h_ct&src=header-signin).
1. Enter the [Amazon S3](https://s3.console.aws.amazon.com/s3/home) service.
1. Create the bucket.
1. Upload files to the bucket.
1. Copy the links.

## Creating a markup element {#tsv-create}

{% include [tsv-create-create-tsv](_includes/cloud-storage/id-tsv-create/create-tsv.md) %}

{% note info %}

Field names may vary for different ready-to-go solutions.

{% endnote %}

{% list tabs %}

- Amazon S3

  {% include [markup-images-amazon](_includes/cloud-storage/markup/markup-images-amazon.md) %}

- Azure Blob Storage

  {% include [markup-images-azure](_includes/cloud-storage/markup/markup-images-azure.md) %}

- Google Cloud Storage

  {% include [markup-images-google](_includes/cloud-storage/markup/markup-images-google.md) %}

- Yandex Object Storage

  {% include [markup-images-yandex](_includes/cloud-storage/markup/markup-images-yandex.md) %}

{% endlist %}

{% include [contact-support](_includes/contact-support.md) %}