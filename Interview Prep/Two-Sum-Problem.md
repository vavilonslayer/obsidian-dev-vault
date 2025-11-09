---
type: interview-question
category: "Algorithms"
difficulty: "Medium"
mastery: 65
reviewed: 2024-03-01
tags: [interview, algorithms, arrays, two-pointers]
---

# 💬 Two Sum Problem

**Категория:** Algorithms - Arrays  
**Сложность:** 🟡 Medium  
**Прогресс изучения:** ![progress](https://progress-bar.dev/65/?title=Mastery&width=180&color=6554c0)  
**Дата повторения:** 2024-03-01

---

## 📝 Вопрос

Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

**Пример:**
```
Input: nums = [2,7,11,15], target = 9
Вывод: [0,1]
Explanation: nums[0] + nums[1] == 9, return [0,1]
```

---

## ✅ Ответ

### Краткий ответ

Использовать hash map (dictionary) для хранения уже просмотренных элементов. Для каждого элемента проверяем, существует ли в map значение `target - current_element`. Если да - возвращаем индексы. Если нет - добавляем текущий элемент в map.

**Сложность:** O(n) время, O(n) память

### Развернутый ответ

**Подход 1: Brute Force (не оптимальный)**
- Проверить каждую пару элементов
- Время: O(n²), Память: O(1)
- Не подходит для больших массивов

**Подход 2: Hash Map (оптимальный)**
- За один проход создаем map: {значение: индекс}
- Для каждого элемента ищем complement = target - element
- Если complement есть в map - нашли решение
- Время: O(n), Память: O(n)

**Почему это работает:**
Если a + b = target, то b = target - a. Сохраняя все элементы в hash map, мы можем за O(1) проверить существование complement.

---

## 💻 Примеры кода

### Пример 1: Hash Map Решение

```python
def two_sum(nums: list[int], target: int) -> list[int]:
    """
    Find two numbers that add up to target
    Время: O(n), Память: O(n)
    """
    seen = {}  # {value: index}
    
    for i, num in enumerate(nums):
        complement = target - num
        
        if complement in seen:
            return [seen[complement], i]
        
        seen[num] = i
    
    return []  # No solution found

# Test
nums = [2, 7, 11, 15]
target = 9
print(two_sum(nums, target))  # Вывод: [0, 1]
```

**Сложность:** O(n)  
**Пространство:** O(n)

### Пример 2: With Error Handling

```python
def two_sum_safe(nums: list[int], target: int) -> list[int]:
    """
    Two sum with input validation
    """
    if not nums or len(nums) < 2:
        raise ValueError("Array must have at least 2 elements")
    
    seen = {}
    
    for i, num in enumerate(nums):
        complement = target - num
        
        if complement in seen:
            return [seen[complement], i]
        
        seen[num] = i
    
    raise ValueError("No solution exists")

# Использование
try:
    result = two_sum_safe([2, 7, 11, 15], 9)
    print(f"Indices: {result}")
except ValueError as e:
    print(f"Error: {e}")
```

### Пример 3: Alternative - Sorted Array

```python
def two_sum_sorted(nums: list[int], target: int) -> list[int]:
    """
    If array is sorted, use two pointers
    Время: O(n), Память: O(1) (excluding sort)
    Note: Returns values, not original indices
    """
    left, right = 0, len(nums) - 1
    
    while left < right:
        current_sum = nums[left] + nums[right]
        
        if current_sum == target:
            return [left, right]
        elif current_sum < target:
            left += 1
        else:
            right -= 1
    
    return []
```

---

## 🔑 Ключевые моменты

- **Важно упомянуть:**
  - Trade-off между временем и памятью
  - Hash map дает O(1) lookup
  - Альтернативный подход с sorted array (two pointers)
  - Edge cases: пустой массив, недостаточно элементов
  
- **Типичные ошибки:**
  - Забыть проверить complement в map перед добавлением текущего элемента
  - Использовать один и тот же индекс дважды
  - Не обработать случай, когда решения нет
  - O(n²) brute force решение вместо O(n)

- **Бонусные темы:**
  - Three Sum вариация (3 элемента)
  - Four Sum вариация
  - Two Sum с sorted array
  - Two Sum с дубликатами

---

## 🎯 Follow-up вопросы

1. **Как изменится решение, если нужно найти все пары?**
   - Нужно продолжать искать после первой пары
   - Учитывать дубликаты

2. **Что если массив отсортирован?**
   - Можно использовать two pointers для O(1) памяти
   - Binary search для каждого complement

3. **Как решить Three Sum?**
   - Фиксируем один элемент, применяем Two Sum к остальным
   - Время: O(n²), Память: O(1)

---

## 📚 Связанные темы

- [[Interview Prep/Three-Sum|Three Sum Problem]]
- [[Interview Prep/Two-Pointers-Pattern|Two Pointers Pattern]]
- [[Notes/Algorithms/Hash-Tables|Hash Tables]]

---

## 🔗 Ресурсы

### Статьи и документация
- [LeetCode - Two Sum](https://leetcode.com/problems/two-sum/)
- [Hash Table Complexity](https://en.wikipedia.org/wiki/Hash_table)

### Видео
- [NeetCode - Two Sum Explanation](https://www.youtube.com/watch?v=KLlXCFG5TnA)

---

## 📊 История изучения

- **Первое изучение:** 2024-02-01
- **Повторения:** 3
- **Последнее повторение:** 2024-03-01
- **Следующее повторение:** 2024-03-15

### Прогресс
- 2024-02-01: 30% - Первое знакомство
- 2024-02-10: 50% - Освоил hash map подход
- 2024-03-01: 65% - Могу решить без подсказок

---

## 💡 Примечания

### Мои заметки
- Важно четко объяснять trade-off между временем и памятью
- Всегда упоминать edge cases
- Можно начать с brute force, затем оптимизировать
- Хорошо знать вариации (Three Sum, Four Sum)

### Tips для собеседования
1. Начать с примера и понять проблему
2. Обсудить brute force подход (O(n²))
3. Предложить оптимизацию с hash map
4. Написать код с проверками
5. Обсудить edge cases
6. Проанализировать complexity
7. Упомянуть альтернативные подходы

---

## ✅ Чек-лист подготовки

- [x] Понял основную концепцию
- [x] Могу объяснить своими словами
- [x] Написал код без подсказок
- [x] Знаю сложность алгоритма
- [x] Понимаю edge cases
- [ ] Готов к follow-up вопросам (нужно повторить Three Sum)

---

*Создано: 2024-02-01*  
*Обновлено: `=date(today)`*
