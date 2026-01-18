# Проверка настроек Mintlify

## Проблема: Mintlify не видит документацию

## Решение по шагам:

### 1. Проверьте настройки в Mintlify Dashboard

1. Откройте **Settings** → **Git settings**
2. Найдите раздел **"Repo settings"**
3. Проверьте:
   - **Repository:** должен быть `yutratkanova/docs`
   - **Branch:** должен быть `main`
   - **Set up as monorepo:** должен быть **ВКЛЮЧЕН** (ON)

### 2. Если "Set up as monorepo" выключен:

1. **Включите переключатель** "Set up as monorepo"
2. После включения появится поле **"Repository Path"** или **"Docs Path"**
3. В это поле введите: `.` (точка) - это означает корень репозитория
4. Нажмите **"Save changes"**

### 3. Проверьте файл конфигурации

В репозитории должен быть файл `mint.json` (не `docs.json`).

Проверьте что файл существует и содержит:
```json
{
  "$schema": "https://mintlify.com/schema.json",
  "name": "PandaPay Trade Platform",
  ...
}
```

### 4. После изменения настроек:

1. Нажмите кнопку **"Refresh"** в Mintlify Dashboard
2. Подождите 1-2 минуты
3. Нажмите **"Visit site"**

### 5. Если не помогло - проверьте структуру файлов

Убедитесь что в корне репозитория есть:
- ✅ `mint.json`
- ✅ `introduction.mdx`
- ✅ `quickstart.mdx`
- ✅ папки: `roles/`, `platform/`, `frontend/`, и т.д.

### 6. Альтернатива: переименовать mint.json

Если Mintlify все еще не видит `mint.json`, попробуйте:
- Переименовать `mint.json` в `mintlify.json`
- Или создать симлинк

---

## Главное действие:

**Включите "Set up as monorepo" в Git settings и укажите путь `.` (точка)**

