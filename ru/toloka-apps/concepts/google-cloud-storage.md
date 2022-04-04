# Google Cloud Storage

[Порядок действий](#workflow)

[Создайте бакет](#create-account)

[Загрузите файлы](#upload)

[Скопируйте ссылки](#get-files)

{% note info %}

{% include [photo-hosting](_includes/cloud-storage/photo-hosting.md) %}

{% endnote %}

Чтобы ознакомиться с [Google Cloud Storage](https://cloud.google.com/storage/docs/introduction), вы можете активировать [Пробный период](https://cloud.google.com/free?).

#### Условия пробного периода

Длительность | Размер бесплатного хранилища | Сумма гранта
------------ | ----------------- | ------------
90 дней | 5 ГБ | 300 $

## Порядок действий {#workflow}

Чтобы получить ссылки:

1. Создайте аккаунт в [Google](https://cloud.google.com/storage/docs/lifecycle).
1. Создайте аккаунт в [Google Cloud](https://cloud.google.com/free?).
1. Перейдите в [консоль управления](https://console.cloud.google.com/projectselector2/storage/browser).
1. Нажмите ![Create project](../_images/tutorials/cloud-storage/google-cloud/create-bucket-icon.png) **Create project**.
1. Введите имя проекта. Выберите предприятие из выпадающего списка и нажмите **Create**.
1. [Создайте бакет](#create-account).
1. [Загрузите файлы](#upload).
1. [Скопируйте ссылки](#get-files).

## Создайте бакет {#create-account}

1. Выберите проект и нажмите ![Create bucket](../_images/tutorials/cloud-storage/google-cloud/create-bucket-icon.png) **Create bucket**.

    ![Create bucket](../_images/tutorials/cloud-storage/google-cloud/choose-project.png =500x268)

1. Введите имя бакета. Имя должно быть уникальным и содержать только латинские строчные буквы, цифры, подчеркивания и дефисы.

    Подробнее о [Правилах наименования бакетов](https://cloud.google.com/storage/docs/naming-buckets?_ga=2.31332223.-1978071647.1627855306).

1. В разделе **Choose where to store your data** выберите **Location type → Region** и наиболее близкий к вашим исполнителям регион. Например, для исполнителей из Германии: **Location → europe-west3 (Frankfurt)**.

1. Раздел **Choose a default storage class for your data** оставьте без изменений.

1. В разделе **Choose how to control access to objects** отключите опцию **Enforce public access prevention on this bucket**.

    ![Choose how to control access to objects](../_images/tutorials/cloud-storage/google-cloud/enforce-access.png =400x133)

1. Нажмите **Create**.

1. Чтобы сделать объекты доступными по ссылке, на вкладке **Permissions** нажмите ![Add](../_images/tutorials/cloud-storage/google-cloud/add-permission.png) **Add**.

    {% note info %}

    {% include [storage-hash](_includes/cloud-storage/hash.md) %}

    {% endnote %}

1. В поле **New members** введите **allUsers**.

1. Выберите роль **Cloud Storage → Storage Object Viewer**.

    ![Storage Object Viewer](../_images/tutorials/cloud-storage/google-cloud/public-access.png =500x201)

1. Нажмите **Save → Allow public access**.

{% note info %}

Вы можете настроить время жизни файлов в бакете, чтобы они автоматически удалялись через несколько дней. [Подробнее](https://myaccount.google.com/).

{% endnote %}

## Загрузите файлы {#upload}

{% cut "Загрузить файлы" %}

На вкладке **Object** нажмите **Upload files** и выберите файлы на компьютере.

{% endcut %}

{% cut "Загрузить папку с файлами" %}

На вкладке **Object** нажмите **Upload folder** и выберите папку на компьютере.

{% endcut %}

{% cut "Создать папку" %}

На вкладке **Object** нажмите **Create folder** и укажите имя папки.

{% endcut %}

![Загрузите файлы](../_images/tutorials/cloud-storage/google-cloud/upload-files.png =500x158)

{% note info %}

Все пробелы и символы в имени файла, кроме латинских букв, будут заменены на коды символов.

{% endnote %}

## Скопируйте ссылки {#get-files}

1. Выберите загруженный файл и в столбце **Public access** нажмите **Copy URL**.

    ![Copy URL](../_images/tutorials/cloud-storage/google-cloud/copy-link.png =600x51)

1. {% include [get-files-link-form](_includes/amazon-cloud-storage/id-get-files/link-form.md) %}

    {% include [get-files-link-without-folder](_includes/amazon-cloud-storage/id-get-files/link-without-folder.md) %}

    ```
    https://storage.googleapis.com/<бакет>/<имя файла>
    ```

    {% include [get-files-link-from-folder](_includes/amazon-cloud-storage/id-get-files/link-from-folder.md) %}

    ```
    https://storage.googleapis.com/<бакет>/<путь к файлу>/<имя файла>
    ```

    {% include [get-files-files-links-create](_includes/amazon-cloud-storage/id-get-files/files-links-create.md) %}

1. {% include [tsv-create-create-tsv](_includes/cloud-storage/id-tsv-create/create-tsv.md) %}

    {% include [markup-images-google](_includes/cloud-storage/markup/markup-images-google.md) %}

{% include [contact-support](_includes/contact-support.md) %}