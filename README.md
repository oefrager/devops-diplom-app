### Создание тестового приложения

  Создаем [Dockerfile](Dockerfile) для компиляции образа нашего приложения.

```
# Собираем образ на основе nginx
docker build -f Dockerfile -t nginx-app .

# Загрузка в публичный реестр
docker tag nginx-app:latest oefrager/nginx-app:1.0.1
docker push oefrager/nginx-app:1.0.1

# Провверяем работоспособност созданного образа:
docker pull oefrager/nginx-app:1.0.1
docker run -d --name nginx-app p 8080:80 nginx-app:latest
```
