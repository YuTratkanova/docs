# СРОЧНОЕ ВОССТАНОВЛЕНИЕ

## Проблема: Mintlify не видит документацию

## Решение по шагам:

### Шаг 1: Проверьте настройки в Mintlify

1. Откройте Mintlify Dashboard → **Settings** → **Git settings**
2. **ОТКЛЮЧИТЕ** "Set up as monorepo" (переключатель должен быть OFF)
3. Нажмите **"Save changes"**

### Шаг 2: Проверьте что mint.json в корне репозитория

Файл `mint.json` должен быть в корне (рядом с README.md)

### Шаг 3: Убедитесь что все файлы запушены

Выполните:
```bash
cd ~/docs
git add .
git commit -m "Fix documentation"
git push
```

### Шаг 4: В Mintlify нажмите Refresh

После push подождите 2 минуты и нажмите кнопку **Refresh** в Dashboard

---

## Если не помогло:

### Вариант A: Переименуйте mint.json в docs.json

Mintlify может искать `docs.json` вместо `mint.json`:

```bash
cd ~/docs
cp mint.json docs.json
git add docs.json
git commit -m "Add docs.json for compatibility"
git push
```

### Вариант B: Проверьте путь к репозиторию

В Settings → Git settings убедитесь:
- Repository: `yutratkanova/docs`
- Branch: `main`
- Path: ПУСТОЕ (если "Set up as monorepo" выключен)

---

## Проверка что работает:

1. Откройте: https://github.com/YuTratkanova/docs/blob/main/mint.json
2. Файл должен открыться
3. Если открывается - проблема в настройках Mintlify
4. Если не открывается - нужно пушить файлы

