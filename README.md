# Hibernate #1 — RPG Admin Panel API

Учебный проект по Hibernate, «Работа с БД».

## 📋 Описание проекта

Проект представляет собой альтернативную реализацию слоя репозитория для RPG-админки, который изначально использовал `Map` в качестве хранилища. Цель — заменить его на полноценную работу с базой данных через **Hibernate ORM**.

## 🎯 Задачи проекта

- [x] Сделать fork из репозитория (выполнено)
- [x] Добавить зависимости в `pom.xml`: `mysql-connector-java`, `hibernate-core-jakarta`
- [x] Выполнить Maven-билд (`mvn clean install`)
- [x] Использовать Java 1.8
- [x] Настроить конфигурацию запуска через IntelliJ IDEA (Tomcat)
- [x] Реализовать методы репозитория через Hibernate (`NativeQuery`, `NamedQuery`)
- [x] Настроить логирование запросов Hibernate

## 🛠️ Стек технологий

| Технология | Версия |
| :--- | :--- |
| **Java** | 1.8 |
| **Maven** | 3.10.0 |
| **Hibernate** | 5.6.11.Final |
| **MySQL Connector** | 8.0.33 |
| **Spring Framework** | 5.3.23 |
| **Thymeleaf** | 3.0.15.RELEASE |
| **Tomcat** | 9.0.119 |
| **MySQL Server** | 8.0.46 |

## 🚀 Запуск проекта

1.  **Клонируйте репозиторий:**
    ```bash
    git clone https://github.com/aaxxmm/project-hibernate-1.git

2. Настройте базу данных MySQL:

Создайте схему rpg.

Выполните SQL-скрипт src/main/resources/init.sql для создания таблицы player и заполнения её данными.

3. Настройте подключение к БД:

Проверьте настройки в конструкторе класса PlayerRepositoryDB.java (URL, пользователь, пароль).

4. Соберите проект:


    mvn clean install

5. Запустите приложение:

Настройте Tomcat Server в IntelliJ IDEA, указав артефакт rpg-hibernate:war exploded.

Запустите Tomcat.

Откройте в браузере: http://localhost:8091/

## 🧠 Реализация
###  Класс PlayerRepositoryDB
Основной класс, реализующий интерфейс IPlayerRepository через Hibernate.

. getAll(int pageNumber, int pageSize) — получает список игроков с пагинацией через NativeQuery.

. getAllCount() — возвращает общее количество игроков через NamedQuery.

. save(Player player) — сохраняет нового игрока в БД.

. update(Player player) — обновляет данные существующего игрока.

. findById(long id) — находит игрока по ID.

. delete(Player player) — удаляет игрока из БД.

###  Логирование запросов
Для детального анализа SQL-запросов, которые генерирует Hibernate, добавлена зависимость p6spy. В консоли сервера отображаются подготовленные стейтменты и запросы с подставленными параметрами.

## 📝 Примечания
Проект выполнен в учебных целях.