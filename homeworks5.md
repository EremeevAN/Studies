# Домашнее задание к занятию 5 «Практическое применение Docker»
## Задача 1
```bash
Dockerfile.pyton:
FROM python:3.9-slim
WORKDIR /app
COPY . .
RUN pip install --no-cache-dir -r requirements.txt
CMD [ "python", "main.py" ]
```

## Задача 3
```bash
compose.yaml:
version: "3"
include:
 - proxy.yaml
services:
  web:
    build:
      dockerfile: Dockerfile.python
    networks:
      backend:
        ipv4_address: 172.20.0.5
    environment:
      - DB_NAME=${MYSQL_DATABASE}
      - DB_PASSWORD=${MYSQL_PASSWORD}
      - DB_USER=${MYSQL_USER}
      - DB_HOST=db
    ports:
      - "5000:5000"
    restart: always
  db:
    image: mysql:8
    networks:
      backend:
        ipv4_address: 172.20.0.10
    environment:
      - MYSQL_ROOT_PASSWORD=${MYSQL_ROOT_PASSWORD}
      - MYSQL_DATABASE=${MYSQL_DATABASE}
      - MYSQL_USER=${MYSQL_USER}
      - MYSQL_PASSWORD=${MYSQL_PASSWORD}
      - MYSQL_ROOT_HOST="%"
    restart: on-failure
networks:
  backend:
    driver: bridge
    ipam:
      config:
        - subnet: 172.20.0.0/24
```



команда curl -L http://127.0.0.1:8090
![image](https://github.com/EremeevAN/Imagesd5/blob/main/2.png)

sql-запросы
![image](https://github.com/EremeevAN/Imagesd5/blob/main/3.png)

## Задача 4
В Yandex Cloud создаем виртуальную машину, устанавливаем docker, docker compose и записываем скрипт
```bash
#!/bin/bash
apt update && \
apt install -y git
cd /opt
if [ ! -d "/opt/shvirtd-example-python" ]; then
  git clone https://github.com/EremeevAN/shvirtd-example-python.git && \
  cd shvirtd-example-python
else
  cd shvirtd-example-python
fi
docker compose up -d
docker ps -a
exit 0
```
Видим, что скрип выполняется
![image](https://github.com/EremeevAN/Imagesd5/blob/main/4.png)

Заходим на сайт проверки http подключений и запускаем проверку 
![image](https://github.com/EremeevAN/Imagesd5/blob/main/13.png)

Выполняем SQL запросы
![image](https://github.com/EremeevAN/Imagesd5/blob/main/5.png)

## Задача 6
Скачайте docker образ hashicorp/terraform:latest и скопируйте бинарный файл /bin/terraform на свою локальную машину, используя dive и docker save. Предоставьте скриншоты действий .
![image](https://github.com/EremeevAN/Imagesd5/blob/main/6.png)
![image](https://github.com/EremeevAN/Imagesd5/blob/main/7.png)
![image](https://github.com/EremeevAN/Imagesd5/blob/main/8.png)
![image](https://github.com/EremeevAN/Imagesd5/blob/main/9.png)
![image](https://github.com/EremeevAN/Imagesd5/blob/main/10.png)

## Задача 6.1
Добейтесь аналогичного результата, используя docker cp.
Предоставьте скриншоты действий .
![image](https://github.com/EremeevAN/Imagesd5/blob/main/11.png)
![image](https://github.com/EremeevAN/Imagesd5/blob/main/12.png)






![image](https://github.com/EremeevAN/Studies/blob/main/Screenshot_4.png)