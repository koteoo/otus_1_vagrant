(OTUS)
# Домашнее задание: 1

Описание и цель ДЗ:
1. Подготовка ПК для выполнения домашних работ
2. Настроить среду для выполнения домашних работ

### Используемые инструменты:

1. Vagrant
2. Packer
3. Github
4. VirtualBox

### Этап выполнения:

Установка окружения:

1. Установить Vagrant, и зарегистрироваться на сайте.
2. Установить Packer.
3. Установить VirtualBox.

Настройка и конфигурация:

1. Сборка Packer - BOX.
   Создав дирректорию Vagrant, создать в ней дирректорию packer и в ней http и scripts.
   Создать файлы centos.json (Vagrant), ks.cfg (http), stage1 и stage2 (Scripts).
   Отредактировать все файлы с необходимыми конфигурациями чтобы собрать BOX.
   
   Запустить сборку: ` packer build centos.json `
     
3. Загрузка собраного BOX в Vagrant cloud.
   Собранный BOX с помощью эмулятора терминала загрузить в Vagrant cloud, предварительно сгенерировав токен на сайте.
   
   Команда для входа:

   ` vagrant cloud auth login -t <your_token>`

   Команда для загрузки: 
   
   ` vagrant cloud publish --release <user_account>/centos8-kernel5 1.0 virtualbox centos-8-kernel-5-x86_64-Minimal.box `
   
5. Скачать данный BOX для проверки и запуска.
   Также с помощью консоли инициализировать свой собранный BOX (Название в Vagrant cloud) в своем каталоге, с помощью команды: `vagrant init <your_box>` .

   После чего появится Vagrantfile.

   Выполняем команду: ` vagrant up `

7. После успешного выполнения можно подключиться к вирутальной машине по SSH с помощью команды: ` vagrant ssh `
   И можно будет проверить обновленно ядро, с помощью команды: ` uname -a `
