1. Используя команду cat в терминале операционной системы Linux, создать два файла Домашние животные (заполнив файл собаками, кошками, хомяками) и Вьючные животными заполнив файл Лошадьми, верблюдами и ослы, а затем объединить их. Просмотреть содержимое созданного файла.
Переименовать файл, дав ему новое имя (Друзья человека).

Для создания файлов используем команду cat вместе с перенаправлением вывода в файлы:

cat > "Домашние животные" << EOF
собаками
кошками
хомяками
EOF

cat > "Вьючные животные" << EOF
Лошадьми
верблюдами
ослы
EOF

Затем, чтобы объединить содержимое файлов, можно использовать команду cat с оператором >> для добавления текста в конец файла:

cat "Домашние животные" >> "Вьючные животные"

Теперь содержимое файлов "Домашние животные" и "Вьючные животными" объединено в файле "Вьючные животными".

Чтобы просмотреть содержимое созданного файла, можно использовать nano:

nano "Вьючные животные"

Чтобы переименовать файл, можно использовать команду mv:

mv "Вьючные животными" "Друзья человека"

2. Создать директорию, переместить файл туда.

Создаём директорию:
mkdir my_directory

Перемещаем туда файл:

mv "Друзья человека" my_directory/

3. Подключить дополнительный репозиторий MySQL. Установить любой пакет из этого репозитория.

Чтобы подключить дополнительный репозиторий MySQL, нужно выполнить следующие шаги:
Скачать и добавить ключ репозитория:
wget -O mysql-apt-config.deb https://dev.mysql.com/get/mysql-apt-config_0.8.15-1_all.deb
sudo dpkg -i mysql-apt-config.deb
При установке пакета mysql-apt-config будет предложено выбрать тип установки MySQL. Выберите нужный вариант и нажмите Enter.
Обновить список пакетов:
sudo apt update
Установить пакет из дополнительного репозитория:
sudo apt install mysql-workbench

Теперь пакет MySQL Workbench установлен из дополнительного репозитория MySQL.

4.	Установить и удалить deb-пакет с помощью dpkg.
Установка deb-пакета с помощью dpkg:
Сначала необходимо загрузить deb-пакет chromium-browser из официального репозитория Ubuntu с помощью следующей команды:
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
После этого можно установить пакет с помощью команды:
sudo dpkg -i google-chrome-stable_current_amd64.deb
Удаление установленного ранее deb-пакета с помощью dpkg:
Чтобы удалить установленный ранее пакет chromium-browser, выполните следующую команду в терминале:
sudo dpkg -r google-chrome-stable
При удалении пакетов с помощью dpkg могут оставаться ненужные зависимости, которые не будут удалены автоматически. Чтобы удалить эти зависимости, можно воспользоваться следующей командой:
sudo apt-get autoremove
