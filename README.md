# K-ISP-21-Gorshihina
LR1

`sudo yum install wget` - эта команда устанавливает утилиту `wget`, которая используется для загрузки файлов по HTTP, HTTPS и FTP. 

`sudo` -Запуск команды с правами суперпользователя (администратора).

`yum` -Это пакетный менеджер для дистрибутивов Linux на базе RPM, таких как CentOS и Red Hat.

`install` -Подкоманда для установки пакета.

`wget` - Имя пакета, который необходимо установить.

`sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo` - Эта команда загружает файл репозитория Docker для CentOS и помещает его в каталог `yum.repos.d`.

- `wget` - Утилита для загрузки файлов.
- `-P /etc/yum.repos.d/`- Опция `-P` указывает `wget`, куда сохранить загруженный файл.
- `https://download.docker.com/linux/centos/docker-ce.repo`- URL-адрес файла, который нужно скачать.
  
