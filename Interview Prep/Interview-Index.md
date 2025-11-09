# 🧠 Interview Preparation

> *Подготовка к техническим собеседованиям*

---

## 📊 Общий прогресс

![Interview Progress](https://progress-bar.dev/25/?title=Interview%20Ready&width=300&color=6554c0)

**Изучено вопросов:** 50 / 170  
**Решено задач:** 35 / 150

---

## 📚 Категории

### 🔢 Алгоритмы и структуры данных

**Прогресс:** ![progress](https://progress-bar.dev/30/)

#### Arrays & Strings
- [ ] Two Pointers
- [ ] Sliding Window
- [ ] String Manipulation

#### Linked Lists
- [ ] Reverse Linked List
- [ ] Detect Cycle
- [ ] Merge Lists

#### Trees & Graphs
- [ ] BFS / DFS
- [ ] Binary Search Tree
- [ ] Graph Traversal

#### Dynamic Programming
- [ ] Fibonacci variations
- [ ] Knapsack problems
- [ ] Longest subsequence

---

### 🏗️ System Design

**Прогресс:** ![progress](https://progress-bar.dev/25/)

#### Основы
- [ ] Scalability concepts
- [ ] Load Balancing
- [ ] Caching strategies
- [ ] Database sharding

#### Компоненты
- [ ] API Gateway
- [ ] Message Queues
- [ ] CDN
- [ ] Microservices

#### Паттерны
- [ ] Event-driven architecture
- [ ] CQRS
- [ ] Saga pattern

---

### 🤖 Machine Learning Questions

**Прогресс:** ![progress](https://progress-bar.dev/33/)

#### Теория
- [ ] Bias-Variance tradeoff
- [ ] Overfitting / Underfitting
- [ ] Cross-validation
- [ ] Feature engineering

#### Модели
- [ ] Linear Regression
- [ ] Decision Trees
- [ ] Neural Networks
- [ ] Ensemble methods

---

### ⚙️ DevOps Questions

**Прогресс:** ![progress](https://progress-bar.dev/25/)

#### Контейнеризация
- [ ] Docker concepts
- [ ] Container orchestration
- [ ] Kubernetes architecture

#### CI/CD
- [ ] Pipeline design
- [ ] Deployment strategies
- [ ] Testing automation

---

## 📝 Вопросы по сложности

### 🟢 Легкие (75% освоено)
```dataview
TABLE 
  category as "Категория",
  mastery as "Освоение"
FROM "Interview Prep"
WHERE difficulty = "easy" AND file.name != "Interview-Index"
SORT mastery DESC
LIMIT 10
```

### 🟡 Средние (40% освоено)
```dataview
TABLE 
  category as "Категория",
  mastery as "Освоение"
FROM "Interview Prep"
WHERE difficulty = "medium" AND file.name != "Interview-Index"
SORT mastery DESC
LIMIT 10
```

### 🔴 Сложные (10% освоено)
```dataview
TABLE 
  category as "Категория",
  mastery as "Освоение"
FROM "Interview Prep"
WHERE difficulty = "hard" AND file.name != "Interview-Index"
SORT mastery DESC
LIMIT 10
```

---

## 🎯 План подготовки

### Неделя 1-2: Алгоритмы
- [ ] Arrays & Strings (20 задач)
- [ ] Linked Lists (10 задач)
- [ ] Trees (15 задач)

### Неделя 3-4: System Design
- [ ] 5 популярных систем
- [ ] Паттерны проектирования
- [ ] Trade-offs

### Неделя 5-6: ML & DevOps
- [ ] ML вопросы (30 вопросов)
- [ ] DevOps концепции (20 вопросов)

---

## 📊 Статистика

### По категориям
| Категория | Изучено | Всего | % |
|-----------|---------|-------|---|
| Algorithms | 15 | 50 | 30% |
| System Design | 5 | 20 | 25% |
| ML Questions | 20 | 60 | 33% |
| DevOps | 10 | 40 | 25% |

### Последние добавленные
```dataview
TABLE 
  category as "Категория",
  difficulty as "Сложность",
  mastery as "Освоение"
FROM "Interview Prep"
WHERE file.name != "Interview-Index"
SORT file.ctime DESC
LIMIT 5
```

---

## 🔗 Ресурсы

### Практика
- [LeetCode](https://leetcode.com)
- [HackerRank](https://hackerrank.com)
- [CodeSignal](https://codesignal.com)
- [Pramp](https://pramp.com)

### System Design
- [System Design Primer](https://github.com/donnemartin/system-design-primer)
- [Grokking System Design](https://www.educative.io/courses/grokking-the-system-design-interview)

### Книги
- Cracking the Coding Interview
- Elements of Programming Interviews
- Designing Data-Intensive Applications

---

## 💡 Tips

- Решать по 2-3 задачи ежедневно
- Повторять пройденные через spaced repetition
- Mock interviews раз в неделю
- Объяснять решения вслух

---

*[[Dashboard|← Назад на Dashboard]]*
