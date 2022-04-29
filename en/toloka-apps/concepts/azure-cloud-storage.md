# Azure Blob Storage

{% note info %}

{% include [photo-hosting](_includes/cloud-storage/photo-hosting.md) %}

{% endnote %}

To try [Microsoft Azure](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction), create a [free account](https://azure.microsoft.com/en-us/free/).

#### Trial terms

Trial length | Free storage size | Grant amount
------------ | ----------------- | ------------
12 months | 5 GB | $200 within 30 days

## Steps to follow {#workflow}

To get links to files:

1. Sign up for [Azure](https://signup.azure.com/signup).
1. [Create a storage account](#create-account).
1. [Create a container](#container).
1. [Upload files to the container](#upload).
1. [Copy links](#get-files).

## Create a storage account {#create-account}

1. Open the Azure [main page](https://portal.azure.com/?quickstart=true#home) and click ![Hamburger menu](../_images/tutorials/cloud-storage/azure/more-icon.png) in the top left corner.

1. Select **Storage accounts**.

1. On the top panel, click ![Create](../_images/tutorials/cloud-storage/azure/plus-icon.png) **Create**.

1. On the **Basic** tab, select the subscription for the new storage account.

1. Enter the name of the resource group and your account.

1. Select the region closest to your performers. For example, for performers from Germany: **Region → (Europe) West Central Germany**.

    {% cut "What it looks like in the interface" %}

    ![What it looks like in the interface](../_images/tutorials/cloud-storage/azure/create-storage-account.png =600x177)

    {% endcut %}

1. Leave other fields unchanged. Click **Review + create**.

1. Wait till it opens. Click **Go to resource**.

    ![Go to resource](../_images/tutorials/cloud-storage/azure/deployment-complete.png =350x199)

## Create a container {#container}

1. In the **Data storage** section in the left menu, select **Containers**.

1. On the top panel, click ![Container](../_images/tutorials/cloud-storage/azure/plus-icon.png) **Container**.

1. Enter the container name.

1. In the **Public access level** field, select **Container**.

    {% note info %}

    {% include [storage-hash](_includes/cloud-storage/hash.md) %}

    {% endnote %}

1. Click **Create**.

{% note info %}

You can set up the lifetime of files in the container so that they are automatically deleted after a specified number of days. [Learn more](https://docs.microsoft.com/en-us/azure/cdn/cdn-manage-expiration-of-blob-content).

{% endnote %}

## Upload your files to the container {#upload}

1. To open the container, click its name.

1. On the top panel, click ![Send](../_images/tutorials/cloud-storage/azure/send-icon.png) **Send**.

1. {% cut "Upload files" %}

    Select files on your device.

    {% endcut %}

    {% cut "Upload files to the folder" %}

    In the **Send to folder** field in the **Additional** section, enter the name of the folder. If the folder doesn't exist, it will be created.

    {% endcut %}

    {% note alert %}

    The name can't contain spaces. Files can't be accessed by link.

    {% endnote %}

1. Click **Send**.

## Copy links {#get-files}

1. Select the uploaded file and copy its **URL** from the **Review** section.

1. All file links are created by the same template.

    Links look like this:

    ```
    https://<storage-account>.blob.core.windows.net/<container>/<file-name>
    ```

    The link in the folder looks like this:

    ```
    https://<storage-account>.blob.core.windows.net/<container>/<file-path>/<file-name>
    ```

    {% note info %}

    To get links to other files quickly, copy the link to one of them and replace `<file-name>` with the names of other files.

    {% endnote %}

1. {% include [tsv-create-create-tsv](_includes/cloud-storage/id-tsv-create/create-tsv.md) %}

    {% include [markup-images-azure](_includes/cloud-storage/markup/markup-images-azure.md) %}

{% include [contact-support](_includes/contact-support.md) %}