---
type: interview-question
category: "DevOps"
difficulty: "Medium"
mastery: 45
reviewed: 2024-03-05
tags: [interview, devops, kubernetes, deployment]
---

# 💬 Explain Blue-Green Deployment

**Категория:** DevOps - Deployment Strategies  
**Сложность:** 🟡 Medium  
**Прогресс изучения:** ![progress](https://progress-bar.dev/45/?title=Mastery&width=180&color=6554c0)  
**Дата повторения:** 2024-03-05

---

## 📝 Вопрос

What is Blue-Green Deployment? Explain the process, benefits, and potential challenges.

---

## ✅ Ответ

### Краткий ответ

Blue-Green Deployment - это стратегия развертывания, при которой поддерживаются две идентичные production среды (Blue и Green). Одна среда (например, Blue) обслуживает production трафик, а другая (Green) используется для развертывания новой версии. После проверки Green среды трафик переключается на нее, а Blue становится standby.

**Ключевые преимущества:**
- Zero downtime deployment
- Instant rollback
- Полное тестирование перед переключением

### Развернутый ответ

#### Как работает Blue-Green Deployment

**1. Начальное состояние:**
- Blue environment обслуживает production трафик
- Green environment идентичен, но idle

**2. Процесс деплоя:**
- Разворачиваем новую версию в Green environment
- Проводим тестирование в Green
- Smoke tests, integration tests
- Проверяем, что все работает корректно

**3. Переключение трафика:**
- Изменяем routing (load balancer, DNS)
- Весь трафик перенаправляется на Green
- Blue становится standby

**4. Rollback (если нужен):**
- Быстро переключаем трафик обратно на Blue
- Instant rollback без downtime

#### Преимущества

**Zero Downtime:**
- Пользователи не видят перерыва в работе
- Переключение занимает секунды

**Fast Rollback:**
- Если проблемы - переключаемся обратно
- Blue environment все еще содержит старую версию

**Full Testing:**
- Можно полностью протестировать новую версию
- В production-like environment
- Перед переключением пользователей

**Disaster Recovery:**
- Всегда есть backup environment
- Можно быстро переключиться при проблемах

#### Недостатки и вызовы

**Resource Cost:**
- Требует 2x resources
- Две полные production среды

**Database Challenges:**
- Миграции БД сложны
- Обе среды часто используют одну БД
- Backward compatibility необходима

**Stateful Applications:**
- Сложно для stateful apps
- Session management
- In-memory data

**Testing Completeness:**
- Сложно протестировать все сценарии
- Production трафик может выявить проблемы

---

## 💻 Примеры кода

### Пример 1: Kubernetes Blue-Green с Service

```yaml
# Blue Deployment
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app-blue
  labels:
    app: myapp
    version: blue
spec:
  replicas: 3
  selector:
    matchLabels:
      app: myapp
      version: blue
  template:
    metadata:
      labels:
        app: myapp
        version: blue
    spec:
      containers:
      - name: app
        image: myapp:1.0.0
        ports:
        - containerPort: 8080

---
# Green Deployment
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app-green
  labels:
    app: myapp
    version: green
spec:
  replicas: 3
  selector:
    matchLabels:
      app: myapp
      version: green
  template:
    metadata:
      labels:
        app: myapp
        version: green
    spec:
      containers:
      - name: app
        image: myapp:2.0.0
        ports:
        - containerPort: 8080

---
# Service initially points to Blue
apiVersion: v1
kind: Service
metadata:
  name: myapp-service
spec:
  selector:
    app: myapp
    version: blue  # Switch to 'green' for cutover
  ports:
  - protocol: TCP
    port: 80
    targetPort: 8080
  type: LoadBalancer
```

**Переключение:**
```bash
# Update service to point to Green
kubectl patch service myapp-service -p '{"spec":{"selector":{"version":"green"}}}'

# Rollback if needed
kubectl patch service myapp-service -p '{"spec":{"selector":{"version":"blue"}}}'
```

### Пример 2: Terraform Blue-Green на AWS

```hcl
# Blue environment
resource "aws_instance" "blue" {
  count         = var.environment == "blue" ? 3 : 0
  ami           = var.blue_ami
  instance_type = "t3.medium"
  
  tags = {
    Name        = "app-blue"
    Environment = "blue"
  }
}

# Green environment
resource "aws_instance" "green" {
  count         = var.environment == "green" ? 3 : 0
  ami           = var.green_ami
  instance_type = "t3.medium"
  
  tags = {
    Name        = "app-green"
    Environment = "green"
  }
}

# Load Balancer
resource "aws_lb_target_group" "blue" {
  name     = "app-blue-tg"
  port     = 80
  protocol = "HTTP"
  vpc_id   = var.vpc_id
}

resource "aws_lb_target_group" "green" {
  name     = "app-green-tg"
  port     = 80
  protocol = "HTTP"
  vpc_id   = var.vpc_id
}

# Listener rule for switching
resource "aws_lb_listener_rule" "main" {
  listener_arn = aws_lb_listener.main.arn
  priority     = 100

  action {
    type             = "forward"
    target_group_arn = var.active_env == "blue" ? 
                       aws_lb_target_group.blue.arn : 
                       aws_lb_target_group.green.arn
  }

  condition {
    path_pattern {
      values = ["/*"]
    }
  }
}
```

**Переключение:**
```bash
# Switch to green
terraform apply -var="active_env=green"

# Rollback to blue
terraform apply -var="active_env=blue"
```

### Пример 3: Shell Script для переключения

```bash
#!/bin/bash
# blue-green-switch.sh

CURRENT_ENV=$(kubectl get service myapp -o jsonpath='{.spec.selector.version}')
NEW_ENV=""

if [ "$CURRENT_ENV" == "blue" ]; then
    NEW_ENV="green"
else
    NEW_ENV="blue"
fi

echo "Current environment: $CURRENT_ENV"
echo "Switching to: $NEW_ENV"

# Verify new environment is healthy
echo "Checking $NEW_ENV health..."
REPLICAS=$(kubectl get deployment app-$NEW_ENV -o jsonpath='{.status.readyReplicas}')
DESIRED=$(kubectl get deployment app-$NEW_ENV -o jsonpath='{.spec.replicas}')

if [ "$REPLICAS" != "$DESIRED" ]; then
    echo "Error: $NEW_ENV is not healthy. $REPLICAS/$DESIRED replicas ready."
    exit 1
fi

# Switch traffic
echo "Switching traffic to $NEW_ENV..."
kubectl patch service myapp -p "{\"spec\":{\"selector\":{\"version\":\"$NEW_ENV\"}}}"

echo "Traffic switched to $NEW_ENV"
echo "Old environment ($CURRENT_ENV) is now standby"

# Monitor for issues
echo "Monitoring for 60 seconds..."
sleep 60

# Check for errors
ERRORS=$(kubectl logs -l version=$NEW_ENV --tail=100 | grep -i error | wc -l)
if [ $ERRORS -gt 10 ]; then
    echo "Warning: High error rate detected. Consider rollback."
fi
```

---

## 🔑 Ключевые моменты

- **Важно упомянуть:**
  - Zero downtime deployment capability
  - Instant rollback mechanism
  - Database migration challenges
  - Resource cost (2x infrastructure)
  - Testing before cutover
  - Load balancer/router role
  
- **Типичные ошибки:**
  - Забыть про database compatibility
  - Не протестировать Green перед переключением
  - Игнорировать stateful data
  - Не планировать rollback процедуру
  - Недооценивать resource costs

- **Бонусные темы:**
  - Canary deployments (gradual rollout)
  - A/B testing integration
  - Feature flags для zero-downtime
  - Database migration strategies
  - Monitoring during cutover

---

## 🎯 Follow-up вопросы

1. **Как решить проблему с database migrations?**
   - Backward-compatible migrations
   - Separate database layer
   - Feature flags
   - Two-phase commit

2. **Чем Blue-Green отличается от Canary?**
   - Blue-Green: 100% traffic switch
   - Canary: Gradual rollout (10% → 50% → 100%)
   - Blue-Green: Easier rollback
   - Canary: More control, less risk

3. **Как обрабатывать stateful applications?**
   - Session replication
   - Sticky sessions
   - External state store (Redis, DB)
   - Drain existing connections before switch

---

## 📚 Связанные темы

- [[Interview Prep/Canary-Deployment|Canary Deployment]]
- [[Interview Prep/Rolling-Updates|Rolling Updates]]
- [[Notes/DevOps/Kubernetes-Architecture|Kubernetes Architecture]]
- [[Notes/DevOps/Load-Balancing|Load Balancing]]

---

## 🔗 Ресурсы

### Статьи и документация
- [Martin Fowler - Blue-Green Deployment](https://martinfowler.com/bliki/BlueGreenDeployment.html)
- [AWS Blue-Green Deployments](https://docs.aws.amazon.com/whitepapers/latest/blue-green-deployments/)
- [Kubernetes Deployment Strategies](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)

### Видео
- [Blue-Green Deployment Explained](https://www.youtube.com/watch?v=example)

---

## 📊 История изучения

- **Первое изучение:** 2024-02-15
- **Повторения:** 2
- **Последнее повторение:** 2024-03-05
- **Следующее повторение:** 2024-03-20

### Прогресс
- 2024-02-15: 20% - Первое знакомство
- 2024-03-05: 45% - Понимаю концепцию, практиковал в K8s

---

## 💡 Примечания

### Мои заметки
- Использовал Blue-Green в проекте с Kubernetes
- Service selector switching работает отлично
- Database migrations - самый сложный аспект
- Important to have monitoring во время cutover

### Tips для собеседования
1. Начать с определения и диаграммы
2. Объяснить процесс step-by-step
3. Упомянуть преимущества и недостатки
4. Обсудить практические challenges (DB, state)
5. Сравнить с другими стратегиями (Canary, Rolling)
6. Привести пример из опыта

---

## ✅ Чек-лист подготовки

- [x] Понял основную концепцию
- [x] Могу объяснить своими словами
- [ ] Могу реализовать в K8s/AWS
- [x] Знаю преимущества и недостатки
- [ ] Понимаю database challenges
- [ ] Готов к follow-up вопросам

---

*Создано: 2024-02-15*  
*Обновлено: `=date(today)`*
