# Решение проблемы "Failed to fetch file paths"

## Проблема сохраняется - что делать дальше

### 1. Проверьте файлы на GitHub

Откройте: https://github.com/YuTratkanova/docs

Убедитесь что видны:
- `mint.json`
- `introduction.mdx`
- Папки: `roles/`, `platform/`, `frontend/` и т.д.

Если файлов нет - сделайте push!

### 2. Попробуйте отключить "Set up as monorepo"

1. Settings → Git settings
2. **Выключите** переключатель "Set up as monorepo" (OFF)
3. Нажмите "Save changes"
4. Подождите 1-2 минуты
5. Проверьте результат

### 3. Проверьте что mint.json валидный

Откройте файл `mint.json` и убедитесь что:
- Нет синтаксических ошибок
- Все пути в `navigation` правильные (без `.mdx` в конце)

### 4. Попробуйте пересоздать проект

Если ничего не помогает:
1. В Mintlify Dashboard найдите настройки проекта
2. Попробуйте отвязать и снова подключить репозиторий

### 5. Альтернатива - используйте mintlify.json

Создайте копию `mint.json` как `mintlify.json`:

```bash
cd ~/docs
cp mint.json mintlify.json
git add mintlify.json
git commit -m "Add mintlify.json"
git push
```

---

## Что проверить прямо сейчас:

1. ✅ Файлы запушены на GitHub?
2. ✅ Путь в настройках правильный? (попробуйте пустое поле)
3. ✅ "Set up as monorepo" включен или выключен?

