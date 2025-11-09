# 💻 Projects

> *Мои проекты и разработки*

---

## 📊 Общая статистика

**Всего проектов:** 8  
**Активных:** 3  
**Завершенных:** 5

---

## 🟢 Активные проекты

### Project A: ML Image Classification
**Статус:** В работе  
**Прогресс:** ![progress](https://progress-bar.dev/80/?width=200)  
**Приоритет:** 🔴 Высокий

[[Projects/ML-Image-Classification|→ Открыть проект]]

---

### Project B: K8s Deployment Pipeline
**Статус:** В процессе  
**Прогресс:** ![progress](https://progress-bar.dev/45/?width=200)  
**Приоритет:** 🟡 Средний

[[Projects/K8s-Deployment-Pipeline|→ Открыть проект]]

---

### Project C: Data Pipeline Automation
**Статус:** Начато  
**Прогресс:** ![progress](https://progress-bar.dev/10/?width=200)  
**Приоритет:** 🟢 Низкий

[[Projects/Data-Pipeline-Automation|→ Открыть проект]]

---

## ✅ Завершенные проекты

```dataview
TABLE 
  status as "Статус",
  progress as "Прогресс",
  completion-date as "Завершен"
FROM "Projects"
WHERE status = "completed"
SORT completion-date DESC
```

---

## 📋 Все проекты

```dataview
TABLE 
  status as "Статус",
  progress as "Прогресс",
  priority as "Приоритет",
  tags as "Теги"
FROM "Projects"
WHERE file.name != "Projects-Index"
SORT priority DESC, progress DESC
```

---

## 🏷️ По технологиям

### 🤖 Machine Learning
- ML Image Classification
- NLP Sentiment Analysis
- Recommendation System

### ⚙️ DevOps
- K8s Deployment Pipeline
- CI/CD Automation
- Infrastructure as Code

### 🐍 Python
- Data Pipeline Automation
- API Service
- ETL Framework

### 🌐 Web Development
- Portfolio Website
- Dashboard App

---

## 📈 Метрики

| Проект | Commits | Issues | PRs | Status |
|--------|---------|--------|-----|--------|
| Project A | 145 | 12 | 34 | 🟢 |
| Project B | 89 | 8 | 21 | 🟡 |
| Project C | 23 | 5 | 7 | 🔴 |

---

## 🎯 Roadmap

### Q1 2024
- [ ] Завершить Project A
- [ ] Развернуть Project B в production
- [ ] Начать новый ML проект

### Q2 2024
- [ ] Оптимизировать Project A
- [ ] Добавить мониторинг в Project B
- [ ] Завершить Project C

---

## 💡 Идеи для будущих проектов

- [ ] Real-time Object Detection System
- [ ] Automated Code Review Tool
- [ ] Personal Knowledge Graph
- [ ] Multi-cloud Deployment Manager

---

## 🔗 Ресурсы

### Репозитории
- [GitHub Profile](https://github.com/username)
- [GitLab](https://gitlab.com/username)

### Документация
- [[Notes/Project-Management|Project Management]]
- [[Notes/Best-Practices|Best Practices]]

---

*[[Dashboard|← Назад на Dashboard]]*
