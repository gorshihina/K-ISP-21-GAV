# K-ISP-21-Gorshihina
LR1

1. `sudo yum install wget` - эта команда устанавливает утилиту `wget`, которая используется для загрузки файлов по HTTP, HTTPS и FTP. 

`sudo` -Запуск команды с правами суперпользователя (администратора).

`yum` -Это пакетный менеджер для дистрибутивов Linux на базе RPM, таких как CentOS и Red Hat.

`install` -Подкоманда для установки пакета.

`wget` - Имя пакета, который необходимо установить.

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
- `curl`: Имя пакета, который необходимо установить.

6. `COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)`- Эта команда получает последнюю доступную версию Docker Compose из GitHub.
- `curl -s`: Делает запрос к API GitHub и включает опцию `-s` для подавления вывода прогресса.
- `grep 'tag_name'`: Ищет строку, содержащую `tag_name`, что указывает на версию.
- `cut -d\" -f4`: Разделяет строку по двойным кавычкам и выводит четвертое поле, которое является номером версии.
- `COMVER=`: Присваивает результат переменной `COMVER`. 


