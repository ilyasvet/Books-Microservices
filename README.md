# Books-Microservices

Из папки app вводим sudo docker-compose up

Переходим в браузере на localhost:5000 и наблюдаем подобную картину

![image](https://github.com/ilyasvet/Books-Microservices/assets/49456780/67a8d79e-e1f7-48a7-afa7-3f3a600f25da)


# Для готовых контейнеров

`sudo docker pull ilyalight113/books-microservices:my

`sudo docker pull ilyalight113/books-microservices:rec

`sudo docker network create microservices

Далее в 2х терминалах запустить эти команды:
````
sudo docker run -p 127.0.0.1:5000:5000/tcp --network microservices \
             -e RECOMMENDATIONS_HOST=recommendations ilyalight113/books-microservices:my

sudo docker run -p 127.0.0.1:50051:50051/tcp --network microservices \
             --name recommendations ilyalight113/books-microservices:rec
````
