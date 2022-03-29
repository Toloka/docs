# Amazon S3

{% note info %}

{% include [photo-hosting](_includes/cloud-storage/photo-hosting.md) %}

{% endnote %}

To try out [S3](https://aws.amazon.com/s3/?nc1=h_ls), you can activate a [free trial](https://aws.amazon.com/free).

#### Trial terms

Trial length | Free storage size | Grant amount
------------ | ----------------- | ------------
12 months | 5 GB | &mdash;

## Steps to follow {#workflow}

To get links to files:

1. Sign up to [Amazon Web Services](https://aws.amazon.com/getting-started/hands-on/backup-files-to-amazon-s3/?nc1=h_ls).
1. Go to the [Console](https://console.aws.amazon.com/console/home?nc2=h_ct&src=header-signin).
1. Log in to [Amazon S3](https://s3.console.aws.amazon.com/s3/home).
1. [Create a bucket](#create-bucket).
1. [Upload files to the bucket](#upload).
1. [Copy links](#get-files).

## Create a bucket {#create-bucket}

1. In the **Buckets** section, click **Create Bucket**.

    ![Create Bucket](../_images/tutorials/cloud-storage/amazon/create-bucket.png =600x118)

1. Enter the bucket name. The name must be unique and must not contain spaces or upper-case letters.

    Learn more about the [Bucket naming rules](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html).

1. Select the region closest to your performers. For example, for performers from Germany: **AWS Region → EU (Frankfurt) eu-central-1**.

1. To make files in the bucket available by link, disable the option **Block all public access** in the **Block Public Access settings for this bucket** section.

    {% note info %}

    {% include [storage-hash](_includes/cloud-storage/hash.md) %}

    {% endnote %}

1. Confirm changes.

    ![Confirm changes](../_images/tutorials/cloud-storage/amazon/accept-privacy.png =600x121)

1. If you want to enable version control, select **Bucket Versioning → Enable**.

    To make your files easier to navigate, add [tags](https://docs.aws.amazon.com/AmazonS3/latest/userguide/CostAllocTagging.html).

1. Click **Create bucket**.

    {% note info %}

    You can set the lifetime of files in the bucket so that they are automatically deleted after a specified number of days. [Learn more](https://aws.amazon.com/ru/blogs/aws/amazon-s3-object-expiration/).

    {% endnote %}

## Upload files to the bucket {#upload}

1. In the **Buckets** section, select a bucket.

1. On the **Objects** tab, click **Upload**.

    ![Confirm changes](../_images/tutorials/cloud-storage/amazon/upload.png =600x182)

1. {% cut "Upload files" %}

    Select the files on your computer and click **Add files**.

    {% endcut %}

    {% cut "Upload a folder with files" %}

    Select the folder with the files on your computer and click **Add folder**.

    {% endcut %}

    {% cut "Create a folder and upload files" %}

    To create a folder in the bucket, click **Create folder** and upload files.

    {% endcut %}

    {% note info %}

    All symbols except for Latin letters will be replaced with codes, and spaces will be replaced with plus signs.

    {% endnote %}

1. Click **Upload**.

1. After the files are uploaded, click **Close**.

## Copy links {#get-files}

1. Select the uploaded file and click **Copy URL** on the **Object** tab.

    ![Confirm changes](../_images/tutorials/cloud-storage/amazon/overview.png =600x345)

1. All file links are created by the same template.

    Links look like this:

    ```
    https://<bucket-name>.s3.<region-code>.amazonaws.com/<file-name>
    ```

    The link in the folder looks like this:

    ```
    <bucket-name>.s3.<region-code>.amazonaws.com/<file-name>
    ```

    {% note info %}

    To get links to other files quickly, copy the link to one of them and replace `<file-name>` with the names of other files.

    {% endnote %}

1. {% include [tsv-create-create-tsv](_includes/cloud-storage/id-tsv-create/create-tsv.md) %}

    {% include [markup-images-amazon](_includes/cloud-storage/markup/markup-images-amazon.md) %}

{% include [contact-support](_includes/contact-support.md) %}