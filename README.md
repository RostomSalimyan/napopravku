
<h1 align="center">
  cloud-storage-api
  <br>
</h1>

<h4 align="center"> Прототип сервиса облачного хранилища для файлов </h4>


<p align="center">
  <a href="#описание">Описание</a> •
  <a href="#как-скачать">Как скачать</a>
</p>

## Описание



* Сервис предоставляет хранение файлов и возможность делится ими с другими, указывая срок хранения по истечению которого
  файл удалится автоматически
* Максимальный объём одного загружаемого файла 20мб, 100мб всего на диске пользователя, файл не может иметь расширение .php
* Пользователь может удалять, переименовывать, и просматривать свои файлы и создавать папки
* Пользователь может получить размер всех файлов внутри директории и размер всех файлов на диске

## Как скачать

Скопируем env.example в корень и переименуем в .env, указываем тип бд и если нужно порт, в APP_URL вписываем хост сайта.
И запускаем следующие команды:
```bash
# Качаем зависимости
$ composer install

# Поднимаем контейнеры
$ ./vendor/bin/sail up

# Установка ключа приложения
$php ./vendor/bin/sail artisan key:generate

# Запускаем миграции
$ ./vendor/bin/sail artisan migrate

# Линкуем папки
$ ./vendor/bin/sail artisan storage:link

# Набираем команду
$ crontab -e
# и вставляем это
# * * * * * cd /path-to-your-project && php artisan schedule:run >> /dev/null 2>&1 
```
