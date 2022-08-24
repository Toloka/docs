# Where to store files

If your task requires images, audio, or video files, upload them to [photo hosting](#image-hosting) or [cloud storage](#cloud) and provide links to them in the [TSV file](../../glossary.md#tsv-file-definition-ru).

If you need less than 10 images (for example, for task instructions or for testing a pool), use photo hosting. If you need to add more images, or audio and video files, use cloud storage.

## Photo hosting {#image-hosting}

Some photo hosting services are free and don't require registration. This way you can quickly and easily upload your files and get links to them. But they have limitations. For example, [wampi]({{ wampi }}) doesn't allow people to use their service for commercial purposes. Images uploaded without creating an account can be deleted if they are not accessed for a year. We recommend that you read the terms of use before using photo hosting services.

{% note info %}

The information about the terms is provided here for informational purposes.

The terms may be changed by the service unilaterally. You can view changes on the photo hosting website.

Toloka is not responsible for such changes or for placing them in this section within a certain timeframe.

{% endnote %}


#### Terms of use

Photo hosting | Maximum image size | Registration | Trial period
----- | ----- | ----- | -----
[wampi]({{ wampi }}) | 10 MB | No | —
[imgbb]({{ imgbb }}) | 32 MB | No | —
[ImageShack]({{ imageshack }}) | 25 MB | Yes | 30 days
 {% if locale == "en-com" %}
[imgur]({{ imgur }}) | 20 MB | Yes | —
{% endif %}

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

Storage type | Trial length | Free storage size | Grant amount | Additional information.
----- | ----- | ----- | ----- | -----
[Amazon S3](amazon-cloud-storage.md) | 12 months | 5 GB | — | [Free access level]({{ amazon-s3-free }})
[Azure Blob Storage](azure-cloud-storage.md) | 12 months | 5 GB | $200 within 30 days | [Free account]({{ azure-free }})
[Google Cloud Storage](google-cloud-storage.md) | 90 days | 5 GB | $300 | [Trial period]({{ google-cloud-free-trial }})
[Yandex Object Storage](use-object-storage.md) | 60 days | 5 TB | $50 | [Trial period]({{ yandex-cloud-free-trial }})


## Creating a TSV file with tasks {#tsv-create}

To use a file in the task interface, you should have a field of **link** type in your project's [input data](incoming.md). You'll need the name of this field later when creating a TSV file.

In the[TSV file with the tasks](pool_csv.md), paste the links into the column that matches the input data field to which this data is passed.

For example, if you want to use images in the `image` field, specify the file links in the `INPUT:image` column:

#### Amazon S3

```
INPUT:image
https://mybucket.s3.eu-north-1.amazonaws.com/newfolder/image1.png
https://mybucket.s3.eu-north-1.amazonaws.com/newfolder/image2.png
```

#### Azure Blob Storage

```
INPUT:image
https://mytolokaaccount.blob.core.windows.net/mycontainer/newfolder/image1.png
https://mytolokaaccount.blob.core.windows.net/mycontainer/newfolder/image2.png
```

#### Google Cloud Storage

```
INPUT:image
https://storage.googleapis.com/mytolokabucket/newfolder/image1.png
https://storage.googleapis.com/mytolokabucket/newfolder/image2.png
```

#### Yandex Object Storage

```
INPUT:image
https://storage.yandexcloud.net/my-bucket/1.jpg
https://storage.yandexcloud.net/my-bucket/2.jpg
```


If these recommendations didn't help:

{% include [contact-support](../_includes/contact-support-help.md) %}