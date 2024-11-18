# Домашнее задание к занятию «Хранение в K8s. Часть 1»

### Цель задания

В тестовой среде Kubernetes нужно обеспечить обмен файлами между контейнерам пода и доступ к логам ноды.

------

### Чеклист готовности к домашнему заданию

1. Установленное K8s-решение (например, MicroK8S).
2. Установленный локальный kubectl.
3. Редактор YAML-файлов с подключенным GitHub-репозиторием.

------

### Дополнительные материалы для выполнения задания

1. [Инструкция по установке MicroK8S](https://microk8s.io/docs/getting-started).
2. [Описание Volumes](https://kubernetes.io/docs/concepts/storage/volumes/).
3. [Описание Multitool](https://github.com/wbitt/Network-MultiTool).

------

### Задание 1 

**Что нужно сделать**

Создать Deployment приложения, состоящего из двух контейнеров и обменивающихся данными.

1. Создать Deployment приложения, состоящего из контейнеров busybox и multitool.

<img width="339" alt="deployment-emptyDir" src="https://github.com/user-attachments/assets/4b18fb99-3924-4a4f-b90a-52349b33fd53">

2. Сделать так, чтобы busybox писал каждые пять секунд в некий файл в общей директории.

<img width="526" alt="busybox" src="https://github.com/user-attachments/assets/bf48ceb5-b5e2-489e-a4b8-57ee7b10b982">

<img width="428" alt="pod" src="https://github.com/user-attachments/assets/cc150c30-42f3-4304-8649-5df85b936de4">

<img width="638" alt="write hello" src="https://github.com/user-attachments/assets/07aab533-935d-4cd4-8a77-705dced4ba2a">

3. Обеспечить возможность чтения файла контейнером multitool.

<img width="246" alt="read multitool" src="https://github.com/user-attachments/assets/7f0924fd-0411-4595-b66e-bfc9c7aa13e4">

4. Продемонстрировать, что multitool может читать файл, который периодоически обновляется.

<img width="619" alt="multitool status log" src="https://github.com/user-attachments/assets/941b4a94-f027-4b59-a5e4-b709dc7308f5">

5. Предоставить манифесты Deployment в решении, а также скриншоты или вывод команды из п. 4.

[deployment-emptyDir.yaml](https://github.com/sash3939/Kubernetes6-Storage/blob/main/deployment-emptyDir.yaml)

------

### Задание 2

**Что нужно сделать**

Создать DaemonSet приложения, которое может прочитать логи ноды.

1. Создать DaemonSet приложения, состоящего из multitool.

<img width="502" alt="daemonset status" src="https://github.com/user-attachments/assets/edc3ab81-6535-4959-b22a-41cda251bfe7">

2. Обеспечить возможность чтения файла `/var/log/syslog` кластера MicroK8S.

<img width="191" alt="read multiotool daemonset" src="https://github.com/user-attachments/assets/89f21882-50de-494c-b349-55aa4888834e">

3. Продемонстрировать возможность чтения файла изнутри пода.

<img width="594" alt="status exec deployment hostPath" src="https://github.com/user-attachments/assets/1efc3890-c4f0-46ab-be36-59db20913595">

<img width="712" alt="read logs" src="https://github.com/user-attachments/assets/f45e016b-e00f-4a76-857d-877723230741">

4. Предоставить манифесты Deployment, а также скриншоты или вывод команды из п. 2.

[deployment-hostPath.yaml](https://github.com/sash3939/Kubernetes6-Storage/blob/main/deployment-hostPath.yaml)

------

### Правила приёма работы

1. Домашняя работа оформляется в своём Git-репозитории в файле README.md. Выполненное задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода необходимых команд `kubectl`, а также скриншоты результатов.
3. Репозиторий должен содержать тексты манифестов или ссылки на них в файле README.md.

------
