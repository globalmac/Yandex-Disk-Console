# Yandex-Disk-Console
Консольная утилита для создания бэкапов для Linux и Mac OS

## Установка

#### 1. Для начала требуется определиться как Вы будете использовать скрипт.

Есть 2 варианта:

**1) Загружать бэкапы в отдельную папку на Вашем Яндекс Диске (например: "Приложения/Backup"), изолюруя остальные папки от случайных манипуляций.**

**2) Получить доступ к записи во все папки Вашего Яндекс Диска. В этом случае приложение сможет загружать Ваши бэкапы в любую из папок, будьте с этим аккурантее!**

**Определились?!? - Погнали...**

#### 2. [Создаём новое приложение](https://oauth.yandex.ru/client/new) и получаем Token.

**Важно**: указать название приложения, выбрать права доступа - "Яндекс.Диск REST API" и отметить:

- **"Доступ к папке приложения на Диске"** - если Вы выбрали для себя 1 вариант с загрузкой файлов в отдельную папку (например: "Приложения/Backup").

- **"Запись в любом месте на Диске"** - если Вы выбрали для себя 2 вариант с загрузкой файлов в любую папку Яндекс Диска.

В пункте "Callback URL" - нажмите на "Подставить URL для разработки" и нажмите "Сохранить".


Вы увидите основную информацию о Вашем приложении и примерно такие строчки:

**ID: sdf767sd6f57sdf7sdf67sd6f7dsf**

Пароль: kortojh76sdfsd9gg32g4ygy23gjdfsfd9

Callback URL: {https://oauth.yandex.ru/verification_code}


#### 3. Получаем наш token.

** Скопируйте ссылку и вставьте Ваш **ID**:

    https://oauth.yandex.ru/authorize?response_type=token&display=popup&client_id=ID

Нажмите кнопку "Разрешить", чтобы приложение получило доступ к вашим данным на Яндекс Диске.

В центре экрана будет тот самый **token**: скопируйте его, откройте файл **yadisk.sh** и вставьте в параметре **token**.


## Использование

Загрузить файл:
```bash
./yadisk.sh -f /path/to/file/file_name
```

Загрузить файл и отправить email в случае ошибки
```bash
./yadisk.sh -f /path/to/file/file_name -m user@localhost -e
```

**После первой загрузки, если Вы выбрали для себя 1 вариант с загрузкой файлов в отдельную папку (например: "Приложения/Backup"), зайдите в свой Яндекс Диск и Вы увидите новую папку "Приложения", в ней Вы найдете папку вашего приложения и сможете проверить результат.**
