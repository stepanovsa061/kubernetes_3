# kubernetes_3

# Задание 1. Создать Deployment и обеспечить доступ к репликам приложения из другого Pod
1) Создать Deployment приложения, состоящего из двух контейнеров — nginx и multitool. Решить возникшую ошибку.
2) После запуска увеличить количество реплик работающего приложения до 2.
3) Продемонстрировать количество подов до и после масштабирования.
4) Создать Service, который обеспечит доступ до реплик приложений из п.1.
5) Создать отдельный Pod с приложением multitool и убедиться с помощью curl, что из пода есть доступ до приложений из п.1.

apply -f deployment.yaml ( ввел env: - name: HTTP_PORT value: "7080" )
          
![1 1](https://github.com/user-attachments/assets/e7fbf7a6-a2fe-4347-bd75-7fa6694f1dfe)

![1 2](https://github.com/user-attachments/assets/aa5ab5aa-cc9c-4111-8828-0bd35f3ed50e)

Увеличил количество реплик до 2х

![1 3 2replicas](https://github.com/user-attachments/assets/748d5462-79d7-4f66-bf21-287381312afc)

Создал deployment-svc.yaml для service, который обеспечит доступ до реплик приложений

![1 4 services](https://github.com/user-attachments/assets/4e8f3dab-113c-4796-b1b4-62f3d1fb8bba)

apply -f multitool-app.yaml

![1 5 multitool-app](https://github.com/user-attachments/assets/e77ad296-237f-48f7-95e6-90bd56413273)

Командой curl проверил состояние пода 

![1 6 curl](https://github.com/user-attachments/assets/b2c4586c-75ad-412e-b9e0-219575c58fcc)

![1 7 curl 2](https://github.com/user-attachments/assets/eb849a78-454d-486a-9e34-cde30f60fb72)

# Задание 2. Создать Deployment и обеспечить старт основного контейнера при выполнении условий
1) Создать Deployment приложения nginx и обеспечить старт контейнера только после того, как будет запущен сервис этого приложения.
2) Убедиться, что nginx не стартует. В качестве Init-контейнера взять busybox.
3) Создать и запустить Service. Убедиться, что Init запустился.
4) Продемонстрировать состояние пода до и после запуска сервиса.

Создадим deployment-init.yaml

![2 1](https://github.com/user-attachments/assets/1eb416d1-f944-4e52-ae8b-0aecd6a3b907)

Сотояние под и создал сервис

![2 2](https://github.com/user-attachments/assets/153ac55c-c18b-4171-96d5-d5521d2a4fcf)

Поды в старте, сервис активен

![2 3 services](https://github.com/user-attachments/assets/88aea733-f7d9-48ca-861e-02e2b3e834af)
