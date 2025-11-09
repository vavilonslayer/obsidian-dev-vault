# 🤝 Contributing Guide

> Как внести свой вклад в Obsidian Dev Vault

---

## 🎯 Цель проекта

Создать best-in-class Obsidian vault для ML и DevOps разработчиков с фокусом на:
- Визуальную привлекательность
- Практичность и удобство
- Автоматизацию и интеграции
- Качественные примеры контента

---

## 🌟 Способы внести вклад

### 1. Добавить новый контент

#### Курсы
- Добавьте курс, который вы проходите
- Используйте `Template-Course.md`
- Включите практические примеры
- Добавьте в соответствующий Index

#### Проекты
- Поделитесь своим проектом
- Опишите архитектуру и технологии
- Включите deployment инструкции
- Добавьте lessons learned

#### Interview Questions
- Добавьте вопросы, которые вам задавали
- Включите подробные ответы
- Примеры кода обязательны
- Follow-up вопросы приветствуются

#### Code Snippets
- Полезные переиспользуемые фрагменты
- С подробной документацией
- Примеры использования
- Best practices

#### Notes
- Концепции и теория
- Связи с другими заметками
- Практические примеры
- Визуализации приветствуются

---

## 📝 Стандарты качества

### Структура заметок

**Обязательные элементы:**
- Frontmatter с метаданными
- Четкие заголовки
- Примеры кода (где применимо)
- Ссылки на ресурсы
- Связи с другими заметками

**Frontmatter шаблон:**
```yaml
---
type: [course|project|interview|snippet|note]
tags: [relevant, tags]
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

### Форматирование

**Markdown:**
- Используйте heading hierarchy (H1 → H2 → H3)
- Code blocks с языком: ```python
- Списки для structure
- Tables где уместно

**Эмодзи:**
- Для визуальной привлекательности
- Consistency в использовании:
  - 📚 Курсы
  - 💻 Проекты
  - 🧠 Интервью
  - 🧰 Сниппеты
  - 📝 Заметки

**Progress bars:**
```markdown
![progress](https://progress-bar.dev/70/?title=Title&width=200&color=4c9aff)
```

### Качество кода

**Code examples должны:**
- Быть working examples
- Включать комментарии
- Следовать best practices
- Иметь объяснения

**Плохо:**
```python
def f(x):
    return x*2
```

**Хорошо:**
```python
def double_value(number: int) -> int:
    """
    Double the input value
    
    Args:
        number: Integer to double
        
    Returns:
        Doubled value
    """
    return number * 2
```

---

## 🔄 Процесс contribution

### 1. Fork & Clone

```bash
# Fork на GitHub
# Затем clone
git clone https://github.com/YOUR_USERNAME/obsidian-dev-vault.git
cd obsidian-dev-vault
```

### 2. Создать Branch

```bash
git checkout -b feature/your-feature-name
# или
git checkout -b content/add-ml-course
```

### 3. Внести изменения

- Добавьте контент
- Следуйте структуре и стандартам
- Проверьте в Obsidian

### 4. Commit

```bash
git add .
git commit -m "Add: Deep Learning course notes"
```

**Commit message guidelines:**
- `Add:` новый контент
- `Update:` обновление существующего
- `Fix:` исправление ошибок
- `Refactor:` реструктуризация
- `Docs:` документация

### 5. Push & Pull Request

```bash
git push origin feature/your-feature-name
```

Создайте Pull Request на GitHub с описанием:
- Что добавлено/изменено
- Зачем это полезно
- Screenshots (если UI изменения)

---

## ✅ Checklist перед PR

### Контент
- [ ] Следует структуре существующих файлов
- [ ] Включает frontmatter с метаданными
- [ ] Имеет примеры кода (где применимо)
- [ ] Ссылки на ресурсы добавлены
- [ ] Связан с другими заметками через links
- [ ] Progress bars правильно отформатированы
- [ ] Эмодзи используются консистентно

### Техническое
- [ ] Файлы в правильных директориях
- [ ] Названия файлов следуют convention
- [ ] Markdown правильно отформатирован
- [ ] Code blocks имеют language specifier
- [ ] Изображения в `Assets/Images/`
- [ ] Проверено в Obsidian

### Документация
- [ ] README обновлен (если нужно)
- [ ] Index files обновлены
- [ ] CHANGELOG обновлен (для больших изменений)

---

## 🎨 Темы для contribution

### High Priority

**Больше примеров контента:**
- [ ] Advanced ML курсы (NLP, RL)
- [ ] Cloud platforms (AWS, GCP, Azure)
- [ ] More interview questions (System Design)
- [ ] Production-ready project examples

**Улучшения функциональности:**
- [ ] Dataview queries оптимизация
- [ ] Custom CSS improvements
- [ ] Template enhancements
- [ ] Plugin configurations

**Автоматизация:**
- [ ] Scripts для maintenance
- [ ] Automated progress tracking
- [ ] Git hooks для consistency
- [ ] CI/CD для validation

### Medium Priority

**Расширение категорий:**
- [ ] Frontend development section
- [ ] Database section
- [ ] Security section
- [ ] Soft skills section

**Интеграции:**
- [ ] Jupyter notebook integration
- [ ] Git integration improvements
- [ ] VSCode workspace setup
- [ ] Docker development environment

### Community Requests

Проверьте [Issues](https://github.com/vavilonslayer/obsidian-dev-vault/issues) для community requests.

---

## 💡 Идеи для нового контента

### Курсы
- FastAPI / Django
- React / Vue.js
- System Design
- Algorithm Masterclass
- Cloud Certifications

### Проекты
- Microservices architecture
- Real-time data pipeline
- ML deployment с MLOps
- Infrastructure as Code examples
- Monitoring & Observability setup

### Interview Prep
- More System Design questions
- Behavioral interview questions
- Company-specific prep
- Salary negotiation

### Snippets
- More language support (Go, Rust, Java)
- Cloud provider snippets (Terraform, CloudFormation)
- Testing frameworks
- CI/CD pipeline templates

---

## 🚫 Что НЕ принимается

### Неприемлемый контент
- Плагиат или copyright violations
- Low-quality или incomplete content
- Unrelated to ML/DevOps/Programming
- Promotional or spam content

### Технические проблемы
- Broken links или images
- Malformed markdown
- Missing metadata
- Несовместимость с Obsidian

---

## 🌐 Локализация

Приветствуются contributions на других языках!

**Структура для локализации:**
```
/lang/
  /ru/  - Russian (основной)
  /en/  - English
  /zh/  - Chinese
  etc.
```

---

## 📞 Коммуникация

### Вопросы и обсуждения
- GitHub Discussions для общих вопросов
- GitHub Issues для bugs и feature requests
- Pull Request comments для code review

### Время ответа
- Issues: 1-3 дня
- Pull Requests: 3-7 дней
- Discussions: Best effort

---

## 🏆 Recognition

Contributors будут:
- Добавлены в CONTRIBUTORS.md
- Упомянуты в release notes
- Credited в документации

### Уровни contributors

**🌟 Core Contributors:**
- Регулярные contributions
- Помощь с reviews
- Community moderation

**💎 Content Contributors:**
- Quality content additions
- Template improvements
- Documentation updates

**🔧 Technical Contributors:**
- Plugin configurations
- Scripts и automation
- Infrastructure improvements

---

## 📄 Лицензия

Внося вклад, вы соглашаетесь что ваш контент будет распространяться под MIT License.

---

## 🙏 Благодарности

Спасибо за интерес к проекту!

Каждый contribution делает этот vault лучше для всего сообщества ML и DevOps разработчиков.

---

## 📚 Ресурсы для contributors

### Markdown
- [Markdown Guide](https://www.markdownguide.org)
- [Obsidian Markdown Reference](https://help.obsidian.md/How+to/Format+your+notes)

### Obsidian
- [Obsidian Documentation](https://help.obsidian.md)
- [Dataview Documentation](https://blacksmithgu.github.io/obsidian-dataview/)

### Git & GitHub
- [Git Handbook](https://guides.github.com/introduction/git-handbook/)
- [GitHub Flow](https://guides.github.com/introduction/flow/)

---

**Happy Contributing! 🚀**

*Questions? Open an issue or start a discussion!*
