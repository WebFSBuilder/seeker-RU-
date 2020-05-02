# seeker-RU-
Русифицированная и доработанная версия Seeker Скрипта  


Концепция Seeker проста, подобно тому, как мы размещаем фишинговые страницы для получения учетных данных, почему бы не разместить поддельную страницу, которая запрашивает ваше местоположение, как многие популярные веб-сайты, основанные на местоположении. Подробнее читайте в блоге thewhiteh4t. Seeker Размещает поддельный веб-сайт на встроенном PHP-сервере и использует Serveo для создания ссылки, которую мы будем перенаправлять к цели, веб-сайт запрашивает разрешение на местоположение и, если цель позволяет, мы можем получить:

Долгота
широта
точность
Высота над уровнем моря - не всегда доступна
Направление - доступно только если пользователь движется
Скорость - доступно только если пользователь движется
Наряду с информацией о местоположении мы также получаем информацию об устройстве без каких-либо разрешений:

Операционная система
Платформа
Количество ядер процессора
Объем оперативной памяти - приблизительные результаты
Разрешение экрана
Информация о GPU
Имя и версия браузера
Публичный IP-адрес
Разведка IP-адресов
Этот инструмент является проверкой концепции и предназначен только для образовательных целей. Seeker показывает, какие данные может собирать вредоносный веб-сайт о вас и ваших устройствах, и почему вы не должны нажимать на случайные ссылки и разрешать такие важные разрешения, как местоположение и т. Д.

Чем это отличается от IP GeoLocation
Другие инструменты и сервисы предлагают IP-геолокацию, которая НЕ является точной и не дает определения местоположения цели, а является приблизительным местоположением провайдера.

Seeker использует HTML API и получает разрешение на местоположение, а затем захватывает долготу и широту с помощью GPS-оборудования, которое присутствует в устройстве, поэтому Seeker лучше всего работает со смартфонами, если отсутствует аппаратное GPS-оборудование, например на ноутбуке, Seeker откатывается на геолокацию IP. или он будет искать кэшированные координаты.

Обычно, если пользователь принимает разрешение на определение местоположения, точность полученной информации составляет приблизительно 30 метров , точность зависит от устройства.

Примечание . На iPhone по какой-то причине точность определения местоположения составляет приблизительно 65 метров.

Шаблоны
Вы можете выбрать шаблон, который будет использовать ищущий из следующих:

Возле тебя
Google Drive (предложено @Akaal_no_one)
WhatsApp (предложено @ Dazmed707)
Проверено на:
Kali Linux 2019.2
BlackArch Linux
Ubuntu 19.04
Кали Нетунтер
Termux
Попугай ОС
Установка
Kali Linux / Ubuntu / Parrot OS
git clone https://github.com/thewhiteh4t/seeker.git
 cd seeker /
chmod 777 install.sh
./install.sh
BlackArch Linux
pacman -S искатель
докер
докер тянуть белый4т / искатель
Termux
git clone https://github.com/thewhiteh4t/seeker.git
 cd seeker /
chmod 777 termux_install.sh
./termux_install.sh
Применение
python3 seeker.py -h

использование: seeker.py [-h] [-s SUBDOMAIN]

необязательные аргументы:
  -h, --help показать это справочное сообщение и выйти 
  -s SUBDOMAIN, --subdomain Субдомен Предоставить субдомен для URL-адреса Serveo (необязательно)
  -k KML, --kml KML Предоставить имя файла KML (необязательно)
  -t TUNNEL, --tunnel TUNNEL Указать туннельный режим [руководство]

# Пример

# SERVEO 
# #######
python3 seeker.py

# NGROK ETC. 
# ###########

# В First Terminal Start ищущий в ручном режиме, как это
python3 seeker.py -t руководство

# Во втором терминале запустите Ngrok или любой другой туннельный сервис на порту 8080
./ngrok http 8080

# ----------------------------------- #

# Subdomain 
# ##########
python3 seeker.py --subdomain google
python3 seeker.py - руководство по туннелю - subdomain zomato

# ----------------------------------- #

# Docker Usage 
# #############

# SERVEO 
# #######
docker run -t --rm thewhiteh4t / seeker

# NGROK 
# ######

# Шаг 1
докерную сеть создаю нгрокнет

# Шаг 2
docker run --rm -t --net ngroknet - имя ищущего thewhiteh4t / seeker python3 seeker.py -t руководство

# Шаг 3 
запуска docker --rm -t --net ngroknet --name ngrok wernight / ngrok ngrok http seeker: 8080
Известные проблемы
Такие службы, как Serveo и Ngrok, запрещены в некоторых странах, таких как Россия и т. Д., Поэтому, если они запрещены в вашей стране, вы можете не получить URL-адрес, если нет, то сначала ПРОЧИТАЙТЕ ЗАКРЫТЫЕ ПРОБЛЕМЫ, если вашей проблемы нет в списке, создайте новую проблему.
