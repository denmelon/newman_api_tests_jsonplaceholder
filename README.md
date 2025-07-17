
# 📬 Postman API Tests — JSONPlaceholder

Автоматизированные API-тесты для [JSONPlaceholder](https://jsonplaceholder.typicode.com), созданные в Postman.

## 📁 Структура проекта

```
postman-api-tests/
├── JSONPlaceholder.postman_collection.json   # Коллекция запросов
├── jsonplaceholder_env.postman_environment.json   # Окружение с переменными
└── .github/
    └── workflows/
        └── postman-tests.yml                 # CI для запуска через GitHub Actions
```

## ✅ Что покрыто

- `GET /posts` — список постов
- `GET /posts/1` — отдельный пост
- `GET /comments?postId=1` — комментарии к посту
- Базовые проверки:
  - Статус-код
  - Тип данных (массив, объект)
  - Поля ответа
- Использование переменных (`{{base_url}}`, `{{post_id}}`)

## 🧪 Запуск локально через Newman

```bash
newman run JSONPlaceholder.postman_collection.json   -e jsonplaceholder_env.postman_environment.json   -r cli,html   --reporter-html-export report.html
```

## ⚙️ CI: GitHub Actions

Коллекция автоматически запускается при каждом push в ветку `main`.  
Результаты доступны как HTML-отчёт в артефактах CI.

## 📄 Отчёт

Файл `report.html` можно открыть в браузере.

## 📦 Зависимости

- [Postman](https://www.postman.com/)
- [Newman](https://github.com/postmanlabs/newman)
- HTML-репортёр: `npm install -g newman-reporter-html`

---

📁 *Проект создан в рамках портфолио QA-инженера. Основа — практика тестирования REST API.*
