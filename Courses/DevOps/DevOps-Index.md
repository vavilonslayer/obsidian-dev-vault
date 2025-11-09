# ⚙️ DevOps Engineering

> *Инфраструктура, автоматизация и надежность*

---

## 📊 Общий прогресс

![DevOps Progress](https://progress-bar.dev/45/?title=DevOps%20Skills&width=300&color=36b37e)

**Завершено курсов:** 2  
**В процессе:** 2  
**Запланировано:** 4

---

## 📚 Курсы

### 🟢 Завершенные
- [[Courses/DevOps/Docker-Fundamentals|Docker Fundamentals]] - ⭐⭐⭐⭐⭐
- [[Courses/DevOps/Git-Advanced|Git Advanced]] - ⭐⭐⭐⭐

### 🟡 В процессе
- [[Courses/DevOps/Kubernetes-Deep-Dive|Kubernetes Deep Dive]] - 55%
- [[Courses/DevOps/CI-CD-Pipeline|CI/CD Pipeline]] - 35%

### ⚪ Запланированные
- Terraform & Infrastructure as Code
- Monitoring & Observability
- AWS Certified Solutions Architect
- Security Best Practices

---

## 💻 Проекты

### Активные проекты
```dataview
TABLE 
  status as "Статус",
  progress as "Прогресс"
FROM "Projects"
WHERE contains(tags, "devops")
SORT progress DESC
```

---

## 🧠 Темы для изучения

### Контейнеризация
- [x] Docker basics
- [x] Docker Compose
- [ ] Multi-stage builds
- [ ] Security best practices

### Оркестрация
- [x] Kubernetes basics
- [ ] Helm charts
- [ ] Service mesh
- [ ] Operators

### CI/CD
- [ ] GitHub Actions
- [ ] GitLab CI
- [ ] Jenkins
- [ ] ArgoCD

### Infrastructure as Code
- [ ] Terraform
- [ ] Ansible
- [ ] CloudFormation
- [ ] Pulumi

### Monitoring
- [ ] Prometheus
- [ ] Grafana
- [ ] ELK Stack
- [ ] Jaeger

---

## 📝 Заметки и ресурсы

### Важные концепции
- [[Notes/DevOps/Container-Orchestration|Container Orchestration]]
- [[Notes/DevOps/GitOps|GitOps]]
- [[Notes/DevOps/Blue-Green-Deployment|Blue-Green Deployment]]

### Инструменты

#### Контейнеризация
- Docker
- Podman
- containerd

#### Оркестрация
- Kubernetes
- Docker Swarm
- Nomad

#### CI/CD
- GitHub Actions
- GitLab CI
- Jenkins
- CircleCI

#### IaC
- Terraform
- Ansible
- Pulumi

---

## 🔗 Полезные ресурсы

### Онлайн курсы
- [Kubernetes Official Training](https://kubernetes.io/training/)
- [Docker Official Docs](https://docs.docker.com)
- [AWS Training](https://aws.amazon.com/training/)

### Книги
- The Phoenix Project
- The DevOps Handbook
- Site Reliability Engineering (Google)
- Kubernetes Up & Running

### Сертификации
- CKA (Certified Kubernetes Administrator)
- CKAD (Certified Kubernetes App Developer)
- AWS Solutions Architect
- Terraform Associate

---

## 📊 Статистика

```dataview
TABLE 
  progress as "Прогресс",
  source as "Источник"
FROM "Courses/DevOps"
WHERE file.name != "DevOps-Index"
SORT progress DESC
```

---

*[[Dashboard|← Назад на Dashboard]]*
