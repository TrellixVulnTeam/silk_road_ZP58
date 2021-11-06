# Решение для распознавания и разметки пешеходных дорог
## Веб-интерфейс
### Системные требования:
1. Docker
2. NVIDIA CUDA 11.1
3. \>= 1 GPU с объемом видеопамяти не менее 4 Гб
### Инструкция по запуску:
1. Склонируйте или скачайте текущий репозиторий.

2. Для сборки docker-контейнера перейдите в корневую папку проекта и выполните:

`docker build . -t silk_road`

3. Для запуска веб интерфейса выполните команду:

`docker run --gpus all -d -p 8011:8011 silk_road`

Если при запуске появляется ошибка, значит, вероятнее всего, Ваша версия Docker не поддерживает запуск контейнера с GPU. Попробуйте запустить со следующей командой:

`docker run -d -p 8011:8011 silk_road`

### Инструкция по остановке:
1. Для остановки веб-интерфейса выполните команду:

`docker stop [CONTAINER ID]`

### Инструкция по работе
0. Запустите веб-интерфейс по инструкции. Подождите некоторое время после выполнения пункта 3.
1. Перейдите по адресу http://localhost:8011/.
2. В соответствующие поля загрузите TIF-изображение размера 5000x5000 и tfw-файл (опционально).
3. Нажмите обработать. Подождите некоторое время.
4. Скачайте необходимые файлы на странице с результатами.

### Возможности:
* Загрузка нескольких файлов одновременно;
* Просмотр распознанных дорожек с наложением на карту;
* Скачивание выходных файлов:
* * Объединенный Shapefile для всех загруженных изображений;
* * Shapefile для каждого изображения;
* * Визуализация дорожек на каждом изображении;
* * Визуализация дорожек после постпроцессинга на каждом изображении;
* * Маска вероятностей дорожек для каждого изображения.
* Развертывание системы на машине без GPU. В таком случае вычисления производятся на CPU.

### Troubleshooting
Если по каким-то причинам веб-интерфейс не работает после выполнения пункта 3 из инструкции по запуску, то возникшие ошибки можно изучить с помощью команды:

`docker logs [CONTAINER ID]`
