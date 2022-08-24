# Google Cloud Storage

{% include [amazon-cloud-storage-alternatives-note](../_includes/concepts/amazon-cloud-storage/id-amazon-cloud-storage/alternatives-note.md) %}


Чтобы ознакомиться с [Google Cloud Storage]({{ google-cloud-storage }}), вы можете активировать [Пробный период]({{ google-cloud-free-trial }}).

#### Условия пробного периода

Длительность | Размер бесплатного хранилища | Сумма гранта
----- | ----- | -----
90 дней | 5 ГБ | 300 $


## Порядок действий {#workflow}

Чтобы получить ссылки на файлы:

1. Создайте аккаунт в [Google]({{ google-account }}).
1. Создайте аккаунт в [Google Cloud]({{ google-cloud-free-trial }}).
1. Перейдите в [консоль управления]({{ google-cloud-home }}).
1. Нажмите ![](../_images/tutorials/cloud-storage/google-cloud/create-bucket-icon.png)**Create project**.
1. Введите имя проекта. Выберите предприятие из выпадающего списка и нажмите **Create**.
1. [Создайте бакет](#create-account).
1. [Загрузите файлы](#upload).
1. [Скопируйте ссылки](#get-files).


## Создайте бакет {#create-account}

1. Выберите проект и нажмите ![](../_images/tutorials/cloud-storage/google-cloud/create-bucket-icon.png)**Create bucket**.

1. Введите имя бакета. Имя должно быть уникальным и содержать только латинские строчные буквы, цифры, дефисы и подчеркивания.
    Подробнее о [Правилах наименования бакетов]({{ google-cloud-about-bucket }}).
1. В разделе **Choose where to store your data** выберите  и наиболее близкий к вашим исполнителям регион. Например, для исполнителей из Германии: .

1. Раздел **Choose a default storage class for your data** оставьте без изменений.

1. В разделе **Choose how to control access to objects** отключите опцию **Enforce public access prevention on this bucket**.

1. Нажмите **Create**.

1. Чтобы сделать объекты доступными по ссылке, на вкладке **Permissions** нажмите ![](../_images/tutorials/cloud-storage/google-cloud/add-permission.png)**Add**.
    {% include [create-bucket-use-hash-note](../_includes/concepts/amazon-cloud-storage/id-create-bucket/use-hash-note.md) %}

1. В поле **New members** введите **allUsers**.

1. Выберите роль .

1. Нажмите .


{% note info %}

Вы можете настроить время жизни файлов в бакете, чтобы они автоматически удалялись через несколько дней. [Подробнее]({{ google-cloud-ttl }}).

{% endnote %}



## Загрузите файлы {#upload}

#### Загрузить файлы

На вкладке **Object** нажмите **Upload files** и выберите файлы на компьютере.

#### Загрузить папку с файлами

На вкладке **Object** нажмите **Upload folder** и выберите папку на компьютере.

#### Создать папку

На вкладке **Object** нажмите **Create folder** и укажите имя папки.

{% note info %}

Все пробелы и символы в имени файла, кроме латинских букв, будут заменены на коды символов.

{% endnote %}



## Скопируйте ссылки {#get-files}

1. Выберите загруженный файл и в столбце **Public access** нажмите **Copy URL**.

1. {% include [get-files-link-form](../_includes/concepts/amazon-cloud-storage/id-get-files/link-form.md) %}

    {% include [get-files-link-without-folder](../_includes/concepts/amazon-cloud-storage/id-get-files/link-without-folder.md) %}

    {% if locale == "ru-ru" %}
    ```
    https://storage.googleapis.com/<бакет>/<имя файла>
    ```
    {% endif %}{% if locale == "en-com" %}
    ```
    https://<bucket-name>.s3.<region-code>.amazonaws.com/<filename>
    ```
    {% endif %}
    {% include [get-files-link-from-folder](../_includes/concepts/amazon-cloud-storage/id-get-files/link-from-folder.md) %}

    {% if locale == "ru-ru" %}
    ```
    https://storage.googleapis.com/<бакет>/<путь к файлу>/<имя файла>
    ```
    {% endif %}{% if locale == "en-com" %}
    ```
    https://<bucket-name>.s3.<region-code>.amazonaws.com/<path-to-file>/<filename>
    ```
    {% endif %}
    {% include [get-files-files-links-create](../_includes/concepts/amazon-cloud-storage/id-get-files/files-links-create.md) %}

1. {% include [tsv-create-create-tsv](../_includes/concepts/cloud-storage/id-tsv-create/create-tsv.md) %}

    {% include [tsv-create-use-links](../_includes/concepts/cloud-storage/id-tsv-create/use-links.md) %}

    ```
    INPUT:image
    https://storage.googleapis.com/mytolokabucket/newfolder/image1.png
    https://storage.googleapis.com/mytolokabucket/newfolder/image2.png
    ```


{% include [contact-support](../_includes/contact-support-new.md) %}