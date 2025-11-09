# 📊 Progress Dashboard

> *Детальная аналитика и визуализация прогресса*

---

## 🎯 Общий обзор

### 📈 Прогресс по основным направлениям

**Machine Learning:**  
![ML Progress](https://progress-bar.dev/70/?title=ML%20Mastery&width=300&color=4c9aff)

**DevOps Engineering:**  
![DevOps Progress](https://progress-bar.dev/45/?title=DevOps%20Skills&width=300&color=36b37e)

**Interview Preparation:**  
![Interview Progress](https://progress-bar.dev/25/?title=Interview%20Ready&width=300&color=6554c0)

**Overall Development:**  
![Overall Progress](https://progress-bar.dev/55/?title=Overall&width=300&color=00b8d9)

---

## 💻 Проекты

### Статус проектов

| Проект | Статус | Прогресс | Приоритет |
|--------|--------|----------|-----------|
| ML Image Classification | 🟢 В работе | ![](https://progress-bar.dev/80/) | Высокий |
| K8s Deployment Pipeline | 🟡 В процессе | ![](https://progress-bar.dev/45/) | Средний |
| Data Pipeline Automation | 🔴 Начато | ![](https://progress-bar.dev/10/) | Низкий |

### Детали проектов

```dataview
TABLE 
  status as "Статус",
  progress as "Прогресс",
  priority as "Приоритет"
FROM "Projects"
WHERE file.name != "Projects-Index"
SORT priority DESC
```

---

## 📚 Курсы

### Прогресс обучения

**Machine Learning Course:**
- Всего модулей: 10
- Завершено: 7
- ![](https://progress-bar.dev/70/?scale=10&suffix=/10)

**DevOps Engineering:**
- Всего модулей: 15
- Завершено: 7
- ![](https://progress-bar.dev/45/?scale=15&suffix=/15)

**Python Advanced:**
- Всего модулей: 12
- Завершено: 10
- ![](https://progress-bar.dev/85/?scale=12&suffix=/12)

### Детальная статистика

```dataview
TABLE 
  progress as "Прогресс",
  source as "Источник",
  completed-modules as "Завершено"
FROM "Courses/ML" OR "Courses/DevOps"
WHERE file.name != "ML-Index" AND file.name != "DevOps-Index"
```

---

## 🧠 Подготовка к собеседованиям

### Прогресс по категориям

| Категория | Изучено | Всего | Прогресс |
|-----------|---------|-------|----------|
| Алгоритмы | 15 | 50 | ![](https://progress-bar.dev/30/) |
| System Design | 5 | 20 | ![](https://progress-bar.dev/25/) |
| ML Вопросы | 20 | 60 | ![](https://progress-bar.dev/33/) |
| DevOps Вопросы | 10 | 40 | ![](https://progress-bar.dev/25/) |

### Сложность вопросов

- 🟢 **Легкие:** 25 вопросов (75% освоено)
- 🟡 **Средние:** 15 вопросов (40% освоено)
- 🔴 **Сложные:** 10 вопросов (10% освоено)

---

## 📈 Временная аналитика

### Время обучения (последние 7 дней)

| День | ML | DevOps | Interview | Проекты | Итого |
|------|-----|--------|-----------|---------|-------|
| Пн | 2ч | 1ч | 0.5ч | 3ч | 6.5ч |
| Вт | 1.5ч | 2ч | 1ч | 2ч | 6.5ч |
| Ср | 2ч | 1ч | 0.5ч | 3ч | 6.5ч |
| Чт | 1ч | 2.5ч | 1ч | 2ч | 6.5ч |
| Пт | 2ч | 1ч | 1ч | 3ч | 7ч |
| Сб | 3ч | 2ч | 2ч | 4ч | 11ч |
| Вс | 2.5ч | 1.5ч | 1.5ч | 3ч | 8.5ч |

**Среднее время в день:** 7.5 часов

### Распределение по категориям (за неделю)

- 🤖 Machine Learning: 28% (14ч)
- ⚙️ DevOps: 22% (11ч)
- 🧠 Interview Prep: 15% (7.5ч)
- 💻 Проекты: 35% (20ч)

---

## 🎯 Цели и достижения

### Текущий месяц

- [x] Начать курс по ML
- [x] Создать первый проект с Docker
- [x] Изучить основы Kubernetes
- [ ] Завершить 50% курса по ML
- [ ] Развернуть production-ready CI/CD
- [ ] Решить 30 задач на алгоритмы

### Достижения

- ✅ **Неделя 1:** Освоены основы Neural Networks
- ✅ **Неделя 2:** Создан первый Docker compose проект
- ✅ **Неделя 3:** Развернут K8s кластер локально
- 🎯 **Неделя 4:** В процессе - Advanced ML topics

---

## 📊 Dataview Queries

### Все активные задачи

```dataview
TASK
WHERE !completed
GROUP BY file.folder
```

### Последние обновления

```dataview
TABLE 
  file.mtime as "Последнее изменение",
  file.folder as "Раздел"
FROM ""
WHERE file.name != "Progress"
SORT file.mtime DESC
LIMIT 10
```

---

*Обновлено: `=date(today)`*
