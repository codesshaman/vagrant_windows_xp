# Виртуальная машина Vagrant c windows xp

Необходимо установить:
- [vagrant (windows)](https://cloud.mail.ru/public/Vvjh/TyWnCn8h9 "vagrant") 
или
- [vagrant (linux)](https://github.com/hashicorp/vagrant-installers/releases/tag/v2.3.4.dev%2Bmain "vagrant") 
и [virtualbox](https://www.virtualbox.org/ "virtualbox").

При необходимости для подключения к виртуальной машине из windows можно использовать любой ssh-клиент, например, [Bitvise SSH Client](https://www.bitvise.com/ssh-client-download "Bitvise").

### Step 1

Клонировать данный репозиторий:

``git clone https://github.com/codesshaman/vagrant_windows_xp.git``

### Step 2

Скачать бокс bento/debian-11.5 для virtualbox с [vagrantup](https://app.vagrantup.com/voidead/boxes/win-xp-sp1 "vagrantup").

a2a5f4df-eba7-4c0c-88e4-7ff6d02d5ada

### Step 3

Переименовать бокс в "debian" и переместить в корень склонированного репозитория vagrant.

``cp ~/Downloads/a2a5f4df-eba7-4c0c-88e4-7ff6d02d5ada path_to/vagrant_python_debian/debian``

``cd vagrant_python_debian``

### Step 4

Склонировать репозиторий вашего python-проекта в папку project.

### Step 5

Инициализация конфигурации (из папки вагранта):

``vagrant box add StefanScherer/windows_10 windows``

### Step 6

Установка виртуальной машины (при включённом virtualbox!):

``vagrant up --provider=virtualbox``

Установка займёт достаточно много времени.

### Step 7

Открываем папку laravel в VsCode

### Step 8

Открываем доступ к виртуальной машине через ssh-клиент:

```
IP: 192.168.58.100
Port: 2222
User: vagrant
Pass: vagrant
```

### Step 9

Для запуска конфигурации используем следующие команды внутри VM (ssh-клиент):

```
cd docker/laravel
docker exec -it lar8cpro composer update
docker exec -it lar8cpro php artisan passport:install
docker exec -it lar8cpro php artisan token:generate
docker exec -it lar8cpro php artisan optimize
```

### Step 10

Открыть конфигурацию в браузере:

``http://192.168.58.100/``

Этот же адрес использовать для запросов postman.

### Управление виртуальными машинами

> Все команды выполняются из папки vagrant

Запуск: ``vagrant up``

Остановка: ``vagrant halt``

Перезагрузка: ``vagrant reload``

Гибернация: ``vagrant suspend``

Удаление VM: ``vagrant destroy``

***

# Vagrant virual machine with docker

Your need install [vagrant](https://cloud.mail.ru/public/Vvjh/TyWnCn8h9 "vagrant") and [virtualbox](https://www.virtualbox.org/ "virtualbox") for up this configuration.

For access to virtual machine you can use any ssh-client, for example [Bitvise SSH Client](https://www.bitvise.com/ssh-client-download "Bitvise").

### Step 1

Clonr this repository: ``https://github.com/GosZakaz/vagrant.git``

### Step 2

Download box bento/debian-11.5 for virtualbox from [vagrantup](https://app.vagrantup.com/bento/boxes/debian-11.5 "vagrantup").

### Step 3

Rename box to "debian" and copy/move to vagrant folder.

> Use ``PowerShell`` or ``cmd`` for the next steps!

### Step 4

Clone target branch of [project backend](https://github.com/GosZakaz/gosz-market-back "back") to the ``docker`` directory named ``laravel``:

```
cd docker
git clone https://github.com/GosZakaz/gosz-market-back.git -b Developer laravel
cd ..
```

### Step 5

Inicialize configuration (from vagrant folder):

``vagrant box add bento/debian-11 debian``

### Step 6

Install VM configuration (with work virtualbox app!):

``vagrant up --provider=virtualbox``

The installation will take quite a long time.

### Step 7

Open laravel folder in VsCode

### Step 8

Connect to vm from ssh-client with next data:

```
IP: 192.168.58.100
Port: 2222
User: vagrant
Pass: vagrant
```

### Step 9

For starting configuration use next commands in ssh-client:

```
cd docker/laravel
docker exec -it lar8cpro composer update
docker exec -it lar8cpro php artisan passport:install
docker exec -it lar8cpro php artisan token:generate
docker exec -it lar8cpro php artisan optimize
```

### Step 10

Open configuration in your browser:

``http://192.168.58.100/``

Use this address for postman querys.

### Manage VM

> All commands used from vagrant folder

Start: ``vagrant up``

Shutdown: ``vagrant halt``

Reboot: ``vagrant reload``

Hybernation: ``vagrant suspend``

Delete VM: ``vagrant destroy``
