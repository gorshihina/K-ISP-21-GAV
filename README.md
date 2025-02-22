# K-ISP-21-Gorshihina
LR1

1. `sudo yum install wget` - эта команда устанавливает утилиту `wget`, которая используется для загрузки файлов по HTTP, HTTPS и FTP. 
- `sudo` -Запуск команды с правами суперпользователя (администратора).
- `yum` -Это пакетный менеджер для дистрибутивов Linux на базе RPM, таких как CentOS и Red Hat.
- `install` -Подкоманда для установки пакета.
- `wget` - Имя пакета, который необходимо установить.

![image](https://github.com/user-attachments/assets/06a75246-c870-4c77-b3ec-20e37544de64)

2. `sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo` - Эта команда загружает файл репозитория Docker для CentOS и помещает его в каталог `yum.repos.d`.
- `wget` - Утилита для загрузки файлов.
- `-P /etc/yum.repos.d/`- Опция `-P` указывает `wget`, куда сохранить загруженный файл.
- `https://download.docker.com/linux/centos/docker-ce.repo`- URL-адрес файла, который нужно скачать.

![image](https://github.com/user-attachments/assets/6b5535df-6503-4365-b649-4cdcba2a82f2)

3. `sudo yum install docker-ce docker-ce-cli containerd.io` - Эта команда устанавливает Docker и его компоненты.
- `docker-ce` -  Это версия Docker Community Edition.
- `docker-ce-cli` - Командная строка для взаимодействия с Docker.
- `containerd.io` - Служба, отвечающая за управление контейнерами и их жизненным циклом.

![image](https://github.com/user-attachments/assets/ce5f6fb7-89a7-4ab6-aeaa-e0b7a2f37d17)
  
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
- `COMVER=`- Присваивает результат переменной `COMVER`.
  
![photo_5318794157298412301_y](https://github.com/user-attachments/assets/872c3776-3381-479f-a243-09a8c047760d)

7. `sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose`- Эта команда загружает последнюю версию Docker Compose и устанавливает ее в систему.
- `curl -L`- Загружает по URL и следует любым перенаправлениям.
- `"$COMVER"`- Использует переменную, содержащую номер версии.
- `$(uname -s)` и `$(uname -m)`-  Определяет операционную систему и архитектуру (например, Linux и x86_64).
- `-o /usr/bin/docker-compose`- Указывает, куда сохранить загруженный файл.

![photo_5318794157298412313_y](https://github.com/user-attachments/assets/070d41d5-2fc4-4567-8309-c36dd807a229)

8. `sudo chmod +x /usr/bin/docker-compose`- Эта команда добавляет разрешение на выполнение загруженного файла Docker Compose. 
- `chmod +x`-  Утилита для изменения разрешений.
- `/usr/bin/docker-compose`- Путь к файлу, для которого добавляются разрешения.

9. `docker-compose --version`- Эта команда проверяет установленную версию Docker Compose.
- `docker-compose`- Утилита для работы с Docker Compose.
- `--version`- Опция, которая выводит информацию о версии.
  
![photo_5318794157298412316_x (1)](https://github.com/user-attachments/assets/78bb2533-e097-4345-a332-139f198df262)

10. `git clone https://github.com/skl256/grafana_stack_for_docker.git`- Эта команда создает локальную копию репозитория Git.
- `git clone`- Команда для клонирования репозитория.
- `https://github.com/skl256/grafana_stack_for_docker.git`- URL репозитория, который будет клонирован.
  
![photo_5318794157298412331_x](https://github.com/user-attachments/assets/9eac7661-0a58-433a-9ea6-84a44be9a847)

11. `cd grafana_stack_for_docker*` - Команда `cd` (change directory) используется для перехода в директорию с именем `grafana_stack_for_docker`. Это означает, что текущая рабочая директория будет изменена на `grafana_stack_for_docker`, что позволит вам выполнять последующие команды внутри этой папки.

12. `sudo mkdir -p /mnt/common_volume/swarm/grafana/config` - Команда `mkdir` (make directory) создает новую директорию.
 Опция `-p` позволяет создать промежуточные директории, если они не существуют. В данном случае создается директория `/mnt/common_volume/swarm/grafana/config`.
 Использование `sudo` означает, что команда будет выполнена с правами суперпользователя, что нужно для создания директорий в защищенных местах файловой системы.

13. `sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}`- Эта команда также создает несколько директорий одновременно благодаря фигурным скобкам. Она создаст три директории: `grafana-config`, `grafana-data`, и `prometheus-data` по пути `/mnt/common_volume/grafana`. Как и в предыдущем случае, используется `sudo` для выполнения с правами суперпользователя.

14. `sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}`- Команда `chown` изменяет владельца и группу для указанных директорий. Опция `-R` (рекурсивно) применяет изменения ко всем подкаталогам и файлам в указанных директориях.
`$(id -u)` вернет идентификатор текущего пользователя, а `$(id -g)` — идентификатор его группы. Это позволяет сделать текущего пользователя владельцем директорий `/mnt/common_volume/swarm/grafana/config` и `/mnt/common_volume/grafana`.

15. `touch /mnt/common_volume/grafana/grafana-config/grafana.ini` - Команда `touch` создает пустой файл или обновляет временную метку существующего файла.
- В данном случае будет создан пустой файл `grafana.ini` в директории `/mnt/common_volume/grafana/grafana-config`. Этот файл, вероятно, будет использоваться для конфигурации Grafana.

16. `cp config/* /mnt/common_volume/swarm/grafana/config/ `- Команда `cp` (copy) копирует файлы.
- Здесь `config/` обозначает, что все файлы из локальной директории `config` будут скопированы в директорию `/mnt/common_volume/swarm/grafana/config/`.
- Конечный символ `*` означает все файлы (и, возможно, каталоги) в указанной директории.

17. `mv grafana.yaml docker-compose.yaml`- Команда `mv` (move) переименовывает файл или перемещает его в другую директорию. В данном случае файл `grafana.yaml` переименовывается в `docker-compose.yaml`. Этот файл, вероятно, используется для настройки Docker Compose.
    
![photo_5318794157298412346_y (1)](https://github.com/user-attachments/assets/3e1bc9ab-8364-4fc2-8ecd-09d5a1bdf408)

18. `sudo docker compose up -d`- Эта команда запускает Docker Compose с конфигурацией, указанной в `docker-compose.yaml`.
- Опция `-d` (detached mode) означает, что контейнеры будут запущены в фоновом режиме.
- Использование `sudo` обеспечивает запуск с правами суперпользователя, потому что Docker обычно требуется такие права.
  
![photo_5318794157298412346_y](https://github.com/user-attachments/assets/24806b99-2ef8-41cd-9b24-37918c29f264)

# # Grafana

* Переходим на сайт `localhost:3000`
    * User & Password GRAFANA: `admin`
    * Код графаны: `3000`
    * Код прометеуса: `http://prometheus:9090`
* В меню выбираем вкладку Dashboards и создаем Dashboard
    * Ждем кнопку +Add visualization, а после "Configure a new data source"
    * Выбираем Prometheus
    * Connection
    * `http://prometheus:9090`
* Authentication
    * Basic authentication
        * User: `admin`
        * Password: `admin`
        * Нажимаем на Save & test и должно показывать зелёную галочку
* В меню выбираем вкладку Dashboards и создаем Dashboard
    * Ждем кнопку "Import dashboard"
    * Find and import dashboards for common applications at grafana.com/dashboards: 1860 //ждем кнопку Load
    * Select Prometheus ждем кнопку "Import"

# #VictoriaMetrics



