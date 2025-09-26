# 🚀 MINIMAL Railway Setup

## ✅ Текущая конфигурация:

### Файлы:
- `Procfile` → `web: python main.py`  
- `main.py` → простая точка входа с uvicorn
- `runtime.txt` → `3.11` (версия Python)
- `requirements.txt` → минимальные зависимости

### Что удалено:
- ❌ `railway.json` 
- ❌ `nixpacks.toml`
- ❌ `Dockerfile.railway`
- ❌ `start.sh`
- ❌ `server.py`

## 🎯 Деплой на Railway:

1. Заходим на [railway.app](https://railway.app)
2. New Project → Deploy from GitHub repo
3. Выбираем `beka4kaa/lea`
4. Railway автоматически:
   - Обнаружит Python проект
   - Установит Python 3.11 из `runtime.txt`
   - Установит зависимости из `requirements.txt`
   - Запустит `python main.py` из `Procfile`

## 🔍 Почему это должно работать:

- **Стандартный подход** - Railway отлично поддерживает Procfile
- **Нет кастомных скриптов** - только Python и uvicorn
- **Минимальные зависимости** - меньше места для ошибок
- **Прямой импорт** - main.py напрямую импортирует app

## 📋 Health Check:

После деплоя проверить:
- `/health` - должен вернуть статус
- `/` - корневой endpoint с информацией

Railway больше НЕ должен искать `start.sh`! 🎉