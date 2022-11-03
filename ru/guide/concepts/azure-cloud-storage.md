# Azure Blob Storage

{% include [amazon-cloud-storage-alternatives-note](../_includes/concepts/amazon-cloud-storage/id-amazon-cloud-storage/alternatives-note.md) %}

Чтобы опробовать возможности [Microsoft Azure]({{ azure-blob }}), создайте [бесплатную учетную запись]({{ azure-free }}).

#### Условия пробного периода

Длительность | Размер бесплатного хранилища | Сумма гранта
----- | ----- | -----
12 месяцев | 5 ГБ | 200 $ в течение 30 дней

## Порядок действий {#workflow}

Чтобы получить ссылки на файлы:

1. Зарегистрируйтесь в [Azure]({{ azure-sign-up }}).
1. [Создайте учетную запись хранения.](#create-account)
1. [Создайте контейнер.](#container)
1. [Загрузите файлы в контейнер.](#upload)
1. [Скопируйте ссылки.](#get-files)

## Создайте учетную запись хранения {#create-account}

1. Откройте меню портала Azure на [главной странице]({{ azure-home }}) и слева вверху нажмите ![](../_images/tutorials/cloud-storage/azure/more-icon.png).

1. Выберите **Учетные записи хранения**.

1. На верхней панели нажмите ![](../_images/tutorials/cloud-storage/azure/plus-icon.png) **Создать**.

1. На вкладке **Основные** выберите подписку, в которой будет создана учетная запись хранения.

1. Введите имя группы ресурсов и учетной записи.

1. Выберите наиболее близкий к исполнителям регион. Например, для исполнителей из Германии: {% if locale == "ru-ru" %}**Регион** → **(Europe) Центрально-Западная Германия**{% elsif locale == "en-com" %}**Region → (Europe) West Central Germany**{% endif %}.

    {% cut "Как это выглядит в интерфейсе" %}

    ![](../_images/tutorials/cloud-storage/azure/create-storage-account.png)

    {% endcut %}

1. Остальные поля оставьте без изменений. Нажмите **Проверка и создание**.

1. Дождитесь окончания развертывания. Нажмите **Перейти к ресурсу.**

    ![](../_images/tutorials/cloud-storage/azure/deployment-complete.png)

## Создайте контейнер {#container}

1. Слева в меню в разделе **Хранилище данных** выберите **Контейнеры**.

1. На верхней панели нажмите ![](../_images/tutorials/cloud-storage/azure/plus-icon.png) **Контейнер**.

1. Введите имя контейнера.

1. В поле **Общедоступный уровень доступа** выберите **Контейнер**.

    {% include [create-bucket-use-hash-note](../_includes/concepts/amazon-cloud-storage/id-create-bucket/use-hash-note.md) %}

1. Нажмите **Создать**.

{% note info %}

Вы можете настроить время жизни файлов в контейнере, чтобы они автоматически удалялись через несколько дней. [Подробнее]({{ azure-ttl }}).

{% endnote %}

## Загрузите файлы в контейнер {#upload}

1. Чтобы войти в контейнер, нажмите на его имя.

1. На верхней панели нажмите ![](../_images/tutorials/cloud-storage/azure/send-icon.png)**Отправка**.

1.  {% cut "Загрузить файлы" %}

    Выберите файлы на компьютере.

    {% endcut %}

    {% cut "Загрузить файлы в папку" %}

    В разделе **Дополнительно** в поле **Отправить в папку** введите имя папки. Если папки не было, она будет создана.

    {% endcut %}

    {% note alert %}

    В имени файлов не должно быть пробелов. Файлы будут недоступны по ссылке.

    {% endnote %}

1. Нажмите **Отправка**.

## Скопируйте ссылки {#get-files}

1. Выберите загруженный файл и в разделе **Обзор** скопируйте **URL-адрес**.

    {% if locale == "ru-ru" %}

    ![](../_images/tutorials/cloud-storage/azure/url.png)

    {% endif %}

1. {% include [get-files-link-form](../_includes/concepts/amazon-cloud-storage/id-get-files/link-form.md) %}

    {% include [get-files-link-without-folder](../_includes/concepts/amazon-cloud-storage/id-get-files/link-without-folder.md) %}

    {% if locale == "ru-ru" %}

    ```plaintext
    https://<учетная-запись-хранения>.blob.core.windows.net/<контейнер>/<имя-файла>
    ```

    {% endif %}{% if locale == "en-com" %}

    ```plaintext
    https://<storage-account>.blob.core.windows.net/<container>/<filename>
    ```

    {% endif %}

    {% include [get-files-link-from-folder](../_includes/concepts/amazon-cloud-storage/id-get-files/link-from-folder.md) %}

    {% if locale == "ru-ru" %}

    ```plaintext
    https://<учетная-запись-хранения>.blob.core.windows.net/<контейнер>/<путь-к-файлу>/<имя-файла>
    ```

    {% endif %}{% if locale == "en-com" %}

    ```plaintext
    https://<storage-account>.blob.core.windows.net/<container>/<file-path>/<filename>
    ```

    {% endif %}

    {% include [get-files-files-links-create](../_includes/concepts/amazon-cloud-storage/id-get-files/files-links-create.md) %}

1. {% include [tsv-create-create-tsv](../_includes/concepts/cloud-storage/id-tsv-create/create-tsv.md) %}

    {% include [tsv-create-use-links](../_includes/concepts/cloud-storage/id-tsv-create/use-links.md) %}

    ```plaintext
    INPUT:image
    https://mytolokaaccount.blob.core.windows.net/mycontainer/newfolder/image1.png
    https://mytolokaaccount.blob.core.windows.net/mycontainer/newfolder/image2.png
    ```

{% include [contact-support](../_includes/contact-support-new.md) %}