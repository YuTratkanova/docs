# Инструкция по настройке Mintlify для общего репозитория

## Структура репозитория

Ваш репозиторий имеет следующую структуру:
```
PandaPay/ (корень репозитория)
├── docs/                    ← Документация находится здесь
│   ├── mint.json
│   ├── introduction.mdx
│   └── ...
├── Trade-Platform-main/     ← Backend
│   └── docs/
│       └── swagger.yaml     ← Swagger файл
└── Trade-Frontend-main/     ← Frontend
```

## Настройка в Mintlify

### 1. Настройка путей в Mintlify Dashboard

В настройках проекта Mintlify укажите:

**Repository Path:** `docs/`

Это означает, что Mintlify будет использовать папку `docs/` как корень документации.

**Mintlify config file:** `docs/mint.json` (или оставьте пустым, Mintlify найдет автоматически)

### 2. Проверка пути к Swagger

В файле `mint.json` путь к Swagger указан как:
```json
"openapi": "../Trade-Platform-main/docs/swagger.yaml"
```

Это **относительный путь от папки `docs/`**.

Если это не работает, можно:

**Вариант 1:** Скопировать swagger.yaml в папку docs
```bash
cp Trade-Platform-main/docs/swagger.yaml docs/swagger.yaml
```

И изменить в `mint.json`:
```json
"openapi": "swagger.yaml"
```

**Вариант 2:** Использовать абсолютный путь (если репозиторий подключен правильно)
```json
"openapi": "Trade-Platform-main/docs/swagger.yaml"
```

### 3. GitHub Actions Workflow

Файл `.github/workflows/mintlify-deploy.yml` должен находиться в **корне репозитория** (это правильно).

Workflow будет запускаться при изменении файлов в папке `docs/`.

### 4. Первый деплой

После настройки:

1. **Добавьте MINTLIFY_API_KEY в GitHub Secrets:**
   - Settings → Secrets and variables → Actions
   - New repository secret
   - Name: `MINTLIFY_API_KEY`
   - Value: ваш API ключ из Mintlify

2. **Проверьте настройки в Mintlify:**
   - Repository: ваш репозиторий
   - Repository Path: `docs/`
   - Branch: `main` (или `master`)

3. **Сделайте commit и push:**
   ```bash
   git add docs/
   git commit -m "Add documentation"
   git push
   ```

4. **Проверьте GitHub Actions:**
   - Перейдите в Actions в GitHub
   - Убедитесь, что workflow запустился
   - Проверьте, что деплой прошел успешно

### 5. Проверка документации

После деплоя:
- Откройте ваш сайт документации в Mintlify
- Проверьте, что все страницы отображаются
- Убедитесь, что Swagger API подключен

## Возможные проблемы

### Проблема: Mintlify не находит файлы

**Решение:** Убедитесь, что в настройках указан правильный путь `docs/`

### Проблема: Swagger не подключается

**Решение:** 
1. Проверьте путь в `mint.json`
2. Попробуйте скопировать `swagger.yaml` в папку `docs/`

### Проблема: GitHub Actions не запускается

**Решение:**
1. Убедитесь, что файл `.github/workflows/mintlify-deploy.yml` существует
2. Проверьте, что `MINTLIFY_API_KEY` добавлен в Secrets
3. Проверьте синтаксис YAML файла

## Контакты

Если возникли проблемы:
- Проверьте логи GitHub Actions
- Проверьте настройки в Mintlify Dashboard
- Обратитесь к документации Mintlify: https://mintlify.com/docs

