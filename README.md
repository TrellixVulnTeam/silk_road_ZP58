# Решение для распознавания и разметки пешеходных дорог
## Веб-интерфейс
### Системные требования:
1. Docker
2. NVIDIA CUDA 11.1
3. \>= 1 GPU
### Инструкция по запуску:
1. Склонируйте или скачайте текущий репозиторий.

2. Для сборки docker-контейнера перейдите в корневую папку проекта и выполните:

`docker build . -t silk_road`

3. Для запуска веб интерфейса выполните команду:

`docker run -d -p 8011:8011 silk_road`

### Инструкция по работе
0. Запустите веб-интерфейс по инструкции. Подождите некоторое время после выполнения пункта 3.
1. Перейдите по адресу http://localhost:8011/.
2. В соответствующие поля загрузите TIF-изображение размера 5000x5000 и tfw-файл (опционально).
3. Нажмите обработать. Подождите некоторое время.
4. Скачайте необходимые файлы на странице с результатами.
