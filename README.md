
# 📬 Postman API Tests — JSONPlaceholder

Automated API tests for JSONPlaceholder created using Postman.

## 📁 Project Structure

```
postman-api-tests/
├── JSONPlaceholder.postman_collection.json   # Collection of API requests
├── jsonplaceholder_env.postman_environment.json   # Environment with variables
└── .github/
    └── workflows/
        └── postman-tests.yml                 # CI config for GitHub Actions
```

## ✅ Covered Scenarios

- `GET /posts` — list of posts
- `GET /posts/1` — single post
- `GET /comments?postId=1` — comments for a post
- Basic tests include:
  - Status code verification
  - Response type (array, object)
  - Field existence and values
- Use of environment variables ({{base_url}}, {{post_id}})

## 🧪 Run Locally with Newman

```bash
newman run JSONPlaceholder.postman_collection.json   -e jsonplaceholder_env.postman_environment.json   -r cli,html   --reporter-html-export report.html
```

## ⚙️ CI: GitHub Actions

The collection is automatically executed on every push to the main branch.
Results are stored as an HTML report in CI artifacts.

## 📄 Report

Open the `report.html` file in your browser to view the results.

## 📦 Dependencies

- [Postman](https://www.postman.com/)
- [Newman](https://github.com/postmanlabs/newman)
- HTML reporter: `npm install -g newman-reporter-html`

---

📁 *This project is part of a QA engineer's portfolio focused on REST API testing.*
