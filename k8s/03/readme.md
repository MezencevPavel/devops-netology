# Домашнее задание к занятию «Запуск приложений в K8S»

### Цель задания

В тестовой среде для работы с Kubernetes, установленной в предыдущем ДЗ, необходимо развернуть Deployment с приложением, состоящим из нескольких контейнеров, и масштабировать его.

------

### Чеклист готовности к домашнему заданию

1. Установленное k8s-решение (например, MicroK8S).
2. Установленный локальный kubectl.
3. Редактор YAML-файлов с подключённым git-репозиторием.

------

### Инструменты и дополнительные материалы, которые пригодятся для выполнения задания

1. [Описание](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) Deployment и примеры манифестов.
2. [Описание](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/) Init-контейнеров.
3. [Описание](https://github.com/wbitt/Network-MultiTool) Multitool.

------

### Задание 1. Создать Deployment и обеспечить доступ к репликам приложения из другого Pod

1. Создать Deployment приложения, состоящего из двух контейнеров — nginx и multitool. Решить возникшую ошибку.
2. После запуска увеличить количество реплик работающего приложения до 2.
3. Продемонстрировать количество подов до и после масштабирования.
4. Создать Service, который обеспечит доступ до реплик приложений из п.1.
5. Создать отдельный Pod с приложением multitool и убедиться с помощью `curl`, что из пода есть доступ до приложений из п.1.

------

### Задание 2. Создать Deployment и обеспечить старт основного контейнера при выполнении условий

1. Создать Deployment приложения nginx и обеспечить старт контейнера только после того, как будет запущен сервис этого приложения.
2. Убедиться, что nginx не стартует. В качестве Init-контейнера взять busybox.
3. Создать и запустить Service. Убедиться, что Init запустился.
4. Продемонстрировать состояние пода до и после запуска сервиса.

------

### Решение 1. Создать Deployment и обеспечить доступ к репликам приложения из другого Pod

1. Создаю новый namespace **netology**
2. запускаю  [deployment.yml](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/03/deployment.yml)  
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/03/png/01.png)  
3.  После увелеченил количество реплик до двух.  
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/03/png/02.png)  
4.  Далее запускаю [service.yml](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/03/service.yml)  
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/03/png/03.png)  
5.  отдельный pod [multitool.yml](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/03/multitool.yml)
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/03/png/04.png)  


------

### Решение 2. Создать Deployment и обеспечить старт основного контейнера при выполнении условий

1.  файл [deployment2.yml](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/03/deployment2.yml) для старта контейнера
2.  файл [nginx-init-svc.yml](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/03/nginx-init-svc.yml) для создания сервиса
3.  ![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/03/png/05.png) видим что pod nginx-init-deploy-786df4c9fc-77psq запущен  
 
