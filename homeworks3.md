# Домашнее задание к занятию 4 «Оркестрация группой Docker контейнеров на примере Docker Compose»
## Задача 1
[Ссылка на образ](https://hub.docker.com/repository/docker/aeremeev1604/custom-nginx/general)
## Задача 2
![image]https://github.com/EremeevAN/Studies/blob/main/Screenshot_4.png
![image]https://github.com/EremeevAN/Studies/blob/main/Screenshot_3.png
## Задача 3
 3. Ctrl-C  завершает работу контейнера.В контейнере используется bash и Ctrl-C выполняет прерывание процесса. Без основного процесса, контейнер останавливаетвся
 10. Проблема в том, что в настройках контейнера указано слушать с контейнера 80 порт и перенаправлять на 8080, а мы в настройках поменяли, что nginx использует 81 порт
 12. Удаление запущенного контейнера выполняется командой docker rm -f "container_id"
## Задача 4
![image]https://github.com/EremeevAN/Studies/blob/main/Screenshot_5.png
## Задача 5
Если существуют оба файла, Compose предпочитает канонический compose.yaml 
![image]https://github.com/EremeevAN/Studies/blob/main/Screenshot_7.png
![image]https://github.com/EremeevAN/Studies/blob/main/Screenshot_9.png
![image]https://github.com/EremeevAN/Studies/blob/main/Screenshot_10.png
![image]https://github.com/EremeevAN/Studies/blob/main/Screenshot_6.png