# ⚡ Краткий справочник

> Быстрая шпаргалка по использованию Obsidian Dev Vault

---

## 🎯 Основные разделы

| Раздел | Путь | Описание |
|--------|------|----------|
| 🏠 Dashboard | `Dashboard.md` | Главная страница |
| 📚 Курсы ML | `Courses/ML/` | Machine Learning курсы |
| ⚙️ Курсы DevOps | `Courses/DevOps/` | DevOps курсы |
| 💻 Проекты | `Projects/` | Мои проекты |
| 🧠 Интервью | `Interview Prep/` | Подготовка к собеседованиям |
| 🧰 Сниппеты | `Snippets/` | Код snippets |
| 📝 Заметки | `Notes/` | Общие заметки |

---

## ⌨️ Горячие клавиши

### Редактирование
- `Cmd/Ctrl + B` - **Жирный**
- `Cmd/Ctrl + I` - *Курсив*
- `Cmd/Ctrl + E` - `Код`
- `Cmd/Ctrl + K` - Создать ссылку
- `Cmd/Ctrl + Shift + H` - ==Выделение==

### Навигация
- `Cmd/Ctrl + O` - Быстрое переключение
- `Cmd/Ctrl + P` - Палитра команд
- `Cmd/Ctrl + Shift + F` - Поиск в файлах
- `Cmd/Ctrl + G` - Граф связей
- `Cmd/Ctrl + E` - Переключить редактирование/просмотр

### Специальные
- `Cmd/Ctrl + Shift + T` - Вставить шаблон
- `Cmd/Ctrl + Shift + D` - Дневная заметка
- `Cmd/Ctrl + Shift + A` - QuickAdd

---

## 📝 Markdown Синтаксис

### Заголовки
```markdown
# H1
## H2
### H3
```

### Форматирование
```markdown
**Жирный**
*Курсив*
==Выделение==
`Код`
~~Strikethrough~~
```

### Списки
```markdown
- Item 1
- Item 2
  - Nested item

1. First
2. Second
```

### Задачи
```markdown
- [ ] Todo
- [x] Done
```

### Links
```markdown
[[Other Note]]
[[Other Note|Display Text]]
[[Other Note#Section]]
```

### Изображения
```markdown
![[image.png]]
![Alt text](https://url.com/image.png)
```

### Код Blocks
````markdown
```python
def hello():
    print("Hello")
```
````

### Таблицы
```markdown
| Column 1 | Column 2 |
|----------|----------|
| Cell 1   | Cell 2   |
```

---

## 🔍 Dataview Queries

### Список файлов
```dataview
LIST
FROM "Folder"
WHERE condition
SORT field
```

### Таблица
```dataview
TABLE field1, field2
FROM "Folder"
WHERE condition
```

### Задачи
```dataview
TASK
FROM "Folder"
WHERE !completed
```

### Inline Queries
```markdown
Сегодня: `=date(today)`
Количество: `=length(file.tasks)`
```

---

## 📋 Шаблоны

### Использование шаблонов

1. Создать новый файл в нужной папке
2. `Cmd/Ctrl + Shift + T`
3. Выбрать нужный шаблон

### Доступные шаблоны

| Шаблон | Использование |
|--------|---------------|
| Template-Course | Для курсов ML/DevOps |
| Template-Project | Для проектов |
| Template-Interview | Для вопросов интервью |
| Template-Snippet | Для code snippets |
| Template-Daily-Note | Для ежедневных заметок |

---

## 🎨 Progress Bars

### Синтаксис
```markdown
![progress](https://progress-bar.dev/70/?title=ML&width=200&color=4c9aff)
```

### Параметры
- `70` - процент прогресса (0-100)
- `title=ML` - заголовок
- `width=200` - ширина в пикселях
- `color=4c9aff` - hex цвет (без #)

### Цвета по категориям
- ML: `4c9aff` (синий)
- DevOps: `36b37e` (зеленый)
- Interview: `6554c0` (фиолетовый)
- Projects: `ff5630` (красный)

---

## 📊 Frontmatter

### Структура
```yaml
---
type: course
status: "В процессе"
progress: 70
tags: [ml, course]
created: 2024-03-01
---
```

### Стандартные поля

**Для курсов:**
- type: course
- source: "Название курса"
- progress: 0-100
- status: "В процессе" / "Завершен"
- tags: [course, ml/devops]

**Для проектов:**
- type: project
- status: "В работе"
- progress: 0-100
- priority: "Высокий/Средний/Низкий"
- tags: [project, technology]

**Для интервью:**
- type: interview-question
- category: "Algorithms"
- difficulty: "Easy/Medium/Hard"
- mastery: 0-100
- tags: [interview, topic]

---

## 🏷️ Теги

### Основные категории
- `#ml` - Machine Learning
- `#devops` - DevOps
- `#course` - Курсы
- `#project` - Проекты
- `#interview` - Интервью
- `#snippet` - Сниппеты
- `#concept` - Концепции
- `#tutorial` - Туториалы

### Использование
```markdown
#ml #deep-learning #course
```

---

## 🔗 Internal Links

### Типы ссылок

**Обычная:**
```markdown
[[Note Name]]
```

**С отображаемым текстом:**
```markdown
[[Note Name|Display Text]]
```

**К разделу:**
```markdown
[[Note Name#Section Name]]
```

**К блоку:**
```markdown
[[Note Name^block-id]]
```

---

## 🎯 Workflow Examples

### Начало дня
1. `Cmd+Shift+D` - Открыть Daily Note
2. Заполнить цели на день
3. Открыть Dashboard для обзора

### Изучение курса
1. Открыть `Courses/ML/` или `Courses/DevOps/`
2. Создать новую заметку
3. `Cmd+Shift+T` → Template-Course
4. Заполнить информацию
5. Обновить progress в Dashboard

### Работа над проектом
1. Открыть `Projects/`
2. Найти или создать проект
3. Обновить статус и TODO
4. Зафиксировать прогресс

### Подготовка к интервью
1. Открыть `Interview Prep/`
2. Выбрать категорию вопроса
3. `Cmd+Shift+T` → Template-Interview
4. Решить задачу
5. Отметить прогресс mastery

### Сохранение сниппета
1. Открыть `Snippets/`
2. Создать заметку
3. `Cmd+Shift+T` → Template-Snippet
4. Вставить код и описание
5. Добавить теги

---

## 💡 Полезные команды

### Command Palette (Cmd/Ctrl+P)

- **"Toggle"** - переключение режимов
- **"Open"** - открыть различные панели
- **"Search"** - поиск
- **"Create"** - создание
- **"Insert"** - вставка

### Часто используемые

- "Toggle left sidebar"
- "Toggle right sidebar"
- "Open graph view"
- "Search and replace"
- "Вставить шаблон"
- "Export to PDF"

---

## 🔧 Быстрые настройки

### Включить/выключить плагин
```
Настройки → Сторонние плагины → Плагин → Toggle
```

### Изменить тему
```
Настройки → Appearance → Themes → Choose
```

### Настроить hotkey
```
Настройки → Hotkeys → Search → Assign
```

### Включить CSS snippet
```
Настройки → Appearance → CSS snippets → Toggle
```

---

## 📈 Статусные индикаторы

### Эмодзи для статусов

**Прогресс:**
- 🟢 Завершено / Хорошо
- 🟡 В процессе / Средне
- 🔴 Начато / Требует внимания
- ⚪ Запланировано
- ✅ Выполнено

**Приоритет:**
- 🔴 Высокий
- 🟡 Средний
- 🟢 Низкий

**Сложность:**
- 🟢 Легко (Easy)
- 🟡 Средне (Medium)
- 🔴 Сложно (Hard)

---

## 📚 Полезные ресурсы

### Документация
- [Obsidian Help](https://help.obsidian.md)
- [Markdown Guide](https://www.markdownguide.org)
- [Dataview Docs](https://blacksmithgu.github.io/obsidian-dataview/)

### Сообщество
- [Forum](https://forum.obsidian.md)
- [Discord](https://discord.gg/obsidianmd)
- [Reddit](https://reddit.com/r/ObsidianMD)

---

## 🎓 Tips & Tricks

### Продуктивность
1. Используйте Quick Switcher (`Cmd+O`) вместо навигации
2. Создавайте aliases для часто используемых заметок
3. Используйте tags для категоризации
4. Backlinks показывают связи между заметками

### Организация
1. Папки для основных категорий
2. Tags для пересекающихся тем
3. Links для связи концепций
4. Index notes для обзора разделов

### Автоматизация
1. Templater для динамических шаблонов
2. Dataview для автоматических списков
3. QuickAdd для быстрого создания
4. Periodic Notes для регулярных обзоров

---

**Сохраните эту страницу в закладки для быстрого доступа!**

*Последнее обновление: 2024-03-09*
