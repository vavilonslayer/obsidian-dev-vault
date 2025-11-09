# 🚀 Obsidian Dev Vault - ML & DevOps

> Визуально-интерактивное Obsidian хранилище для программиста (Machine Learning + DevOps)

![Progress](https://img.shields.io/badge/Progress-100%25-brightgreen)
![Version](https://img.shields.io/badge/Version-1.0-blue)
![Obsidian](https://img.shields.io/badge/Obsidian-Compatible-purple)

---

## 🎯 О проекте

Это **уникальное визуально-интерактивное Obsidian-хранилище**, специально созданное для разработчиков в области Machine Learning и DevOps. Включает продуманную структуру, эстетичный дизайн, готовые шаблоны, сниппеты и дашборды для отслеживания прогресса и продуктивности.

### ✨ Особенности

- 📊 **Визуальные дашборды** с progress bars и метриками
- 🎨 **Эстетичный дизайн** в стиле "Notion meets Obsidian"
- 🤖 **ML & DevOps фокус** - специализированный контент
- 📝 **Готовые шаблоны** для курсов, проектов, интервью, сниппетов
- ⚡ **Автоматизация** через Dataview, Templater
- 🔗 **Интеграция** с инструментами разработчика

---

## 📁 Структура хранилища

```
obsidian-dev-vault/
├── Dashboard.md              # Главная страница с визуальными элементами
├── Dashboard/
│   ├── Progress.md          # Детальная аналитика прогресса
│   └── Weekly-Review.md     # Еженедельный обзор
├── Courses/
│   ├── ML/                  # Курсы по Machine Learning
│   │   ├── ML-Index.md
│   │   └── Deep-Learning.md
│   └── DevOps/              # Курсы по DevOps
│       ├── DevOps-Index.md
│       └── Kubernetes-Deep-Dive.md
├── Projects/
│   ├── Projects-Index.md
│   └── ML-Image-Classification.md
├── Interview Prep/
│   ├── Interview-Index.md
│   └── Two-Sum-Problem.md
├── Snippets/
│   ├── Snippets-Index.md
│   └── PyTorch-Training-Template.md
├── Notes/
│   └── Notes-Index.md
├── Templates/
│   ├── Template-Course.md
│   ├── Template-Project.md
│   ├── Template-Interview.md
│   ├── Template-Snippet.md
│   └── Template-Daily-Note.md
├── Assets/
│   └── Images/              # Централизованное хранение изображений
└── .obsidian/
    ├── config               # Основные настройки
    ├── snippets/
    │   └── custom-styles.css
    └── plugins/
        ├── dataview/
        └── templater-obsidian/
```

---

## 🎨 Основные разделы

### 📊 Dashboard (Главная страница)
- Приветствие и текущая дата
- Визуальные progress bars по всем направлениям
- Быстрые ссылки на все разделы
- Статистика задач и обучения
- Интеграция с Dataview для динамических данных

### 📚 Courses (Курсы)
- **ML:** Deep Learning, Computer Vision, NLP
- **DevOps:** Docker, Kubernetes, CI/CD
- Шаблоны с progress tracking
- Конспекты, примеры кода, практические задания

### 💻 Projects (Проекты)
- ML Image Classification
- K8s Deployment Pipeline
- Data Pipeline Automation
- Детальное описание архитектуры, технологий, прогресса

### 🧠 Interview Prep (Подготовка к интервью)
- Алгоритмы и структуры данных
- System Design вопросы
- ML/DevOps специфические темы
- Tracking mastery по каждому вопросу

### 🧰 Snippets (Сниппеты кода)
- Python (ML, Web, Utils)
- Docker & Kubernetes
- Bash/Shell scripts
- SQL, JavaScript, Cloud (AWS/GCP)

### 📝 Notes (Заметки)
- Общие знания и концепции
- Организованы по категориям
- Связаны с курсами и проектами

---

## ⚙️ Рекомендуемые плагины

### Обязательные
- **Dataview** - динамические списки и таблицы
- **Templater** - продвинутые шаблоны
- **Calendar** - планирование и daily notes

### Рекомендуемые
- **QuickAdd** - быстрое создание заметок
- **Periodic Notes** - ежедневные/еженедельные обзоры
- **Tracker** - трекинг привычек и метрик
- **Obsidian Charts** - визуализация данных
- **Style Settings** - кастомизация темы

### Для медиа
- **Paste Image Rename** - автоматическое переименование вставленных изображений
- **Attachment Management** - централизованное хранение в Assets/Images

---

## 🎨 Темы оформления

Рекомендуемые темы для наилучшего визуального опыта:

- **Minimal** - чистый, минималистичный дизайн
- **AnuPpuccin** - красочная, современная тема
- **Blue Topaz** - профессиональная тема с акцентами

Кастомные CSS сниппеты включены в `.obsidian/snippets/custom-styles.css`

---

## 🚀 Быстрый старт

### 1. Установка
```bash
# Клонировать репозиторий
git clone https://github.com/vavilonslayer/obsidian-dev-vault.git

# Открыть в Obsidian
# Файл → Открыть хранилище → Выбрать папку obsidian-dev-vault
```

### 2. Установка плагинов
1. Открыть Настройки → Сторонние плагины
2. Включить сторонние плагины
3. Установить рекомендуемые плагины:
   - Dataview
   - Templater
   - Calendar
   - QuickAdd

### 3. Настройка
1. Настройки → Файлы и ссылки → Место для новых вложений по умолчанию: `Assets/Images`
2. Настройки → Внешний вид → CSS сниппеты: Включить `custom-styles.css`
3. Настройки → Горячие клавиши: Настроить под себя (уже есть базовые)

### 4. Начало работы
1. Открыть `Dashboard.md` - главная страница
2. Изучить структуру и существующий контент
3. Использовать шаблоны из папки `Templates/`
4. Создать свой первый курс/проект/заметку

---

## 💡 Примеры использования

### Создание нового курса
1. Перейти в `Courses/ML/` или `Courses/DevOps/`
2. Создать новую заметку
3. Вставить шаблон из `Templates/Template-Course.md`
4. Заполнить информацию

### Добавление проекта
1. Перейти в `Projects/`
2. Использовать `Templates/Template-Project.md`
3. Описать архитектуру, технологии, прогресс
4. Обновлять по мере развития проекта

### Подготовка к интервью
1. Создать вопрос в `Interview Prep/`
2. Использовать `Templates/Template-Interview.md`
3. Добавить решение, примеры кода
4. Отмечать прогресс изучения

### Сохранение сниппета
1. В `Snippets/` создать новую заметку
2. Использовать `Templates/Template-Snippet.md`
3. Добавить код, описание, примеры

---

## 📊 Визуализация прогресса

### Progress Bars
Используются встроенные сервисы для отображения прогресса:

```markdown
![progress](https://progress-bar.dev/70/?title=ML&width=200&color=4c9aff)
![progress](https://progress-bar.dev/45/?title=DevOps&width=200&color=36b37e)
```

### Dataview Queries
Автоматические списки и таблицы:

```markdown
```dataview
TABLE 
  progress as "Прогресс",
  status as "Статус"
FROM "Projects"
SORT progress DESC
```
```

---

## 🔧 Настройки

### Горячие клавиши (по умолчанию)
- `Cmd/Ctrl + B` - Жирный
- `Cmd/Ctrl + I` - Курсив
- `Cmd/Ctrl + Shift + H` - Выделение
- `Cmd/Ctrl + E` - Код
- `Cmd/Ctrl + Shift + T` - Вставить шаблон
- `Cmd/Ctrl + Shift + A` - QuickAdd
- `Cmd/Ctrl + Shift + D` - Дневная заметка

### Автоматическое сохранение изображений
Все изображения автоматически сохраняются в `Assets/Images/`

Настройка: Настройки → Файлы и ссылки → Место для новых вложений по умолчанию

---

## 🤝 Вклад и обратная связь

Это хранилище можно адаптировать под свои нужды:

1. **Fork** репозиторий
2. Добавить свой контент
3. Настроить шаблоны под себя
4. Поделиться улучшениями через Pull Request

---

## 📚 Дополнительные ресурсы

### Obsidian
- [Официальная документация](https://help.obsidian.md)
- [Obsidian Forum](https://forum.obsidian.md)
- [Obsidian Discord](https://discord.gg/obsidianmd)

### Плагины
- [Dataview Documentation](https://blacksmithgu.github.io/obsidian-dataview/)
- [Templater Documentation](https://silentvoid13.github.io/Templater/)

### Вдохновение
- [Awesome Obsidian](https://github.com/kmaasrud/awesome-obsidian)
- [Obsidian Hub](https://publish.obsidian.md/hub/)

---

## 📝 Лицензия

MIT License - свободно используйте и модифицируйте под свои нужды.

---

## 🎉 Заключение

Это хранилище создано для того, чтобы сделать обучение и работу программиста более организованной, визуальной и продуктивной. Надеюсь, оно поможет вам в достижении ваших целей!

**Успешного обучения! 🚀**

---

*Создано с ❤️ для ML и DevOps сообщества*
