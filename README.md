# PandaPay Documentation

Документация для платформы PandaPay Trade Platform, созданная с помощью Mintlify.

## Структура документации

```
docs/
├── mint.json                    # Конфигурация Mintlify
├── introduction.mdx             # Главная страница
├── quickstart.mdx               # Быстрый старт
├── architecture-overview.mdx     # Обзор архитектуры
├── roles/                       # Роли пользователей
│   ├── merchant.mdx
│   ├── trader.mdx
│   ├── team-lead.mdx
│   ├── admin.mdx
│   └── super-admin.mdx
├── platform/                    # Backend API
│   ├── api-introduction.mdx
│   ├── api-authentication.mdx
│   ├── api-merchant/
│   ├── api-trader/
│   └── api-admin/
├── frontend/                    # Frontend документация
│   ├── overview.mdx
│   ├── getting-started.mdx
│   ├── admin/
│   ├── merchant/
│   ├── trader/
│   ├── team-lead/
│   └── payment-window/
├── features/                    # Функционал системы
│   └── orders.mdx
├── support/                     # Техподдержка
│   └── faq.mdx
└── technical/                   # Технические детали
```

## Настройка Mintlify

### 1. Регистрация в Mintlify

1. Перейдите на [mintlify.com](https://mintlify.com)
2. Зарегистрируйтесь или войдите
3. Создайте новый проект

### 2. Подключение репозитория

1. В настройках проекта выберите "Connect Repository"
2. Подключите ваш GitHub репозиторий
3. Укажите путь к документации: `docs/`

### 3. Настройка API ключа

1. В настройках проекта найдите "API Key"
2. Скопируйте API ключ
3. Добавьте его в GitHub Secrets:
   - Перейдите в Settings → Secrets and variables → Actions
   - Создайте новый secret: `MINTLIFY_API_KEY`
   - Вставьте скопированный API ключ

### 4. Включение AI Copilot

1. В настройках проекта найдите "AI Copilot"
2. Включите AI чат-бот
3. Настройте параметры (опционально)

### 5. Первый деплой

После настройки документация будет автоматически деплоиться при каждом push в ветку `main` или `master`.

Также можно запустить деплой вручную:
- Через GitHub Actions: Actions → Deploy to Mintlify → Run workflow
- Через Mintlify CLI: `mintlify deploy`

## Локальная разработка

### Установка Mintlify CLI

```bash
npm i -g mintlify
```

### Запуск локального сервера

```bash
cd docs
mintlify dev
```

Документация будет доступна по адресу `http://localhost:3000`

## Автоматическое обновление

Документация автоматически обновляется при каждом изменении файлов в папке `docs/` благодаря GitHub Actions workflow (`.github/workflows/mintlify-deploy.yml`).

Workflow запускается при:
- Push в ветку `main` или `master`
- Изменении файлов в папке `docs/`
- Ручном запуске через GitHub Actions

## Добавление нового контента

1. Создайте новый `.mdx` файл в соответствующей папке
2. Добавьте страницу в `mint.json` в раздел `navigation`
3. Заполните контент используя MDX синтаксис
4. Закоммитьте и запушьте изменения
5. Документация автоматически обновится

## Формат файлов

Все файлы документации должны быть в формате `.mdx` (Markdown + JSX).

### Пример страницы

```mdx
---
title: "Название страницы"
description: "Краткое описание"
---

# Заголовок

Текст с использованием **Markdown** синтаксиса.

<Card title="Карточка">
  Содержимое карточки
</Card>
```

## Полезные ссылки

- [Mintlify документация](https://mintlify.com/docs)
- [MDX документация](https://mdxjs.com/)
- [Mintlify компоненты](https://mintlify.com/docs/components/overview)

## Поддержка

Если у вас возникли вопросы по документации:
1. Проверьте [Mintlify документацию](https://mintlify.com/docs)
2. Обратитесь к команде разработки

