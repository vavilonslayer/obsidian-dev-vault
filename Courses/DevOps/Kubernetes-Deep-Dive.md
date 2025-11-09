---
type: course
source: "Udemy - Docker & Kubernetes: The Complete Guide"
progress: 55
status: "В процессе"
started: 2024-02-01
completed: 
tags: [course, devops, kubernetes, docker]
---

# 📚 Kubernetes Deep Dive

**Тип:** 📚 Курс  
**Источник:** Udemy - Docker & Kubernetes: The Complete Guide  
**Прогресс:** ![progress](https://progress-bar.dev/55/?title=Kubernetes&width=180&color=36b37e)  
**Статус:** В процессе

---

## 📘 Описание курса

*Глубокое погружение в Kubernetes для production deployments*

### 🎯 Цели обучения
- Понять архитектуру Kubernetes
- Научиться деплоить приложения в K8s
- Освоить Helm, Ingress, Service Mesh
- Изучить best practices для production

### 📋 Содержание
1. Kubernetes Basics ✅
2. Pods & Deployments ✅
3. Services & Networking ✅
4. ConfigMaps & Secrets 🔄 50%
5. Persistent Storage ⏳
6. Helm Charts ⏳
7. Monitoring & Logging ⏳

---

## 📝 Конспект

### Модуль 1: Kubernetes Architecture
- **Основные компоненты:**
  - Control Plane (API Server, Scheduler, Controller Manager)
  - Worker Nodes (Kubelet, Kube-proxy, Container Runtime)
  - etcd - distributed key-value store

- **Ключевые концепции:**
  - Desired state vs Current state
  - Declarative configuration
  - Self-healing

### Модуль 2: Pods & Deployments
- **Pods:**
  - Smallest deployable unit
  - Multi-container pods
  - Init containers
  - Lifecycle hooks

- **Deployments:**
  - Rolling updates
  - Rollback strategies
  - Scaling (manual and auto)

### Модуль 3: Services & Networking (Current)
- **Service Types:**
  - ClusterIP
  - NodePort
  - LoadBalancer
  - ExternalName

- **Ingress:**
  - Ingress controllers
  - Path-based routing
  - TLS termination

---

## 💡 Ключевые идеи

> Самые важные выводы и концепции

- **Идея 1:** Kubernetes управляет desired state, а не императивными командами
- **Идея 2:** Services обеспечивают stable networking для pods
- **Идея 3:** Labels и selectors - основа организации ресурсов
- **Идея 4:** Namespaces изолируют ресурсы в одном кластере

---

## 💻 Примеры кода

### Пример 1: Basic Deployment

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.21
        ports:
        - containerPort: 80
        resources:
          requests:
            memory: "64Mi"
            cpu: "250m"
          limits:
            memory: "128Mi"
            cpu: "500m"
```

**Объяснение:**
- Deployment создает 3 реплики nginx pods
- Resource limits защищают от перегрузки
- Labels используются для селекции pods

### Пример 2: Service with Ingress

```yaml
---
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  selector:
    app: nginx
  ports:
  - protocol: TCP
    port: 80
    targetPort: 80
  type: ClusterIP

---
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: nginx-ingress
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  rules:
  - host: myapp.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: nginx-service
            port:
              number: 80
  tls:
  - hosts:
    - myapp.example.com
    secretName: tls-secret
```

---

## 🧪 Практические задания

- [x] Задание 1: Deploy simple application to K8s
- [x] Задание 2: Implement rolling update strategy
- [x] Задание 3: Configure service networking
- [ ] Задание 4: Set up Ingress with TLS
- [ ] Задание 5: Implement persistent storage
- [ ] Задание 6: Create Helm chart

---

## 📈 Мой прогресс

### Пройденные модули
- [x] Kubernetes Architecture
- [x] Pods & Deployments
- [x] Services
- [x] Networking basics
- [ ] ConfigMaps & Secrets (50%)
- [ ] Storage
- [ ] Helm
- [ ] Monitoring

### Временные затраты
- **Всего времени:** 32 часа
- **Среднее время на модуль:** 6 часов

---

## 🔗 Ресурсы

### Ссылки
- [Kubernetes Official Docs](https://kubernetes.io/docs/)
- [GitHub с примерами](https://github.com/username/k8s-examples)
- [CNCF Landscape](https://landscape.cncf.io)

### Связанные заметки
- [[Notes/DevOps/K8s-Architecture|Kubernetes Architecture]]
- [[Notes/DevOps/Service-Mesh|Service Mesh]]
- [[Notes/DevOps/Helm-Charts|Helm Charts]]

---

## 📊 Оценка курса

**Сложность:** 🟡 Средняя  
**Полезность:** ⭐⭐⭐⭐⭐  
**Рекомендую:** ✅ Да

### Отзыв
Очень практический курс. Много hands-on заданий. Instructor хорошо объясняет сложные концепции. После курса чувствую себя уверенно с K8s.

---

## 💬 Заметки

- Важно практиковаться на реальном кластере (minikube для локальной разработки)
- Kubectl - must know инструмент
- Полезно изучить kubectl cheat sheet
- Community на Slack очень активное

---

*Создано: 2024-02-01*  
*Обновлено: `=date(today)`*
