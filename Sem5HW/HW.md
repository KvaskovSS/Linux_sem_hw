# Домашняя работа по семинару №5
## Все задания выполнил в общем виде

## 1. Подключить дополнительный репозиторий на выбор: Docker, Nginx, Oracle MySQL. Установить любой пакет из этого репозитория.
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update
sudo apt install docker-ce
```

## 2. Установить и удалить deb-пакет с помощью dpkg.
```
sudo dpkg -i package.deb

sudo dpkg -r package_name
```
## 3. Установить и удалить snap-пакет.
```
sudo snap install package_name

sudo snap remove package_name
```
## 4. Добавить задачу для выполнения каждые 3 минуты (создание директории, запись в файл).
```
crontab -e

*/3 * * * * mkdir /path/to/directory && echo "Запись в файл" >> /path/to/file
```

## 5. Подключить PPA-репозиторий на выбор. Установить из него пакет. Удалить PPA из системы.
```
sudo add-apt-repository ppa:repository_name

sudo apt update

sudo apt install package_name

sudo add-apt-repository --remove ppa:repository_name
```

## 6. Создать задачу резервного копирования (tar) домашнего каталога пользователя. Реализовать с использованием пользовательских crontab-файлов.
```
crontab -e

0 1 * * * tar -czvf /path/to/backup.tar.gz /home/user
```