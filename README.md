# Дашборд конверсий


[![hexlet-check](https://github.com/hypnozer/python-for-data-analysts-project-100/actions/workflows/hexlet-check.yml/badge.svg)](https://github.com/hypnozer/python-for-data-analysts-project-100/actions)

Анализ посещений и регистраций образовательной платформы.
Первый этап — загрузка двух CSV и предварительное исследование данных
в [Jupyter Notebook](data_preparation.ipynb).

Учебный проект Хекслета: https://ru.hexlet.io/programs/python-for-data-analysts


## Стек

- Python 3.11+ (проверено на Python 3.14)
- pandas и requests для работы с данными
- Jupyter Notebook для интерактивного выполнения

## Установка

```bash
git clone https://github.com/hypnozer/python-for-data-analysts-project-100.git
cd python-for-data-analysts-project-100
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements-dev.txt
```

## Использование

Из корня репозитория запустите:

```bash
jupyter notebook data_preparation.ipynb
```

Выберите ядро Python из созданного окружения и выполните все ячейки сверху вниз
(Restart Kernel and Run All Cells). В notebook сохранены результаты выполнения:
структура таблиц, `describe(include="all")`, проверки пропусков и дубликатов,
распределения категорий, диапазоны дат и выводы.

При первом запуске notebook скачивает [визиты](https://drive.google.com/file/d/1QosQQ4RRNR9rkL4t7sB707h2Uy0XfYJe/view)
и [регистрации](https://drive.google.com/file/d/1AeQz0kaSgz0lxYSDtuNm36muhy5fRCzZ/view)
через requests. Локальные копии сохраняются в `data/` и исключены из Git.
Повторный запуск использует эти файлы; для обновления удалите `data/visits.csv`
и `data/registrations.csv` и выполните notebook заново.

Обе выгрузки содержат по 1000 строк без пропусков и полных дубликатов.
Визиты охватывают 1–7 марта 2023 года, регистрации — 1–5 марта.
У визитов 519 уникальных посетителей, у регистраций 1000 уникальных пользователей
и 997 уникальных email. Разные периоды и отсутствие общего идентификатора
не позволяют интерпретировать отношение размеров выборок как конверсию.

В аналитическом коде используются только pandas и requests из разрешённого
списка. Jupyter и nbclient в `requirements-dev.txt` — инструменты запуска notebook.

---

<details>
<summary>Автоматические тесты Хекслета</summary>

Тесты запускаются на каждый коммит. За запуск отвечает файл `.github/workflows/hexlet-check.yml` — не удаляйте и не переименовывайте ни его, ни репозиторий.

</details>

## О Хекслете

[Хекслет](https://ru.hexlet.io/) — школа программирования: авторские программы обучения с практикой, поддержкой наставников и реальными проектами, которые остаются в резюме. Этот репозиторий — один из таких проектов.
