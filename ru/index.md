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
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/overview.html">Как устроена Толока</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/unwanted.html">Какие задания нельзя размещать в Толоке</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/access.html">Регистрация</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/first-project.html">Первый проект</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/data-security.html">Безопасность данных</a></p>
    </div>
    <div class="grid-item">
        <h2>Туториалы</h2>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/categorization.html">Изображения</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/video-moderation.html">Видео</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/transcript-audio.html">Аудио</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/content-moderation.html">Тексты</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/questionnaire.html">Обогащение данных</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/walk.html">Полевые задачи</a></p>
    </div>
    <div class="grid-item">
        <h2>Проекты</h2>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/project.html">Создание проекта</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/pool-main.html">Управление пулами</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/task_upload.html">Размещение заданий</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/result-of-eval.html">Получение результатов</a></p>
    </div>
    <div class="grid-item">
        <h2>Интерфейс задания</h2>
        <p><a href="template-builder/">Конструктор шаблонов</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/spec.html">Редактор HTML/CSS/JS</a></p>
        <p></p>
        <h2>Настройки Толоки</h2>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/users.html">Пользователи</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/nav.html">Навыки</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/budget.html">Профиль</a></p>
    </div>
    <div class="grid-item">
        <h2>Советы и рекомендации</h2>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/sandbox.html">Песочница</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/cloud-storage.html">Хранение данных</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/control.html">Правила контроля качества</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/train.html">Добавление обучения</a></p>
    </div>
    <div class="grid-item">
        <h2>Решение проблем и поддержка</h2>
        <p><a href="https://toloka.ai/ru/docs/guide/concepts/frequent-customer-errors.html">Частые ошибки заказчиков</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/troubleshooting/troubleshooting.html">Все вопросы на одной странице</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/glossary.html">Глоссарий</a></p>
        <p><a href="https://toloka.ai/ru/docs/guide/troubleshooting/support.html">Служба поддержки</a></p>
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