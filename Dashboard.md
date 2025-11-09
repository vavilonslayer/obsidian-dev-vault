# 🏠 Developer Dashboard

> *Добро пожаловать в твое продуктивное пространство!*  
> 📅 **Сегодня:** `=date(today)`

---

## 🎯 Текущие цели

- [ ] Завершить курс по Machine Learning
- [ ] Развернуть CI/CD pipeline для проекта
- [ ] Подготовиться к собеседованию по алгоритмам
- [ ] Изучить новые инструменты DevOps

---

## 📊 Общий прогресс

### 📘 Прогресс по курсам
- **Machine Learning:** ![progress](https://progress-bar.dev/70/?title=ML&width=200&color=4c9aff)
- **DevOps:** ![progress](https://progress-bar.dev/45/?title=DevOps&width=200&color=36b37e)
- **Python Advanced:** ![progress](https://progress-bar.dev/85/?title=Python&width=200&color=ff5630)

### 💻 Активные проекты
- **Project A** 🟢 80% - ML Image Classification
- **Project B** 🟡 45% - K8s Deployment Pipeline
- **Project C** 🔴 10% - Data Pipeline Automation

### 🔄 Подготовка к собеседованиям
![progress](https://progress-bar.dev/25/?title=Interview%20Prep&width=180&color=6554c0)

---

## 🗂️ Быстрые ссылки

### 📚 Обучение
- [[Courses/ML/ML-Index|🤖 Machine Learning]]
- [[Courses/DevOps/DevOps-Index|⚙️ DevOps Engineering]]
- [[Interview Prep/Interview-Index|🧠 Interview Preparation]]

### 💻 Разработка
- [[Projects/Projects-Index|📁 Мои проекты]]
- [[Snippets/Snippets-Index|🧰 Code Snippets]]
- [[Notes/Notes-Index|📝 Заметки]]

### 📈 Аналитика
- [[Dashboard/Progress|📊 Детальный прогресс]]
- [[Dashboard/Weekly-Review|📅 Недельный обзор]]

---

## 📅 Сегодня

### ✅ Задачи на день
```dataview
TASK
FROM "Projects" OR "Courses"
WHERE !completed
LIMIT 5
```

### 📝 Недавние заметки
```dataview
TABLE file.mtime as "Изменено"
FROM "Notes" OR "Courses"
SORT file.mtime DESC
LIMIT 5
```

---

## 🎨 Секции

### 📚 Курсы
Изучаю новые технологии и совершенствую навыки
- [[Courses/ML/ML-Index|Machine Learning]] - Глубокое обучение, нейросети
- [[Courses/DevOps/DevOps-Index|DevOps]] - Kubernetes, Docker, CI/CD

### 💻 Проекты
Мои текущие и завершенные проекты
- [[Projects/Projects-Index|Все проекты]]

### ⚙️ DevOps
Инфраструктура, автоматизация, мониторинг
- Docker & Kubernetes
- CI/CD Pipelines
- Infrastructure as Code

### 🤖 Machine Learning
ML модели, эксперименты, датасеты
- Neural Networks
- Computer Vision
- NLP

### 🧠 Интервью
Подготовка к техническим собеседованиям
- [[Interview Prep/Interview-Index|База вопросов]]
- Алгоритмы и структуры данных
- System Design

---

## 📊 Статистика

```dataview
TABLE 
  length(file.tasks) as "Всего задач",
  length(filter(file.tasks, (t) => t.completed)) as "Выполнено"
FROM "Projects" OR "Courses"
```

---

*Последнее обновление: `=date(today)`*
