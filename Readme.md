# Инструкция по работе с Git

## Что такое гит?
***Git*** - самая популярная реализация распределённой системы контроля версий(версионность поддерживается и на сервере, и у каждого клиента). Самой распространнённой реализацией ***Git*** является (GitHub)[https://github.com]

## Подготовка репозитория
Для создания репозитория используется команда *git init*. Для этого необходимо открыть в терминале папку с будущем репозиторием и написать *git init*

## Отображение текущего состояния репозитория
Для отображения текущего состояния репозитория используется команда *git status*. Для этого в терминале с папкой-репозиторием пишем *git status*.

## Создание коммитов

### Добавление файлов к коммиту
Для добавления файла к новому коммиту используется команда *git add*. Используется она следующим образом: в терминале с папкой-репозиторием пишем *git add <название файла>*.

### Создание коммита
Для создание новой фиксации(коммита) используется команда *git commit*. Для этого в терминале с папкой-репозиторием пишем *git commit -m "<сообщение к коммиту>*. Сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО!!!***

## Разница между текущим состоянием файла и последним закоммиченным файлом
Для того чтобы посмотереть разницу между текущим состоянием файла и последним закомиченным файлом используется команда *git diff*. Для этого в терминале с папкой-репозиторием пишем *git diff*.

## Журнал изменений
Для просмотра истории изменений используется команда *git log*. Для этого в терминале с папкой-репозиторием необходимо написать *git log*

## Перемещение между коммитами
Для перемещения на другую фиксацию(коммит) используется команда *git checkout*. Для этого необходимо, как показано в прошлом пункте, в журнале изменений найти необходимый коммит и его хеш(номер), после чего в терминале с папкой-репозиторием надо написать *git checkout <хеш коммита>*. После выполнения этой команды мы попадаем в состояние **detached head**, в котором никакие следующие коммиты сохраняться не будут. Для выхода из этого состояния необходимо написать *git checkout master*.

## Ветки в гит
### Создание веток в гит
Для создание новой ветки используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch <название ветки>*.
### Просмотр списка веток
Для просмотра списка веток используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch*. Выделенная зелёным со звёздочкой ветка - это ветка, в данный момент на которой мы находимся.

### Перемещение между ветками
Для перехода на другую ветку используется команда *git checkout*. Для этого в терминале с папкой-репозиторием необходимо написать *git checkout <название ветки>*. Такая ветка должна **существовать**.

## Слияние веток и разрешение конфликтов
После того как создали ветку с новым(и) коммитам(и), мы можем вновь перейти в ветку *master* с помощью команды *git checkout master*, и слить изменения с созданной ветки в ветку *master* с помощью команды *git merge <имя ветки>* в терминале с папкой-репозиторием. Однако иногда при слиянии веток могут происходить конфликты, состояние конфликта возникает тогда, когда в нескольких разных ветках была изменена одна и таже строка текста. После появления конфликта необходимо его решить: можно принять текущее изменение, или входящее изменение, или принять оба изменения. Но чаще удобнее решить конфликт вручную, для этого необходимо убрать **<<<<<<< HEAD(текущее изменение) **, **=======**, **>>>>>>> <имя ветки> (входящее изменение)**, сохранить файл, в терминале с папкой-репозиторием приписать комманду *git add <имя файла>*, далее создать коммит с помощью команды *git commit -m "сообщение к коммиту"*.

## Удаление веток
После слияния веток созданную ветку (черновик) можно удалить за ненадобностью. Для этого необходимо в терминале прописать *git branch -d <имя ветки>*.

## Работа с удаленными репозиториями

### Клонирование репозитория с GitHub 
Для того чтобы склонировать внешний репозиторий с GitHub в наш локальный репозиторий, необходимо в терминале с папкой-репозиторием написать команду *git clone <адрес репозитория, который копируем на свой ПК>*.

### Команда pull
Для того чтобы извлечь и загрузить содержимое из удаленного репозитория и немедленно обновить локальный репозиторий этим содержимым используется команда *git pull*. Для этого в терминале с папкой-репозиторием необходимо написать *git pull*.

### Команда push
Для того чтобы отправить изменения с локального репозитория на удаленный репозиторий, используется команда *git push*. Для этого в терминале с папкой-репозиторием необходимо написать *git push*.