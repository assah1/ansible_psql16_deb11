# Ansible Playbook для Настройки PostgreSQL

Этот Ansible playbook автоматизирует установку и настройку PostgreSQL на целевых серверах. Он включает управление пакетами, настройку брандмауэра (UFW) и конфигурацию самой базы данных.

## Содержание

- [Описание](#описание)
- [Структура Playbook](#структура-playbook)
- [Переменные](#переменные)
- [Использование](#использование)
- [Примечания](#примечания)

---

## Описание

Данный playbook выполняет следующие действия:

- Устанавливает необходимые пакеты.
- Настраивает часовой пояс.
- Включает и настраивает UFW для управления доступом.
- Добавляет GPG ключ и репозиторий для установки PostgreSQL.
- Устанавливает и настраивает PostgreSQL.
- Создает базу данных и пользователя с заданными правами доступа.
- Обновляет конфигурации PostgreSQL для логирования и доступа.

---

## Структура Playbook

1. **Загрузка Переменных**: Загружает переменные из файла `vars.yml`.
2. **Установка Пакетов**: Устанавливает необходимые для базовой работы сервера пакеты:
   - `python3-psycopg2`
   - `curl`
   - `git`
   - `ufw`
   - и другие.
3. **Настройка Часового Пояса**: Устанавливает временную зону.
4. **Настройка UFW**: Включает UFW и устанавливает правила доступа.
5. **Настройка rsyslog**: Настраивает ведение журналов UFW.
6. **Добавление GPG Ключа**: Скачивает и добавляет GPG ключ PostgreSQL.
7. **Добавление APT Репозитория**: Добавляет репозиторий PostgreSQL для установки.
8. **Установка PostgreSQL**: Устанавливает PostgreSQL.
9. **Запуск и Включение Службы**: Запускает и включает PostgreSQL.
10. **Инициализация PostgreSQL**: Проверяет и инициализирует базу данных.
11. **Создание Базы Данных и Пользователя**: Создает базу данных и пользователя.
12. **Настройка Привилегий**: Устанавливает права доступа к базе данных.
13. **Обновление Конфигурации**: Обновляет конфигурацию PostgreSQL.
14. **Настройка Логирования**: Настраивает параметры логирования.
15. **Настройка Доступа**: Устанавливает метод подключения для всех пользователей.
