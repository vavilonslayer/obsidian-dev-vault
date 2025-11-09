# 📝 Notes

> *Общие заметки и знания*

---

## 📊 Статистика

**Всего заметок:** 127  
**Категорий:** 12  
**Последнее обновление:** `=date(today)`

---

## 🗂️ Категории

### 🤖 Machine Learning
```dataview
LIST
FROM "Notes/ML"
SORT file.name
LIMIT 10
```

### ⚙️ DevOps
```dataview
LIST
FROM "Notes/DevOps"
SORT file.name
LIMIT 10
```

### 💻 Programming
```dataview
LIST
FROM "Notes/Programming"
SORT file.name
LIMIT 10
```

### 🏗️ Architecture
```dataview
LIST
FROM "Notes/Architecture"
SORT file.name
LIMIT 10
```

---

## 🆕 Недавние заметки

```dataview
TABLE 
  file.folder as "Категория",
  file.mtime as "Изменено"
FROM "Notes"
WHERE file.name != "Notes-Index"
SORT file.mtime DESC
LIMIT 15
```

---

## 🔍 Поиск по тегам

### #concept
```dataview
LIST
FROM "Notes"
WHERE contains(tags, "concept")
LIMIT 5
```

### #tutorial
```dataview
LIST
FROM "Notes"
WHERE contains(tags, "tutorial")
LIMIT 5
```

### #best-practices
```dataview
LIST
FROM "Notes"
WHERE contains(tags, "best-practices")
LIMIT 5
```

---

## ⭐ Избранное

- [[Notes/ML/Neural-Networks-Overview|Neural Networks Overview]]
- [[Notes/DevOps/Kubernetes-Architecture|Kubernetes Architecture]]
- [[Notes/Programming/Design-Patterns|Design Patterns]]
- [[Notes/Architecture/Microservices|Microservices Architecture]]

---

## 📚 По темам

### Machine Learning
- Neural Networks
- Deep Learning
- Computer Vision
- Natural Language Processing

### DevOps
- Containerization
- Orchestration
- CI/CD
- Monitoring

### Programming
- Python
- JavaScript
- Go
- Design Patterns

### System Design
- Architecture Patterns
- Scalability
- Databases
- Distributed Systems

---

*[[Dashboard|← Назад на Dashboard]]*
