
# Телефонный справочник жильцов  
### Современное десктоп-приложение для работы с базой данных жильцов  
**Python + Tkinter + PostgreSQL**


## Возможности

✔ Просмотр записей  
✔ Добавление жильцов  
✔ Редактирование  
✔ Удаление  
✔ Очистка неиспользуемых справочников  
✔ Поиск по любому полю  
✔ Управление справочниками  
✔ Удобный интерфейс на Tkinter  

---

## 🛠 Используемые технологии

| Компонент | Технология |
|----------|------------|
| Python | 3.10+ |
| GUI | Tkinter |
| База данных | PostgreSQL |
| Драйвер | psycopg2 |
| ОС | Windows / Linux / macOS |

---



## ⚙ Установка и запуск

### 1. Клонирование проекта

```bash
git clone <URL_вашего_репозитория>
cd <папка_проекта>
```
### 2. Установка зависимостей
```bash
pip install psycopg2-binary
```
### 3. Настройка подключения к базе
Отредактируйте параметры подключения в файле main.py (или в начале кода):

```bash
DB_NAME = "TelephoneBook"
DB_USER = "postgres"
DB_PASSWORD = "your_password"
DB_HOST = "localhost"
DB_PORT = "5432"
```
### 4. Создание структуры базы данных

```bash
CREATE TABLE fam (fam_id SERIAL PRIMARY KEY, fam_e VARCHAR(50));
CREATE TABLE name (name_id SERIAL PRIMARY KEY, name_e VARCHAR(50));
CREATE TABLE otc (otc_id SERIAL PRIMARY KEY, otc_e VARCHAR(50));
CREATE TABLE street (street_id SERIAL PRIMARY KEY, street_e VARCHAR(100));

CREATE TABLE main (
    id SERIAL PRIMARY KEY,
    fam INTEGER REFERENCES fam(fam_id),
    name INTEGER REFERENCES name(name_id),
    otc INTEGER REFERENCES otc(otc_id),
    street INTEGER REFERENCES street(street_id),
    bldn INTEGER,
    bldn_r INTEGER,
    appr INTEGER,
    telephone VARCHAR(20)
);
```
### 5. Запуск
```bash
python main.py
```
## Интерфейс
### Главное окно
- Добавить
- Изменить
- Удалить
- Поиск
- Обновить
### Справочники
- Добавление
- Редактирование
- Удаление, если не используется
