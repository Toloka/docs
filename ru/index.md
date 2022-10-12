<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 50px;
}
.grid-item {
  display: flex;
  flex-direction: column;
}
h2 {
  padding-top: 32px !important;
  margin-top: 0 !important;
}
h3 {
  padding-top: 16px !important;
  margin-top: 0 !important;
}
</style>

# Документация Толоки

[Толока]({{ toloka }}) позволяет анализировать большие массивы данных силами интернет-пользователей в короткие сроки. Например, вы можете поручить пользователям распределить множество товаров в вашем интернет-магазине по группам, найти или проверить какую-либо информацию, перевести тексты и т. д.

<div class="grid-container">
    <div class="grid-item">
        <h2>С чего начать</h2>
        <p><a href="guide/concepts/overview">Как устроена Толока</a></p>
        <p><a href="guide/concepts/unwanted">Какие задания нельзя размещать в Толоке</a></p>
        <p><a href="guide/concepts/access">Регистрация</a></p>
        <p><a href="guide/concepts/first-project">Первый проект</a></p>
        <p><a href="guide/concepts/data-security">Безопасность данных</a></p>
    </div>
    <div class="grid-item">
        <h2>Туториалы</h2>
        <p><a href="guide/concepts/categorization">Изображения</a></p>
        <p><a href="guide/concepts/video-moderation">Видео</a></p>
        <p><a href="guide/concepts/transcript-audio">Аудио</a></p>
        <p><a href="guide/concepts/content-moderation">Тексты</a></p>
        <p><a href="guide/concepts/questionnaire">Обогащение данных</a></p>
        <p><a href="guide/concepts/walk">Полевые задачи</a></p>
    </div>
    <div class="grid-item">
        <h2>Проекты</h2>
        <p><a href="guide/concepts/project">Создание проекта</a></p>
        <p><a href="guide/concepts/pool-main">Управление пулами</a></p>
        <p><a href="guide/concepts/task_upload">Размещение заданий</a></p>
        <p><a href="guide/concepts/result-of-eval">Получение результатов</a></p>
    </div>
    <div class="grid-item">
        <h2>Интерфейс задания</h2>
        <p><a href="template-builder/">Конструктор шаблонов</a></p>
        <p><a href="guide/concepts/spec">Редактор HTML/CSS/JS</a></p>
        <p></p>
        <h2>Настройки Толоки</h2>
        <p><a href="guide/concepts/users">Пользователи</a></p>
        <p><a href="guide/concepts/nav">Навыки</a></p>
        <p><a href="guide/concepts/budget">Профиль</a></p>
    </div>
    <div class="grid-item">
        <h2>Советы и рекомендации</h2>
        <p><a href="guide/concepts/sandbox">Песочница</a></p>
        <p><a href="guide/concepts/cloud-storage">Хранение данных</a></p>
        <p><a href="guide/concepts/control">Правила контроля качества</a></p>
        <p><a href="guide/concepts/train">Добавление обучения</a></p>
    </div>
    <div class="grid-item">
        <h2>Решение проблем и поддержка</h2>
        <p><a href="guide/concepts/frequent-customer-errors">Частые ошибки заказчиков</a></p>
        <p><a href="guide/troubleshooting/troubleshooting">Все вопросы на одной странице</a></p>
        <p><a href="glossary">Глоссарий</a></p>
        <p><a href="guide/troubleshooting/support">Служба поддержки</a></p>
    </div>
</div>

## Разработчикам

<div class="grid-container">
    <div class="grid-item">
        <h3>REST API</h3>
        <p><a href="api/">API Толоки</a></p>
    </div>
    <div class="grid-item">
        <h3>Python SDK</h3>
        <p><a href="toloka-kit/">Toloka-Kit</a></p>
        <p><a href="crowd-kit/">Crowd-Kit</a></p>
    </div>
</div>

{% include [social-media](../ru/_includes/social-media.md) %}