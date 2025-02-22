# K-ISP-21-Gorshihina
LR1

1. `sudo yum install wget` - эта команда устанавливает утилиту `wget`, которая используется для загрузки файлов по HTTP, HTTPS и FTP. 
- `sudo` -Запуск команды с правами суперпользователя (администратора).
- `yum` -Это пакетный менеджер для дистрибутивов Linux на базе RPM, таких как CentOS и Red Hat.
- `install` -Подкоманда для установки пакета.
- `wget` - Имя пакета, который необходимо установить.

2. `sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo` - Эта команда загружает файл репозитория Docker для CentOS и помещает его в каталог `yum.repos.d`.

- `wget` - Утилита для загрузки файлов.
- `-P /etc/yum.repos.d/`- Опция `-P` указывает `wget`, куда сохранить загруженный файл.
- `https://download.docker.com/linux/centos/docker-ce.repo`- URL-адрес файла, который нужно скачать.
  
3. `sudo yum install docker-ce docker-ce-cli containerd.io` - Эта команда устанавливает Docker и его компоненты.
- `docker-ce` -  Это версия Docker Community Edition.
- `docker-ce-cli` - Командная строка для взаимодействия с Docker.
- `containerd.io` - Служба, отвечающая за управление контейнерами и их жизненным циклом.
  
4. `sudo systemctl enable docker --now` - Эта команда включает сервис Docker и запускает его немедленно.  
- `systemctl` - Утилита для управления системными службами.
- `enable` - Включает автозапуск сервиса при загрузке системы.
- `docker` -  Имя сервиса, который необходимо включить.
- `--now` -  Указывает, чтобы сервис был запущен немедленно.

5. `sudo yum install curl` - Эта команда устанавливает утилиту `curl`, которая используется для работы с URL-адресами, позволяет загружать и отправлять данные.
- `curl`-  Имя пакета, который необходимо установить.

6. `COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)`- Эта команда получает последнюю доступную версию Docker Compose из GitHub.
- `curl -s`- Делает запрос к API GitHub и включает опцию `-s` для подавления вывода прогресса.
- `grep 'tag_name'`- Ищет строку, содержащую `tag_name`, что указывает на версию.
- `cut -d\" -f4`- Разделяет строку по двойным кавычкам и выводит четвертое поле, которое является номером версии.
- `COMVER=`- Присваивает результат переменной `COMVER`. \

7. `sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose`- Эта команда загружает последнюю версию Docker Compose и устанавливает ее в систему.
- `curl -L`- Загружает по URL и следует любым перенаправлениям.
- `"$COMVER"`- Использует переменную, содержащую номер версии.
- `$(uname -s)` и `$(uname -m)`-  Определяет операционную систему и архитектуру (например, Linux и x86_64).
- `-o /usr/bin/docker-compose`- Указывает, куда сохранить загруженный файл.

8. `sudo chmod +x /usr/bin/docker-compose`- Эта команда добавляет разрешение на выполнение загруженного файла Docker Compose. 
- `chmod +x`-  Утилита для изменения разрешений.
- `/usr/bin/docker-compose`- Путь к файлу, для которого добавляются разрешения.

9. `docker-compose --version`- Эта команда проверяет установленную версию Docker Compose.
- `docker-compose`- Утилита для работы с Docker Compose.
- `--version`- Опция, которая выводит информацию о версии.

10. `git clone https://github.com/skl256/grafana_stack_for_docker.git`- Эта команда создает локальную копию репозитория Git.
- `git clone`- Команда для клонирования репозитория.
- `https://github.com/skl256/grafana_stack_for_docker.git`- URL репозитория, который будет клонирован.

11. `cd grafana_stack_for_docker**` - Команда `cd` (change directory) используется для перехода в директорию с именем `grafana_stack_for_docker`. Это означает, что текущая рабочая директория будет изменена на `grafana_stack_for_docker`, что позволит вам выполнять последующие команды внутри этой папки.


