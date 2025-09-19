# [Сосисочная у дома](https://front-iisakov.2sem.students-projects.ru) 🛒
[Сосисочная у дома](https://front-iisakov.2sem.students-projects.ru) это проект семестровой работы студента первого курса специальности DevOps - развертывание полнофункционального веб-приложения интернет-магазина на платформе Kubernetes с использованием пакетного менеджера Helm.

## 🏗️ Архитектура проекта
### Микросервисная структура:
- Frontend - Angular приложение
- Backend - Java Spring Boot API
- Backend-Report - Go сервис для отчетности
- Базы данных - PostgreSQL и MongoDB

### Технологический стек:
- Kubernetes - оркестрация контейнеров 
- Helm - пакетный менеджер для развертывания 
- Docker - контейнеризация приложений 
- PostgreSQL - реляционная база данных 
- MongoDB - документоориентированная БД 
- Java Spring Boot - основной backend 
- Golang - сервис отчетности 
- Angular - фронтенд приложение

## 📁 Структура проекта
```text
sausage-store/
├── sausage-store-chart/     # Helm chart основного приложения
│   ├── charts/
│   │   ├── backend/         # Java backend
│   │   ├── backend-report/  # Go report service
│   │   ├── frontend/        # Angular frontend
│   │   └── infra/           # Базы данных (PostgreSQL + MongoDB)
│   └── values.yaml          # Конфигурационные значения
├── backend/                 # Исходный код Java приложения
├── backend-report/          # Исходный код Go сервиса
├── frontend/                # Исходный код Angular приложения
├── podinfo/                 # Дополнительный Helm chart
└── docker-compose.yml       # Локальная разработка
```

## 🚀 Быстрый старт


### Предварительные требования:
- Kubernetes кластер
- Helm 3+
- kubectl

### Установка:
```bash
# Добавление репозитория (если необходимо)
helm repo add sausage-store /path/to/chart

# Установка приложения
helm install sausage-store sausage-store-chart/
Обновление:
bash
helm upgrade sausage-store sausage-store-chart/
```
## ⚙️ Конфигурация
### Основные настройки в sausage-store-chart/values.yaml:
- Ресурсы CPU/Memory для каждого сервиса
- Параметры баз данных
- Настройки репликации
- Конфигурация ingress

## 📊 Мониторинг
Приложение включает:

- Health checks для всех сервисов
- Prometheus метрики
- Готовность к горизонтальному масштабированию (HPA)

## 🛠️ Разработка
### Локальный запуск:
```bash
docker-compose up -d
```
### Сборка образов:
```bash
docker build -t sausage-store-backend ./backend
docker build -t sausage-store-frontend ./frontend
docker build -t sausage-store-report ./backend-report
```

## 📝 Особенности реализации
- Миграции БД через Flyway для PostgreSQL
- ConfigMap и Secrets для управления конфигурацией
- Resource quotas для контроля ресурсов
- Persistent volumes для хранения данных
- Service discovery через Kubernetes DNS

## 🔧 Troubleshooting
- Проверка статуса:
```bash
kubectl get pods,svc,pvc
kubectl describe resourcequota

```

[Сосисочная у дома](https://front-iisakov.2sem.students-projects.ru)
