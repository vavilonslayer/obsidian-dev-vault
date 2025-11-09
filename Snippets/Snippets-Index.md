# 🧰 Code Snippets

> *Коллекция полезных сниппетов и шаблонов кода*

---

## 📊 Статистика

**Всего сниппетов:** 45  
**Категорий:** 8  
**Языков:** 6

---

## 🐍 Python

### Data Science & ML
- [[Snippets/Python/Data-Loading|Data Loading & Preprocessing]]
- [[Snippets/Python/Model-Training|Model Training Template]]
- [[Snippets/Python/Visualization|Data Visualization]]

### Web Development
- [[Snippets/Python/FastAPI-Template|FastAPI Basic Template]]
- [[Snippets/Python/Flask-API|Flask REST API]]
- [[Snippets/Python/Async-Requests|Async HTTP Requests]]

### Utilities
- [[Snippets/Python/File-Operations|File Operations]]
- [[Snippets/Python/Date-Time|Date & Time Utils]]
- [[Snippets/Python/Logging|Logging Setup]]

---

## 🐳 Docker

### Dockerfiles
- [[Snippets/Docker/Python-Dockerfile|Python Multi-stage Dockerfile]]
- [[Snippets/Docker/Node-Dockerfile|Node.js Dockerfile]]
- [[Snippets/Docker/Nginx-Dockerfile|Nginx Custom Dockerfile]]

### Docker Compose
- [[Snippets/Docker/Compose-Web-App|Web App with Database]]
- [[Snippets/Docker/Compose-ML-Stack|ML Development Stack]]

---

## ☸️ Kubernetes

### Deployments
- [[Snippets/K8s/Deployment|Basic Deployment]]
- [[Snippets/K8s/StatefulSet|StatefulSet with PVC]]
- [[Snippets/K8s/DaemonSet|DaemonSet Configuration]]

### Services & Ingress
- [[Snippets/K8s/Service|Service Configurations]]
- [[Snippets/K8s/Ingress|Ingress with TLS]]

---

## 🔧 Bash/Shell

### DevOps Scripts
- [[Snippets/Bash/Deploy-Script|Deployment Script]]
- [[Snippets/Bash/Backup-Script|Backup Automation]]
- [[Snippets/Bash/Monitor-Script|System Monitoring]]

### Utilities
- [[Snippets/Bash/Git-Shortcuts|Git Shortcuts]]
- [[Snippets/Bash/Docker-Cleanup|Docker Cleanup]]

---

## 📜 JavaScript/TypeScript

### Node.js
- [[Snippets/JS/Express-Server|Express Server Setup]]
- [[Snippets/JS/Async-Patterns|Async Patterns]]

### React
- [[Snippets/JS/React-Hooks|Custom Hooks]]
- [[Snippets/JS/React-Context|Context API Setup]]

---

## 🗄️ SQL

### Queries
- [[Snippets/SQL/Complex-Joins|Complex Joins]]
- [[Snippets/SQL/Window-Functions|Window Functions]]
- [[Snippets/SQL/Performance-Tuning|Performance Optimization]]

---

## ☁️ Cloud (AWS/GCP/Azure)

### Terraform
- [[Snippets/Cloud/Terraform-EC2|EC2 Instance]]
- [[Snippets/Cloud/Terraform-S3|S3 Bucket with Policy]]

### CloudFormation
- [[Snippets/Cloud/CF-VPC|VPC Template]]

---

## 📝 Все сниппеты

```dataview
TABLE 
  language as "Язык",
  category as "Категория",
  file.ctime as "Создан"
FROM "Snippets"
WHERE file.name != "Snippets-Index"
SORT file.ctime DESC
```

---

## 🔍 По языкам

```dataview
LIST
FROM "Snippets"
WHERE file.name != "Snippets-Index"
GROUP BY language
```

---

## 🆕 Недавно добавленные

```dataview
TABLE 
  language as "Язык",
  category as "Категория"
FROM "Snippets"
WHERE file.name != "Snippets-Index"
SORT file.ctime DESC
LIMIT 10
```

---

## ⭐ Избранное

- [[Snippets/Python/Model-Training|ML Model Training Template]]
- [[Snippets/Docker/Compose-ML-Stack|ML Development Stack]]
- [[Snippets/K8s/Deployment|Kubernetes Deployment]]
- [[Snippets/Bash/Deploy-Script|Deployment Script]]

---

## 🔗 Внешние ресурсы

### Snippet Libraries
- [GitHub Gists](https://gist.github.com)
- [Carbon.now.sh](https://carbon.now.sh) - Beautiful code screenshots
- [Ray.so](https://ray.so) - Code snippet sharing

### Documentation
- [DevDocs](https://devdocs.io)
- [Cheatography](https://cheatography.com)

---

*[[Dashboard|← Назад на Dashboard]]*
