# 🤖 Machine Learning

> *Центр знаний по Machine Learning и AI*

---

## 📊 Общий прогресс

![ML Progress](https://progress-bar.dev/70/?title=ML%20Mastery&width=300&color=4c9aff)

**Завершено курсов:** 3  
**В процессе:** 2  
**Запланировано:** 5

---

## 📚 Курсы

### 🟢 Завершенные
- [[Courses/ML/Neural-Networks-Basics|Neural Networks Basics]] - ⭐⭐⭐⭐⭐
- [[Courses/ML/Python-for-ML|Python for ML]] - ⭐⭐⭐⭐⭐

### 🟡 В процессе
- [[Courses/ML/Deep-Learning|Deep Learning Specialization]] - 70%
- [[Courses/ML/Computer-Vision|Computer Vision]] - 45%

### ⚪ Запланированные
- Natural Language Processing
- Reinforcement Learning
- MLOps Fundamentals

---

## 💻 Проекты

### Активные проекты
```dataview
TABLE 
  status as "Статус",
  progress as "Прогресс"
FROM "Projects"
WHERE contains(tags, "ml")
SORT progress DESC
```

---

## 🧠 Темы для изучения

### Neural Networks
- [x] Perceptron
- [x] Backpropagation
- [ ] Advanced architectures
- [ ] Optimization techniques

### Deep Learning
- [x] CNN
- [ ] RNN / LSTM
- [ ] Transformers
- [ ] GANs

### Computer Vision
- [ ] Object Detection
- [ ] Image Segmentation
- [ ] Face Recognition

### NLP
- [ ] Text Classification
- [ ] Named Entity Recognition
- [ ] Transformer models

---

## 📝 Заметки и ресурсы

### Важные концепции
- [[Notes/ML/Gradient-Descent|Gradient Descent]]
- [[Notes/ML/Loss-Functions|Loss Functions]]
- [[Notes/ML/Regularization|Regularization]]

### Датасеты
- MNIST
- CIFAR-10
- ImageNet
- COCO

### Инструменты
- TensorFlow
- PyTorch
- Keras
- scikit-learn

---

## 🔗 Полезные ресурсы

### Онлайн курсы
- [Coursera - Deep Learning](https://coursera.org)
- [Fast.ai](https://fast.ai)
- [Stanford CS229](https://cs229.stanford.edu)

### Книги
- Deep Learning (Ian Goodfellow)
- Hands-On Machine Learning (Aurélien Géron)
- Pattern Recognition and Machine Learning (Bishop)

### Блоги и сайты
- [Distill.pub](https://distill.pub)
- [Papers With Code](https://paperswithcode.com)
- [Towards Data Science](https://towardsdatascience.com)

---

## 📊 Статистика

```dataview
TABLE 
  progress as "Прогресс",
  source as "Источник"
FROM "Courses/ML"
WHERE file.name != "ML-Index"
SORT progress DESC
```

---

*[[Dashboard|← Назад на Dashboard]]*
