# 📊 Визуализация структуры хранилища

> Визуальное представление структуры Obsidian Dev Vault

---

## 🗂️ Полная структура файлов

```
obsidian-dev-vault/
│
├── 📄 Dashboard.md                    # 🏠 Главная страница с визуальными элементами
├── 📄 README.md                       # 📖 Документация проекта
├── 📄 SETUP.md                        # ⚙️ Инструкция по установке
├── 📄 QUICK-REFERENCE.md              # ⚡ Быстрая справка
│
├── 📁 Dashboard/                      # Дашборды и аналитика
│   ├── Progress.md                    # 📊 Детальная аналитика прогресса
│   ├── Weekly-Review.md               # 📅 Еженедельный обзор
│   └── Daily/                         # 📆 Ежедневные заметки (создаются автоматически)
│
├── 📁 Courses/                        # Курсы и обучение
│   ├── ML/                            # 🤖 Machine Learning
│   │   ├── ML-Index.md                # Индекс ML курсов
│   │   └── Deep-Learning.md           # Пример: Deep Learning Specialization
│   │
│   └── DevOps/                        # ⚙️ DevOps Engineering
│       ├── DevOps-Index.md            # Индекс DevOps курсов
│       └── Kubernetes-Deep-Dive.md    # Пример: Kubernetes курс
│
├── 📁 Projects/                       # Проекты
│   ├── Projects-Index.md              # Индекс проектов
│   └── ML-Image-Classification.md     # Пример: ML проект
│
├── 📁 Interview Prep/                 # Подготовка к интервью
│   ├── Interview-Index.md             # Индекс вопросов
│   ├── Two-Sum-Problem.md             # Пример: Алгоритм
│   └── Blue-Green-Deployment.md       # Пример: DevOps вопрос
│
├── 📁 Snippets/                       # Code Snippets
│   ├── Snippets-Index.md              # Индекс сниппетов
│   └── PyTorch-Training-Template.md   # Пример: PyTorch шаблон
│
├── 📁 Notes/                          # Общие заметки
│   ├── Notes-Index.md                 # Индекс заметок
│   ├── ML/                            # ML концепции
│   │   └── Gradient-Descent.md        # Пример: ML заметка
│   ├── DevOps/                        # DevOps концепции
│   │   └── Kubernetes-Architecture.md # Пример: DevOps заметка
│   └── Programming/                   # Программирование
│
├── 📁 Templates/                      # Шаблоны
│   ├── Template-Course.md             # Шаблон курса
│   ├── Template-Project.md            # Шаблон проекта
│   ├── Template-Interview.md          # Шаблон вопроса интервью
│   ├── Template-Snippet.md            # Шаблон сниппета
│   └── Template-Daily-Note.md         # Шаблон дневной заметки
│
├── 📁 Assets/                         # Медиа файлы
│   └── Images/                        # 🖼️ Изображения (автоматическое хранение)
│
└── 📁 .obsidian/                      # Конфигурация Obsidian
    ├── config                         # Основные настройки
    ├── appearance.json                # Настройки темы
    ├── community-plugins.json         # Список плагинов
    ├── daily-notes.json               # Конфигурация daily notes
    │
    ├── plugins/                       # Плагины
    │   ├── dataview/                  # Dataview конфигурация
    │   │   └── data.json
    │   ├── templater-obsidian/        # Templater конфигурация
    │   │   └── data.json
    │   └── quickadd/                  # QuickAdd конфигурация
    │
    ├── snippets/                      # CSS сниппеты
    │   └── custom-styles.css          # Кастомные стили
    │
    └── themes/                        # Темы оформления
```

---

## 🎯 Основные секции

### 🏠 Dashboard (Главная)
**Файл:** `Dashboard.md`

**Содержит:**
- Приветствие и текущая дата
- Общий прогресс (progress bars)
- Текущие цели
- Быстрые ссылки на разделы
- Статистика (Dataview queries)
- Недавние заметки

**Связанные:**
- `Dashboard/Progress.md` - детальная аналитика
- `Dashboard/Weekly-Review.md` - еженедельные обзоры

---

### 📚 Courses (Курсы)

```
Courses/
├── ML/
│   ├── ML-Index.md                 # Обзор ML курсов
│   ├── Deep-Learning.md            # Пример курса
│   ├── Computer-Vision.md          # Добавьте свои
│   └── NLP.md                      # курсы
│
└── DevOps/
    ├── DevOps-Index.md             # Обзор DevOps курсов
    ├── Kubernetes-Deep-Dive.md     # Пример курса
    ├── Docker-Mastery.md           # Добавьте свои
    └── CI-CD-Pipeline.md           # курсы
```

**Каждый курс содержит:**
- Progress tracking
- Конспекты по модулям
- Примеры кода
- Практические задания
- Ресурсы и ссылки

---

### 💻 Projects (Проекты)

```
Projects/
├── Projects-Index.md               # Обзор всех проектов
├── ML-Image-Classification.md      # ML проект
├── K8s-Deployment-Pipeline.md      # DevOps проект
└── Data-Pipeline-Automation.md     # Data проект
```

**Каждый проект содержит:**
- Архитектура и технологии
- TODO и прогресс
- Документация
- Code examples
- Deployment инструкции

---

### 🧠 Interview Prep (Интервью)

```
Interview Prep/
├── Interview-Index.md              # Обзор по категориям
├── Algorithms/
│   ├── Two-Sum-Problem.md
│   ├── Binary-Search.md
│   └── ...
├── System-Design/
│   └── ...
├── ML-Questions/
│   └── ...
└── DevOps/
    ├── Blue-Green-Deployment.md
    └── ...
```

**Каждый вопрос содержит:**
- Формулировка вопроса
- Развернутый ответ
- Примеры кода
- Follow-up вопросы
- Mastery tracking

---

### 🧰 Snippets (Сниппеты)

```
Snippets/
├── Snippets-Index.md               # Индекс по языкам
├── Python/
│   ├── PyTorch-Training-Template.md
│   ├── Data-Loading.md
│   └── ...
├── Docker/
│   └── ...
├── Kubernetes/
│   └── ...
└── Bash/
    └── ...
```

**Каждый сниппет содержит:**
- Готовый код
- Описание и use cases
- Примеры использования
- Dependencies

---

### 📝 Notes (Заметки)

```
Notes/
├── Notes-Index.md                  # Индекс заметок
├── ML/
│   ├── Gradient-Descent.md
│   ├── Neural-Networks.md
│   └── ...
├── DevOps/
│   ├── Kubernetes-Architecture.md
│   ├── Docker-Networking.md
│   └── ...
├── Programming/
│   └── ...
└── Architecture/
    └── ...
```

**Каждая заметка:**
- Объясняет концепцию
- Содержит примеры
- Связана с другими заметками
- Имеет tags для поиска

---

## 🔄 Информационные потоки

### От изучения к применению

```
📚 Courses          →    📝 Notes          →    💻 Projects
(Обучение)              (Концепции)            (Применение)
    ↓                       ↓                       ↓
Deep Learning.md    →   Neural-Networks.md  →  ML-Image-Classification.md
```

### Подготовка к интервью

```
📚 Courses          →    📝 Notes          →    🧠 Interview Prep
(Изучение)              (Понимание)            (Проверка знаний)
    ↓                       ↓                       ↓
K8s Course.md       →   K8s-Architecture.md →  Blue-Green-Deployment.md
```

### Создание базы знаний

```
💻 Projects         →    🧰 Snippets       →    📝 Notes
(Практика)              (Переиспользование)    (Документирование)
    ↓                       ↓                       ↓
ML Project          →   PyTorch-Template   →   Best-Practices.md
```

---

## 📊 Использование Dataview

### Автоматические списки

**В Dashboard.md:**
```dataview
LIST FROM "Projects" WHERE status = "active"
```

**В Progress.md:**
```dataview
TABLE progress, status FROM "Courses"
```

**В Interview-Index.md:**
```dataview
TABLE difficulty, mastery FROM "Interview Prep"
```

---

## 🎨 Визуальные элементы

### Progress Bars (на всех уровнях)

**Dashboard:**
- Общий прогресс по направлениям
- Прогресс по проектам
- Interview preparation

**Course Pages:**
- Прогресс прохождения курса
- Прогресс по модулям

**Project Pages:**
- Прогресс выполнения проекта
- Completion по задачам

**Interview Questions:**
- Mastery level вопроса

---

## 🔗 Взаимосвязи

### Типы связей

**1. Навигационные (Index → Content)**
```
ML-Index.md → Deep-Learning.md → Gradient-Descent.md
```

**2. Концептуальные (Related Topics)**
```
Neural-Networks.md ↔ Deep-Learning.md ↔ Backpropagation.md
```

**3. Практические (Theory → Practice)**
```
K8s-Architecture.md → K8s-Deep-Dive.md → K8s-Project.md
```

---

## 💡 Best Practices

### Организация файлов

1. **Index files** в каждой папке
2. **Templates** для consistency
3. **Tags** для cross-cutting concerns
4. **Links** для связи концепций

### Naming conventions

- `Category-Topic.md` для заметок
- `Template-Type.md` для шаблонов
- `Category-Index.md` для индексов

### Maintenance

- Регулярно обновлять progress bars
- Использовать Daily Notes
- Еженедельные reviews
- Архивировать завершенное

---

## 🎯 Путь пользователя

### Новый пользователь

1. **Start:** `Dashboard.md`
2. **Setup:** `SETUP.md`
3. **Learn:** `QUICK-REFERENCE.md`
4. **Create:** Использовать Templates

### Ежедневное использование

1. **Утро:** Daily Note
2. **Работа:** Update Projects/Courses
3. **Вечер:** Update progress in Dashboard
4. **Неделя:** Weekly Review

### Рост и развитие

```
Start → Learn → Practice → Master → Share
  ↓       ↓        ↓         ↓        ↓
 Read   Courses  Projects  Expert   Notes
```

---

*Визуализация помогает лучше понять структуру vault и эффективно его использовать!*
