---
type: snippet
language: "python"
category: "ML/Training"
tags: [snippet, python, ml, training]
created: 2024-02-15
---

# 🧰 PyTorch Model Training Template

**Язык:** Python  
**Категория:** ML/Training  
**Использование:** Template для обучения PyTorch моделей

---

## 📝 Код

```python
import torch
import torch.nn as nn
import torch.optim as optim
from torch.utils.data import DataLoader
from tqdm import tqdm


class ModelTrainer:
    """
    Universal trainer for PyTorch models
    """
    
    def __init__(
        self,
        model: nn.Module,
        train_loader: DataLoader,
        val_loader: DataLoader,
        criterion: nn.Module,
        optimizer: optim.Optimizer,
        device: str = 'cuda',
        scheduler: optim.lr_scheduler._LRScheduler = None
    ):
        self.model = model.to(device)
        self.train_loader = train_loader
        self.val_loader = val_loader
        self.criterion = criterion
        self.optimizer = optimizer
        self.scheduler = scheduler
        self.device = device
        self.history = {
            'train_loss': [],
            'val_loss': [],
            'train_acc': [],
            'val_acc': []
        }
    
    def train_epoch(self):
        """Train for one epoch"""
        self.model.train()
        running_loss = 0.0
        correct = 0
        total = 0
        
        pbar = tqdm(self.train_loader, desc='Training')
        for inputs, labels in pbar:
            inputs, labels = inputs.to(self.device), labels.to(self.device)
            
            # Forward pass
            self.optimizer.zero_grad()
            outputs = self.model(inputs)
            loss = self.criterion(outputs, labels)
            
            # Backward pass
            loss.backward()
            self.optimizer.step()
            
            # Statistics
            running_loss += loss.item()
            _, predicted = outputs.max(1)
            total += labels.size(0)
            correct += predicted.eq(labels).sum().item()
            
            # Update progress bar
            pbar.set_postfix({
                'loss': running_loss / (pbar.n + 1),
                'acc': 100. * correct / total
            })
        
        epoch_loss = running_loss / len(self.train_loader)
        epoch_acc = 100. * correct / total
        
        return epoch_loss, epoch_acc
    
    def validate(self):
        """Validate the model"""
        self.model.eval()
        running_loss = 0.0
        correct = 0
        total = 0
        
        with torch.no_grad():
            for inputs, labels in tqdm(self.val_loader, desc='Validation'):
                inputs, labels = inputs.to(self.device), labels.to(self.device)
                
                outputs = self.model(inputs)
                loss = self.criterion(outputs, labels)
                
                running_loss += loss.item()
                _, predicted = outputs.max(1)
                total += labels.size(0)
                correct += predicted.eq(labels).sum().item()
        
        epoch_loss = running_loss / len(self.val_loader)
        epoch_acc = 100. * correct / total
        
        return epoch_loss, epoch_acc
    
    def fit(self, epochs: int, early_stopping_patience: int = None):
        """
        Train the model for multiple epochs
        
        Аргументы:
            epochs: Number of epochs to train
            early_stopping_patience: Stop if no improvement for N epochs
        """
        best_val_loss = float('inf')
        patience_counter = 0
        
        for epoch in range(epochs):
            print(f'\nEpoch {epoch + 1}/{epochs}')
            print('-' * 50)
            
            # Train
            train_loss, train_acc = self.train_epoch()
            
            # Validate
            val_loss, val_acc = self.validate()
            
            # Update history
            self.history['train_loss'].append(train_loss)
            self.history['train_acc'].append(train_acc)
            self.history['val_loss'].append(val_loss)
            self.history['val_acc'].append(val_acc)
            
            # Print statistics
            print(f'Train Loss: {train_loss:.4f}, Acc: {train_acc:.2f}%')
            print(f'Val Loss: {val_loss:.4f}, Acc: {val_acc:.2f}%')
            
            # Learning rate scheduling
            if self.scheduler:
                self.scheduler.step(val_loss)
                print(f'Learning Rate: {self.optimizer.param_groups[0]["lr"]:.6f}')
            
            # Early stopping
            if early_stopping_patience:
                if val_loss < best_val_loss:
                    best_val_loss = val_loss
                    patience_counter = 0
                    self.save_checkpoint('best_model.pth')
                else:
                    patience_counter += 1
                    if patience_counter >= early_stopping_patience:
                        print(f'\nEarly stopping triggered after {epoch + 1} epochs')
                        break
        
        return self.history
    
    def save_checkpoint(self, path: str):
        """Save model checkpoint"""
        torch.save({
            'model_state_dict': self.model.state_dict(),
            'optimizer_state_dict': self.optimizer.state_dict(),
            'history': self.history
        }, path)
        print(f'Checkpoint saved to {path}')
    
    def load_checkpoint(self, path: str):
        """Load model checkpoint"""
        checkpoint = torch.load(path)
        self.model.load_state_dict(checkpoint['model_state_dict'])
        self.optimizer.load_state_dict(checkpoint['optimizer_state_dict'])
        self.history = checkpoint['history']
        print(f'Checkpoint loaded from {path}')


# Usage Example
if __name__ == '__main__':
    # Create model
    model = YourModel()
    
    # Create data loaders
    train_loader = DataLoader(train_dataset, batch_size=32, shuffle=True)
    val_loader = DataLoader(val_dataset, batch_size=32, shuffle=False)
    
    # Define loss and optimizer
    criterion = nn.CrossEntropyLoss()
    optimizer = optim.Adam(model.parameters(), lr=0.001)
    scheduler = optim.lr_scheduler.ReduceLROnPlateau(
        optimizer, mode='min', patience=3, factor=0.5
    )
    
    # Create trainer
    trainer = ModelTrainer(
        model=model,
        train_loader=train_loader,
        val_loader=val_loader,
        criterion=criterion,
        optimizer=optimizer,
        scheduler=scheduler,
        device='cuda' if torch.cuda.is_available() else 'cpu'
    )
    
    # Train
    history = trainer.fit(epochs=50, early_stopping_patience=5)
```

---

## 💬 Описание

Универсальный класс для обучения PyTorch моделей с поддержкой:
- Progress bars (tqdm)
- Learning rate scheduling
- Early stopping
- Checkpointing
- Training history tracking

### Когда использовать
- Быстрое прототипирование ML моделей
- Стандартизация процесса обучения
- Эксперименты с разными архитектурами

### Параметры
- **model:** PyTorch модель (nn.Module)
- **train_loader:** DataLoader для training данных
- **val_loader:** DataLoader для validation данных
- **criterion:** Loss function
- **optimizer:** Optimizer (Adam, SGD, etc.)
- **device:** 'cuda' или 'cpu'
- **scheduler:** (Optional) Learning rate scheduler

---

## 💻 Примеры использования

### Пример 1: Базовое использование

```python
# Define simple CNN
class SimpleCNN(nn.Module):
    def __init__(self, num_classes=10):
        super().__init__()
        self.features = nn.Sequential(
            nn.Conv2d(3, 64, 3, padding=1),
            nn.ReLU(),
            nn.MaxPool2d(2),
            nn.Conv2d(64, 128, 3, padding=1),
            nn.ReLU(),
            nn.MaxPool2d(2),
        )
        self.classifier = nn.Sequential(
            nn.Linear(128 * 8 * 8, 512),
            nn.ReLU(),
            nn.Dropout(0.5),
            nn.Linear(512, num_classes)
        )
    
    def forward(self, x):
        x = self.features(x)
        x = x.view(x.size(0), -1)
        x = self.classifier(x)
        return x

# Create and train
model = SimpleCNN(num_classes=10)
trainer = ModelTrainer(
    model=model,
    train_loader=train_loader,
    val_loader=val_loader,
    criterion=nn.CrossEntropyLoss(),
    optimizer=optim.Adam(model.parameters(), lr=0.001)
)
history = trainer.fit(epochs=30, early_stopping_patience=5)
```

**Вывод:**
```
Epoch 1/30
--------------------------------------------------
Training: 100%|██████████| 1875/1875 [00:45<00:00, loss: 0.4532, acc: 84.32]
Validation: 100%|██████████| 313/313 [00:05<00:00]
Train Loss: 0.4532, Acc: 84.32%
Val Loss: 0.3421, Acc: 87.45%
```

### Пример 2: С learning rate scheduler

```python
from torch.optim.lr_scheduler import ReduceLROnPlateau

model = SimpleCNN()
optimizer = optim.Adam(model.parameters(), lr=0.001)
scheduler = ReduceLROnPlateau(
    optimizer,
    mode='min',
    patience=3,
    factor=0.5,
    verbose=True
)

trainer = ModelTrainer(
    model=model,
    train_loader=train_loader,
    val_loader=val_loader,
    criterion=nn.CrossEntropyLoss(),
    optimizer=optimizer,
    scheduler=scheduler
)

history = trainer.fit(epochs=50, early_stopping_patience=7)

# Plot training curves
import matplotlib.pyplot as plt

plt.figure(figsize=(12, 4))
plt.subplot(1, 2, 1)
plt.plot(history['train_loss'], label='Train Loss')
plt.plot(history['val_loss'], label='Val Loss')
plt.legend()
plt.title('Loss')

plt.subplot(1, 2, 2)
plt.plot(history['train_acc'], label='Train Acc')
plt.plot(history['val_acc'], label='Val Acc')
plt.legend()
plt.title('Accuracy')
plt.show()
```

---

## ⚙️ Конфигурация

### Зависимости
```bash
pip install torch torchvision tqdm matplotlib
```

### Переменные окружения
```bash
# Optional: specify CUDA device
export CUDA_VISIBLE_DEVICES=0
```

---

## 🎯 Use Cases

1. **Image Classification**
   - CNN models для CIFAR-10, ImageNet
   - Transfer learning с pre-trained models

2. **Natural Language Processing**
   - RNN/LSTM для text classification
   - Transformer models

3. **Time Series**
   - LSTM для предсказания временных рядов
   - Anomaly detection

---

## 💡 Tips & Tricks

- **Совет 1:** Используй ReduceLROnPlateau для автоматической настройки learning rate
- **Совет 2:** Early stopping предотвращает overfitting
- **Совет 3:** Сохраняй лучшую модель по validation loss, не по accuracy
- **Совет 4:** Mixed precision training (torch.cuda.amp) ускоряет обучение на современных GPU

---

## ⚠️ Важные моменты

- **Performance:** tqdm может немного замедлять обучение, можно отключить в production
- **Security:** Не загружай checkpoints из ненадежных источников (torch.load небезопасен)
- **Compatibility:** Требует PyTorch 1.9+

---

## 🔗 Связанные сниппеты

- [[Snippets/Python/Data-Loading|Data Loading & Preprocessing]]
- [[Snippets/Python/Model-Evaluation|Model Evaluation Metrics]]

---

## 📚 Ресурсы

- [PyTorch Official Tutorial](https://pytorch.org/tutorials/)
- [Training Neural Networks Best Practices](https://karpathy.github.io/2019/04/25/recipe/)
- [PyTorch Lightning](https://www.pytorchlightning.ai/) - More advanced training framework

---

*Создано: 2024-02-15*  
*Обновлено: `=date(today)`*
