# 🚀 Railway Deployment - Final Configuration

## ✅ Current Setup:

1. **Procfile** - Railway будет использовать этот файл для запуска:
   ```
   web: python3 -m uvicorn mcp_ui_aggregator.api.app:app --host 0.0.0.0 --port $PORT
   ```

2. **nixpacks.toml** - Настройки сборки:
   ```toml
   [phases.setup]
   nixPkgs = ['python311', 'pip']
   
   [phases.install]
   cmds = ['pip install -r requirements.txt']
   ```

3. **railway.json** - Конфигурация платформы с health check

## 🎯 Как задеплоить:

1. **На Railway:**
   - Зайти на [railway.app](https://railway.app)
   - New Project → Deploy from GitHub repo
   - Выбрать репозиторий `beka4kaa/lea`

2. **Railway автоматически:**
   - Обнаружит Python проект
   - Использует `nixpacks.toml` для сборки
   - Запустит команду из `Procfile`
   - Применит настройки из `railway.json`

## 🔍 Что изменилось:

- ✅ Убрали все bash скрипты
- ✅ Используем стандартный uvicorn запуск
- ✅ Procfile для определения команды запуска
- ✅ Минимальная конфигурация nixpacks
- ✅ Фиксированные версии в requirements.txt

## 📋 Файлы для деплоя:

- `Procfile` - команда запуска
- `requirements.txt` - зависимости Python
- `nixpacks.toml` - настройки сборки
- `railway.json` - конфигурация Railway
- `.railwayignore` - исключения

Теперь Railway должен успешно собрать и запустить проект! 🎉