# Проєкт Взаємодії з Трембітою

Цей проєкт входить в набір прикладів взаємодії з API шлюзу безпечного обміну системи Трембіта (ШБО), 
що демонструють технічні особливості розробки вебсервісів та вебклієнтів, сумісних з системою Трембіта. 
Даний проєкт описує створення сумісного SOAP-клієнта 
мовою програмування Python з використанням фреймворку Flask та zeep для здійснення викликів SOAP API через ШБО.\
Приклад описує отримання з умовної бази даних (реєстру) відомості про інформаційні об’єкти (у прикладі об’єктом є користувач) 
та управління їх статусом, у тому числі відправку запитів на пошук, отримання, створення, редагування та видалення об’єктів через SOAP API.\
Додатково розглянуто функції API ШБО для завантаження архівів з підписаними електронними повідомленнями-запитами, 
повідомленнями-відповідями у вигляді ASiC-контейнерів, а також генерацію ключів і сертифікатів для взаємної автентифікації між SOAP-клієнтом та ШБО.


## Вимоги
- Python 3.10+
- Git (для клонування репозиторію)
- Ubuntu Server 24.04
  
## Структура проєкту

Структура проєкту виглядає наступним чином:

```
web-client_trembita_sync/
├── Dockerfile
├── LICENSE
├── README.Docker.md
├── README.md
├── app.py
├── asic
├── certs
│    ├── cert.pem
│    └── key.pem
├── compose.yaml
├── config.ini
├── deploy.sh
├── docs
│    ├── docker_installation.md
│    ├── manual_installation.md
│    └── script_installation.md
├── remove.sh
├── requirements.txt
├── templates
│    ├── create_person.html
│    ├── error.html
│    ├── list_certs.html
│    ├── list_files.html
│    ├── list_files_run_aawy.html
│    ├── list_person.html
│    ├── navbar.html
│    ├── search_form.html
│    └── user_form.html
└── utils.py
```
## Розгортання

- Для ручного розгортання дивіться [тут](./docs/manual_installation.md).
- Для розгортання за допомогою скрипта дивіться [тут](./docs/script_installation.md).
- Для розгортання у Docker дивіться [тут](./docs/docker_installation.md).

## Видалення

Ми додали скрипт `remove.sh` для автоматизації процесу видалення клієнту та очищення системи.
Скрипт працює лише у випадку якщо проєкт було розгорнуто також за допомогою скрипту автоматичного розгортання.

### Використання скрипта remove.sh

1. Зробіть файл виконуваним:

   ```bash
   chmod +x remove.sh
   ```

2. Запустіть скрипт:

   ```bash
   ./remove.sh
   ```

Скрипт автоматично зупинить та видалить системний сервіс, видалить віртуальне середовище, клонований репозиторій та системні залежності. 


## Внесок

Якщо ви хочете зробити свій внесок у проєкт, будь ласка, створіть форк репозиторію і відправте Pull Request.

## Ліцензія

Цей проект ліцензується відповідно до умов MIT License.
