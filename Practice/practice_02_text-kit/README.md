# Text Kit

Учебный проект: строки, числа, проверка данных и даты.

## Назначение

Демонстрирует приёмы работы со строками, датами, числами и проверкой данных.
Точка входа — `app/main.py`, запускается как модуль.

## Структура проекта

- `app/main.py` — точка запуска: константы с примерами данных, функция `main()`
- `app/__init__.py` — делает `app` пакетом
- `app/utils/__init__.py` — делает `app.utils` пакетом
- `app/utils/text.py` — функции для строк: `clean_spaces`, `shorten`, `initials`, `slug`
- `app/utils/dates.py` — функции для дат: `parse_date`, `format_date`, `is_weekend`, `days_between`
- `app/services/__init__.py` — делает `app.services` пакетом
- `app/services/statistics.py` — расчёты: `average`, `median`, `spread`, `count_values`
- `app/services/validation.py` — проверка данных: `is_email`, `normalize_phone`, `is_phone`, `password_problems`
- `tests/` — модульные тесты (`unittest`)

## Запуск

Из корня проекта:

    python -m app.main

Ожидаемый вывод — блоки «СТРОКИ», «ЧИСЛА», «ПРОВЕРКА ДАННЫХ», «ДАТЫ»
с результатами по образцам из `app/main.py`.

## Тесты

    python -m unittest discover -s tests -v

Ожидается 19 тестов, в конце — `OK`.

## Принцип разделения функций

- **`app/utils/`** — общие мелкие функции, которые не зависят от предметной
  области и пригодятся в любом проекте: работа со строками и датами.
- **`app/services/`** — правила конкретно этого проекта: расчёты по числам
  (среднее, медиана, разброс, подсчёт значений) и проверка данных
  (почта, телефон, пароль).
  