# 🚀 Setup Guide - Obsidian Dev Vault

> Пошаговая инструкция по настройке вашего Obsidian vault

---

## 📋 Требования

- **Obsidian:** v1.0.0 или выше
- **Git:** для клонирования репозитория
- **Опционально:** Node.js для дополнительных скриптов

---

## 🔧 Установка

### Шаг 1: Клонирование репозитория

```bash
# Клонировать репозиторий
git clone https://github.com/vavilonslayer/obsidian-dev-vault.git

# Перейти в директорию
cd obsidian-dev-vault
```

### Шаг 2: Открыть в Obsidian

1. Запустить Obsidian
2. Нажать "Open folder as vault"
3. Выбрать папку `obsidian-dev-vault`
4. Obsidian откроет vault

---

## ⚙️ Настройка плагинов

### Включение Community Plugins

1. Открыть **Settings** (⚙️ иконка внизу слева)
2. Перейти в **Community plugins**
3. Нажать **Turn on community plugins**
4. Подтвердить включение

### Установка обязательных плагинов

#### 1. Dataview
```
Settings → Community plugins → Browse → Поиск "Dataview" → Install → Enable
```

**Конфигурация:**
- Settings → Dataview
- ✅ Enable JavaScript Queries
- ✅ Enable Inline Queries
- ✅ Enable Inline JavaScript Queries

#### 2. Templater
```
Settings → Community plugins → Browse → Поиск "Templater" → Install → Enable
```

**Конфигурация:**
- Settings → Templater
- Template folder location: `Templates`
- ✅ Trigger Templater on new file creation: OFF (по умолчанию)
- Hotkey: `Cmd/Ctrl + Shift + T`

#### 3. Calendar
```
Settings → Community plugins → Browse → Поиск "Calendar" → Install → Enable
```

**Конфигурация:**
- Создает календарь в боковой панели
- Клик по дате создает Daily Note

### Рекомендуемые плагины

#### QuickAdd
Быстрое создание заметок с шаблонами
```
Settings → Community plugins → Browse → "QuickAdd"
```

#### Periodic Notes
Ежедневные, еженедельные, месячные обзоры
```
Settings → Community plugins → Browse → "Periodic Notes"
```

#### Tracker
Трекинг привычек и метрик
```
Settings → Community plugins → Browse → "Tracker"
```

#### Obsidian Charts
Визуализация данных
```
Settings → Community plugins → Browse → "Obsidian Charts"
```

---

## 🎨 Настройка темы оформления

### Установка Minimal Theme

1. Settings → Appearance → Themes → Manage
2. Поиск "Minimal"
3. Install and use
4. Settings → Appearance → CSS snippets
5. ✅ Включить `custom-styles`

### Альтернативные темы

**AnuPpuccin:**
- Красочная, современная тема
- Отличная поддержка плагинов

**Blue Topaz:**
- Профессиональная тема
- Хорошо подходит для работы

---

## 📁 Настройка хранения файлов

### Attachment Location

**Важно:** Все изображения должны сохраняться в `Assets/Images`

1. Settings → Files & Links
2. **Default location for new attachments:** `Assets/Images`
3. ✅ Automatically update internal links: ON
4. New link format: `Shortest path`

### Paste Image Rename (опционально)

Для автоматического переименования вставляемых изображений:
```
Settings → Community plugins → Browse → "Paste Image Rename"
```

Конфигурация:
- Image name pattern: `{{fileName}}-{{date}}`
- Duplicate number: `After file name`

---

## ⌨️ Горячие клавиши

### Предустановленные

Уже настроены в vault:

| Команда | Hotkey | Описание |
|---------|--------|----------|
| Bold | `Cmd/Ctrl + B` | Выделить текст жирным |
| Italic | `Cmd/Ctrl + I` | Курсив |
| Highlight | `Cmd/Ctrl + Shift + H` | Подсветка |
| Code | `Cmd/Ctrl + E` | Inline code |
| Insert Template | `Cmd/Ctrl + Shift + T` | Вставить шаблон |
| QuickAdd | `Cmd/Ctrl + Shift + A` | Быстрое добавление |
| Daily Note | `Cmd/Ctrl + Shift + D` | Открыть/создать дневную заметку |

### Дополнительные (рекомендуем настроить)

1. Settings → Hotkeys
2. Поиск команды
3. Назначить клавиши

**Полезные команды:**
- Open quick switcher: `Cmd/Ctrl + O`
- Search in all files: `Cmd/Ctrl + Shift + F`
- Open graph view: `Cmd/Ctrl + G`
- Toggle left sidebar: `Cmd/Ctrl + Shift + ←`

---

## 📊 Проверка установки

### Тест 1: Dataview работает

1. Открыть `Dashboard.md`
2. Проверить, что Dataview queries отображаются
3. Если нет - перезагрузить Obsidian

### Тест 2: Шаблоны работают

1. Создать новый файл в `Courses/ML/`
2. `Cmd/Ctrl + Shift + T`
3. Выбрать `Template-Course.md`
4. Шаблон должен вставиться

### Тест 3: Progress bars отображаются

1. Открыть `Dashboard.md`
2. Progress bars должны отображаться как изображения
3. Если нет - проверить интернет соединение

### Тест 4: CSS стили применены

1. Settings → Appearance → CSS snippets
2. ✅ `custom-styles` должен быть включен
3. Перезагрузить Obsidian если нужно

---

## 🎯 Первые шаги

### 1. Изучить Dashboard

Откройте `Dashboard.md` - это ваша главная страница с:
- Быстрыми ссылками на все разделы
- Progress bars
- Текущими целями
- Статистикой

### 2. Создать первую заметку

Попробуйте создать:
- **Курс:** `Courses/ML/` + Template-Course.md
- **Проект:** `Projects/` + Template-Project.md
- **Вопрос для интервью:** `Interview Prep/` + Template-Interview.md

### 3. Настроить под себя

- Обновите Dashboard с вашими целями
- Измените progress bars на актуальные значения
- Добавьте свои проекты и курсы

### 4. Установить ритм

- Используйте Daily Notes для ежедневного планирования
- Weekly Review для еженедельных обзоров
- Обновляйте Dashboard регулярно

---

## 🔧 Troubleshooting

### Dataview не работает

**Проблема:** Dataview queries не отображаются

**Решение:**
1. Settings → Dataview → ✅ Enable JavaScript Queries
2. Перезагрузить Obsidian (`Cmd/Ctrl + R`)
3. Проверить синтаксис query

### Progress bars не показываются

**Проблема:** Изображения progress bars не загружаются

**Решение:**
1. Проверить интернет соединение
2. Сервис progress-bar.dev может быть недоступен
3. Альтернатива: использовать локальные progress indicators

### Шаблоны не вставляются

**Проблема:** Templater не работает

**Решение:**
1. Settings → Templater → Template folder: `Templates`
2. Убедиться что плагин включен
3. Перезагрузить Obsidian

### CSS стили не применяются

**Проблема:** Кастомные стили не видны

**Решение:**
1. Settings → Appearance → CSS snippets
2. ✅ Включить `custom-styles`
3. Reload Obsidian

---

## 📱 Мобильная версия

### Obsidian Mobile

1. Установить Obsidian на iOS/Android
2. Синхронизировать через:
   - Obsidian Sync (платно, официальный)
   - Git (бесплатно, через плагин)
   - iCloud/Google Drive (бесплатно)

### Рекомендуемые настройки для мобильной версии

- Включите Reader mode для просмотра
- Настройте мобильные hotkeys
- Используйте упрощенную тему

---

## 🔄 Обновления и синхронизация

### Git Sync (рекомендуется)

1. Установить плагин "Obsidian Git"
2. Настроить автокоммиты
3. Push/Pull для синхронизации

```bash
# Вручную
git pull origin main
git add .
git commit -m "Update vault"
git push origin main
```

### Obsidian Sync

Официальный платный сервис ($8/месяц):
- Автоматическая синхронизация
- End-to-end encryption
- Version history

---

## 💡 Полезные советы

### Workflow tips

1. **Утром:** Открыть Daily Note, поставить цели
2. **В течение дня:** Делать заметки, обновлять progress
3. **Вечером:** Review выполненных задач
4. **Еженедельно:** Weekly Review

### Организация

- Используйте tags для категоризации
- Links для связи концепций
- Aliases для альтернативных названий
- Frontmatter для метаданных

### Продуктивность

- Keyboard shortcuts для скорости
- Templates для стандартизации
- Dataview для автоматизации
- Daily notes для habit tracking

---

## 📚 Дополнительные ресурсы

### Документация

- [Obsidian Help](https://help.obsidian.md)
- [Dataview Plugin](https://blacksmithgu.github.io/obsidian-dataview/)
- [Templater Plugin](https://silentvoid13.github.io/Templater/)

### Сообщество

- [Obsidian Forum](https://forum.obsidian.md)
- [Obsidian Discord](https://discord.gg/obsidianmd)
- [r/ObsidianMD](https://reddit.com/r/ObsidianMD)

### Видео туториалы

- [Linking Your Thinking](https://www.youtube.com/c/NickMilo)
- [Obsidian Office Hours](https://www.youtube.com/c/ObsidianOfficeHours)

---

## ✅ Checklist готовности

После setup проверьте:

- [ ] Obsidian открыт с vault
- [ ] Community plugins включены
- [ ] Dataview установлен и работает
- [ ] Templater установлен и настроен
- [ ] Тема применена (Minimal или другая)
- [ ] CSS snippets включены
- [ ] Attachment location: `Assets/Images`
- [ ] Hotkeys настроены
- [ ] Dashboard.md открывается корректно
- [ ] Progress bars отображаются
- [ ] Можно создать заметку с шаблоном

---

## 🎉 Готово!

Теперь ваш Obsidian vault готов к работе!

Начните с `Dashboard.md` и исследуйте vault.

**Happy note-taking! 📝**

---

*Если возникли проблемы, откройте issue на GitHub или обратитесь в сообщество Obsidian.*
