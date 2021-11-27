# 14.1 Создание и использование секретов   
1. Создан секрет   
openssl genrsa -out cert.key 4096   
openssl req -x509 -new -key cert.key -days 3650 -out cert.crt \   
-subj '/C=RU/ST=Moscow/L=Moscow/CN=server.local'   
kubectl create secret tls domain-cert --cert=certs/cert.crt --key=certs/cert.key   

![secret](https://user-images.githubusercontent.com/78191008/143670650-7a58e85e-dfb5-4f80-953f-369946db9b2d.png)

![secret-view](https://user-images.githubusercontent.com/78191008/143670674-5df589a3-c954-4898-b9b4-cb5ab4d570a5.png)

2. Создан конфиг файл для деплоя 

![dep](https://user-images.githubusercontent.com/78191008/143670725-31de4677-8ba5-43b9-add9-7a425eefaac4.png)
