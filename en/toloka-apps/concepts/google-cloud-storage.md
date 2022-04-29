# Google Cloud Storage

{% note info %}

{% include [photo-hosting](_includes/cloud-storage/photo-hosting.md) %}

{% endnote %}


To try out [Google Cloud Storage](https://cloud.google.com/storage/docs/introduction), you can activate [Free trial](https://cloud.google.com/free?).

#### Trial terms

Trial length | Free storage size | Grant amount
------------ | ----------------- | ------------
90 days | 5 GB | $300

## Steps to follow {#workflow}

To get links to files:

1. Create a [Google](https://cloud.google.com/storage/docs/lifecycle) account.
1. Create a [Google Cloud](https://cloud.google.com/free?) account.
1. Go to the [Console](https://console.cloud.google.com/projectselector2/storage/browser).
1. Click ![Create project](../_images/tutorials/cloud-storage/google-cloud/create-bucket-icon.png) **Create project**.
1. Enter the project name. Select the organization from the drop-down list and click **Create**.
1. [Create a bucket](#create-account).
1. [Upload files](#upload).
1. [Copy links](#get-files).


## Create a bucket {#create-account}

1. Select a project and click ![Create bucket](../_images/tutorials/cloud-storage/google-cloud/create-bucket-icon.png) **Create bucket**.

    ![Create bucket](../_images/tutorials/cloud-storage/google-cloud/choose-project.png =600x322)

1. Enter the bucket name. The name should be unique and contain only lower-case Latin letters, numbers, hyphens, and underscores.

    Learn more about the [Bucket naming rules](https://cloud.google.com/storage/docs/naming-buckets?_ga=2.31332223.-1978071647.1627855306).

1. In **Choose where to store your data** select **Location type → Region** and select the region closest to your performers. For example, for performers from Germany: **Location → europe-west3 (Frankfurt)**.

1. Leave the **Choose a default storage class for your data** section unchanged.

1. In **Choose how to control access to objects**, disable the option **Enforce public access prevention on this bucket**.

    ![Choose how to control access to objects](../_images/tutorials/cloud-storage/google-cloud/enforce-access.png =600x200)

1. Click **Create**.

1. To make objects accessible by link, on the **Permissions** tab click ![Add](../_images/tutorials/cloud-storage/google-cloud/add-permission.png) **Add**.

    {% note info %}

    {% include [storage-hash](_includes/cloud-storage/hash.md) %}

    {% endnote %}

1. In the **New members** field, enter **allUsers**.

1. Select **Cloud Storage → Storage Object Viewer**.

    ![Storage Object Viewer](../_images/tutorials/cloud-storage/google-cloud/public-access.png =600x241)

1. Click **Save → Allow public access**.

{% note info %}

You can set the lifetime of files in the bucket so that they are automatically deleted after a specified number of days. [Learn more](https://myaccount.google.com/).

{% endnote %}

## Upload files {#upload}

{% cut "Upload files" %}

On the **Object** tab, click **Upload files** and select the files on your computer.

{% endcut %}

{% cut "Upload a folder with files" %}

On the **Object** tab, click **Upload folder** and select a folder on your computer.

{% endcut %}

{% cut "Create a folder" %}

On the **Object** tab, click **Create folder** and enter the folder name.

{% endcut %}

![Upload files](../_images/tutorials/cloud-storage/google-cloud/upload-files.png =600x190)

{% note info %}

All spaces and symbols in the file names will be replaced with codes.

{% endnote %}

## Copy links {#get-files}

1. Choose the file you uploaded and click **Copy URL** in the **Public access** column.

    ![Copy URL](../_images/tutorials/cloud-storage/google-cloud/copy-link.png =600x51)

1. All file links are created by the same template.

    Links look like this:

    ```
    https://storage.googleapis.com/<bucket>/<file-name>
    ```

    The link in the folder looks like this:

    ```
    https://storage.googleapis.com/<bucket>/<file-path>/<file-name>
    ```

    {% note info %}

    To get links to other files quickly, copy the link to one of them and replace `<file-name>` with the names of other files.

    {% endnote %}

1. {% include [tsv-create-create-tsv](_includes/cloud-storage/id-tsv-create/create-tsv.md) %}

    {% include [markup-images-google](_includes/cloud-storage/markup/markup-images-google.md) %}

{% include [contact-support](_includes/contact-support.md) %}