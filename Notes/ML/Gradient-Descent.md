# Gradient Descent

**Tags:** #ml #optimization #concept

---

## 📝 Определение

Gradient Descent - это итеративный алгоритм оптимизации, используемый для минимизации функции потерь (loss function) в машинном обучении.

---

## 💡 Основная идея

Алгоритм движется в направлении наибольшего убывания функции (противоположно градиенту), постепенно приближаясь к минимуму.

### Формула обновления весов

```
θ = θ - α * ∇J(θ)
```

Где:
- θ - параметры модели (weights)
- α - learning rate (шаг обучения)
- ∇J(θ) - градиент функции потерь
- J(θ) - функция потерь

---

## 🔄 Типы Gradient Descent

### 1. Batch Gradient Descent
- Использует весь датасет для вычисления градиента
- **Плюсы:** Стабильная конвергенция
- **Минусы:** Медленный для больших датасетов

### 2. Stochastic Gradient Descent (SGD)
- Использует один sample для обновления
- **Плюсы:** Быстрее, может выйти из локальных минимумов
- **Минусы:** Нестабильная траектория

### 3. Mini-batch Gradient Descent
- Использует небольшие батчи (например, 32-256 samples)
- **Баланс** между batch и SGD
- **Наиболее популярный** на практике

---

## 💻 Пример кода

```python
import numpy as np

def gradient_descent(X, y, learning_rate=0.01, iterations=1000):
    """
    Simple gradient descent for linear regression
    """
    m, n = X.shape
    theta = np.zeros(n)
    
    for i in range(iterations):
        # Compute predictions
        predictions = X.dot(theta)
        
        # Compute errors
        errors = predictions - y
        
        # Compute gradient
        gradient = (1/m) * X.T.dot(errors)
        
        # Update parameters
        theta = theta - learning_rate * gradient
        
        # Compute cost (optional, for monitoring)
        if i % 100 == 0:
            cost = (1/(2*m)) * np.sum(errors**2)
            print(f'Iteration {i}, Cost: {cost:.4f}')
    
    return theta

# Usage
X_train = np.random.randn(100, 3)
y_train = np.random.randn(100)
theta_optimal = gradient_descent(X_train, y_train)
```

---

## ⚙️ Важные гиперпараметры

### Learning Rate (α)
- **Слишком большой:** алгоритм не сходится, "прыгает"
- **Слишком маленький:** медленная конвергенция
- **Типичные значения:** 0.001 - 0.1
- **Решение:** Learning rate scheduling

### Number of Iterations
- Зависит от датасета и learning rate
- Использовать early stopping

---

## 📊 Визуализация

```
Cost
  ^
  |     .
  |   .   .
  | .       .
  |           .
  |              .
  +-----------------> Iterations
```

---

## 🔗 Связанные концепции

- [[Notes/ML/Loss-Functions|Loss Functions]]
- [[Notes/ML/Optimization|Optimization Algorithms]]
- [[Notes/ML/Backpropagation|Backpropagation]]

---

## 💡 Практические советы

1. Нормализуйте features перед обучением
2. Используйте adaptive learning rate (Adam, RMSprop)
3. Мониторьте loss на validation set
4. Визуализируйте learning curves

---

*Создано: 2024-02-20*
