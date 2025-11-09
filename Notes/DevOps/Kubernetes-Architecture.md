# Kubernetes Architecture

**Tags:** #devops #kubernetes #architecture

---

## 📝 Обзор

Kubernetes - это платформа для оркестрации контейнеров, автоматизирующая развертывание, масштабирование и управление containerized приложениями.

---

## 🏗️ Основные компоненты

### Control Plane
Управляющий уровень кластера

#### 1. API Server (kube-apiserver)
- **Функция:** Frontend для Kubernetes control plane
- **Задачи:** 
  - Обработка REST операций
  - Валидация и конфигурация данных
  - Обеспечение связи между компонентами

#### 2. etcd
- **Функция:** Distributed key-value store
- **Задачи:**
  - Хранение всей cluster data
  - Источник истины для desired state
  - Highly available

#### 3. Scheduler (kube-scheduler)
- **Функция:** Размещение pods на nodes
- **Задачи:**
  - Выбор оптимального node для pod
  - Учет ресурсов, constraints, affinity rules

#### 4. Controller Manager (kube-controller-manager)
- **Функция:** Запуск controller processes
- **Контроллеры:**
  - Node Controller
  - Replication Controller
  - Endpoints Controller
  - Service Account Controller

#### 5. Cloud Controller Manager
- **Функция:** Интеграция с cloud providers
- **Задачи:**
  - Управление cloud-specific ресурсами
  - Load balancers, storage volumes

---

### Worker Nodes
Рабочие узлы, где запускаются приложения

#### 1. Kubelet
- **Функция:** Agent на каждом node
- **Задачи:**
  - Запуск pods
  - Мониторинг состояния
  - Связь с API server

#### 2. Kube-proxy
- **Функция:** Network proxy
- **Задачи:**
  - Управление network rules
  - Обеспечение connectivity к services
  - Load balancing

#### 3. Container Runtime
- **Функция:** Запуск контейнеров
- **Примеры:** Docker, containerd, CRI-O

---

## 🔄 Архитектура

```
┌─────────────────────────────────────────┐
│           Control Plane                 │
│  ┌──────────┐  ┌──────┐  ┌───────────┐│
│  │API Server│  │ etcd │  │ Scheduler ││
│  └──────────┘  └──────┘  └───────────┘│
│  ┌─────────────────────────────────┐  │
│  │   Controller Manager            │  │
│  └─────────────────────────────────┘  │
└─────────────────────────────────────────┘
              │
              │ kubectl
              ▼
┌─────────────────────────────────────────┐
│         Worker Nodes                     │
│  ┌────────────────────────────────────┐│
│  │  Node 1                            ││
│  │  ┌────────┐  ┌───────────────┐   ││
│  │  │Kubelet │  │  Kube-proxy   │   ││
│  │  └────────┘  └───────────────┘   ││
│  │  ┌────────────────────────────┐  ││
│  │  │    Container Runtime       │  ││
│  │  │  ┌───┐  ┌───┐  ┌───┐      │  ││
│  │  │  │Pod│  │Pod│  │Pod│      │  ││
│  │  │  └───┘  └───┘  └───┘      │  ││
│  │  └────────────────────────────┘  ││
│  └────────────────────────────────────┘│
└─────────────────────────────────────────┘
```

---

## 🎯 Ключевые концепции

### Desired State vs Current State
- **Desired State:** Что вы хотите
- **Current State:** Что есть сейчас
- **Kubernetes:** Постоянно работает над тем, чтобы current state = desired state

### Declarative Configuration
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx
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
```

---

## 💡 Основные объекты

### 1. Pod
- Smallest deployable unit
- Один или несколько контейнеров
- Shared network и storage

### 2. Deployment
- Управляет ReplicaSets
- Rolling updates
- Rollback capability

### 3. Service
- Stable network endpoint
- Load balancing между pods
- Service discovery

### 4. Namespace
- Virtual clusters
- Изоляция ресурсов
- Multi-tenancy

---

## 🔧 Работа с кластером

### Основные команды

```bash
# Информация о кластере
kubectl cluster-info

# Просмотр nodes
kubectl get nodes

# Просмотр pods
kubectl get pods -A

# Описание ресурса
kubectl describe pod <pod-name>

# Логи
kubectl logs <pod-name>

# Exec в контейнер
kubectl exec -it <pod-name> -- /bin/bash

# Apply конфигурации
kubectl apply -f deployment.yaml

# Удаление ресурса
kubectl delete -f deployment.yaml
```

---

## 📊 High Availability

### Control Plane HA
- Multiple API servers за load balancer
- Multiple etcd instances (odd number: 3, 5, 7)
- Multiple controller managers (leader election)

### Worker Node HA
- Multiple worker nodes
- Pod replicas распределены по nodes
- Node failure → pods перезапускаются на других nodes

---

## 🔗 Связанные темы

- [[Courses/DevOps/Kubernetes-Deep-Dive|Kubernetes Course]]
- [[Notes/DevOps/Docker|Docker]]
- [[Notes/DevOps/Service-Mesh|Service Mesh]]

---

## 💡 Best Practices

1. **Resource Limits:** Всегда задавайте requests и limits
2. **Health Checks:** Используйте liveness и readiness probes
3. **Labels:** Правильная организация через labels
4. **Namespaces:** Изолируйте окружения
5. **RBAC:** Настройте правильные permissions
6. **Monitoring:** Используйте Prometheus + Grafana

---

*Создано: 2024-02-18*
