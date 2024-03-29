# Тестовое задание для Backend Python Developer

[Ссылка на GitHub](https://github.com/GennadyBr/fastapi_pg_jwt_email)

### Задача:
    • Используйте фреймворк FastAPI и базу данных PostgreSQL. 
    • Разработайте API для управления пользователями. 


## Проект развернут на VPS
[Ссылка на VPS](http://5.35.83.245:8002/docs)

### Логи выводятся в консоль и в файл
    logs/fastapi_elk.log

### Авторизация
    для http://5.35.83.245:8002/login
    используйте:
    login abcd12
    password abcd12

## Для локального запуска выполните следующие команды

### Скопируйте репозиторий:
    git clone https://github.com/GennadyBr/fastapi_pg_jwt_email.git

### Переименуйте файл .env.example в .env:

### Запустите контейнеры:
    make up

### Сделайте миграцию alembic:
    make al

### Перейдите в папку с проектом:
    cd fastapi_pg_jwt_email

### Запустите проект:
    python main.py

### Перейдите по ссылке:
http://0.0.0.0:8002/docs

### Логи выводятся в консоль и в файл
    logs/fastapi_elk.log

### Авторизация
    для http://0.0.0.0:8002/login
    используйте:
    login abcd12
    password abcd12



### Описание модели данных: 
### Создайте модель пользователя с полями: 
    • id: целое число, автоматически генерируется при создании пользователя. 
    • username: строка, уникальное поле, от 6 до 36 символов. 
    • email: строка, уникальное поле, валидный адрес электронной почты. 
    • password: строка, хэш пароля с использованием bcrypt. 
    • config: json, личная информация о пользователях. 
        ◦ ФИО: строка, до 200 символов. 
        ◦ дата рождения 
        ◦ список из тегов 
### Описание API: 
    1. Регистрация пользователя: 
        ◦ Метод: POST 
        ◦ Путь: /register 
        ◦ Сделать отправку письма на почту 
        ◦ Поля входных данных (типы данных, ограничения):  
            ▪ username 
            ▪ email (валидация адреса электронной почты) 
            ▪ password  
            ▪ fio 
            ▪ birthday 
            ▪ tags 
        ◦ Возвращаемый результат: JSON с информацией о зарегистрированном пользователе. 
    2. Аутентификация пользователя: 
        ◦ Метод: POST 
        ◦ Путь: /login 
        ◦ Поля входных данных (типы данных, ограничения):  
            ▪ username (str) 
            ▪ password (str) 
        ◦ Возвращаемый результат: JSON с JWT-токеном для аутентификации. 
    3. Получение списка пользователей: 
        ◦ Метод: GET 
        ◦ Путь: /users 
        ◦ Поля входных данных (типы данных):  
            ▪ access_token (str, заголовок авторизации в формате "Bearer {токен}") 
        ◦ Возвращаемый результат: JSON со списком всех пользователей. 
    4. Поиск пользователей по полям: 
        ◦ Метод: GET 
        ◦ Путь: /users/search 
        ◦ Поля входных данных (типы данных):  
            ▪ jwt_token (заголовок авторизации в формате "Bearer {токен}") 
            ▪ username (необязательное поле) 
            ▪ email (необязательное поле) 
            ▪ fio (необязательное поле) 
            ▪ birthday (необязательное поле) 
            ▪ tags (необязательное поле) 
        ◦ Возвращаемый результат: JSON со списком найденных пользователей. 
    5. Удаление пользователя: 
        ◦ Метод: POST 
        ◦ Путь: /user_delete/{user_id} 
        ◦ Поля входных данных (типы данных):  
            ▪ jwt_token (заголовок авторизации в формате "Bearer {токен}") 
        ◦ Возвращаемый результат: JSON с информацией о удаленном пользователе. 
### Дополнительные требования: 
    • Реализуйте логирования каждого запроса, выводите в консоль информацию о типе запроса, пути и времени обработки, тело запроса и ответа.
    • Обеспечьте безопасность API с помощью JWT-токенов. 
    • Реализуйте систему проверку доступа к запросам 
    • Для отправки письма на почту используйте функцию (async def send_email_confirmation(email)). 
### Инструкции для сдачи тестового задания: 
    1. Сделайте репозиторий. 
    2. Создайте ветку с название fast_api_sqlalchemy_json. 
    3. Разработайте исходный код, соответствующий требованиям задачи. 
    4. Сделайте коммит и пуш ваш репозиторий. 
    5. Сделайте merge вашей ветки в master-ветку. 
    6. Отправьте ссылку HR или техническому специалисту  

### Удачи! 
  