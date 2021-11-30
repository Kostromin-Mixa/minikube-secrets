# 14.1 Создание и использование секретов   
1. Создан секрет   
openssl genrsa -out cert.key 4096   
openssl req -x509 -new -key cert.key -days 3650 -out cert.crt \   
-subj '/C=RU/ST=Moscow/L=Moscow/CN=server.local'   
kubectl create secret tls domain-cert --cert=certs/cert.crt --key=certs/cert.key   

![secret](https://user-images.githubusercontent.com/78191008/143670650-7a58e85e-dfb5-4f80-953f-369946db9b2d.png)

![secret-view](https://user-images.githubusercontent.com/78191008/143670674-5df589a3-c954-4898-b9b4-cb5ab4d570a5.png)

2. Создан конфиг файл для деплоя [dep.yaml](https://github.com/Kostromin-Mixa/minikube-secrets/blob/main/dep.yaml)   

![dep](https://user-images.githubusercontent.com/78191008/143670725-31de4677-8ba5-43b9-add9-7a425eefaac4.png)

Подключение секрета в виде тома, под secret-test [mypod.yml](https://github.com/Kostromin-Mixa/minikube-secrets/blob/main/mypod.yml)  
![sec_po](https://user-images.githubusercontent.com/78191008/144036366-0e0d5a01-d507-419a-ba29-bb47c0250170.png)
![sec_mo_test](https://user-images.githubusercontent.com/78191008/144036428-f136cfc6-e3db-4aff-8f74-9c67418893c5.png)

Подключение секрета в виде переменных окружения, под secret-env-pod [value.yml](https://github.com/Kostromin-Mixa/minikube-secrets/blob/main/value.yml)  

![sec_po_test](https://user-images.githubusercontent.com/78191008/144036579-5f741a66-9067-422e-aaa8-820a11faabb1.png)



