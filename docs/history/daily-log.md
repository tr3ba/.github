<div align="center">

# Журнал розробки TREBA

### Ключові дні з липня до листопада 2026

[English](daily-log.en.md) · **Українська**

[Головна](../../README.uk.md) · [Історія проєкту](project-history.md) · [Команда](../team/README.md)

</div>

Тут зібрано дні, коли проєкт помітно змінювався. Для деталей можна відкрити відповідний PR або коміт.

[**07 Липень**](#daily-july) · [**08 Серпень**](#daily-august) · [**09 Вересень**](#daily-september) · [**10 Жовтень**](#daily-october) · [**11 Листопад**](#daily-november)

<a id="daily-july"></a>
## Липень: старт

| День | Що відбулося |
|---|---|
| **18 липня** | Команда отримала завдання створити маркетплейс за наданим дизайном. |
| **20 липня** | З'явилися окремі [backend](https://github.com/tr3ba/treba-backend/commit/a44ad6dca4be32cb07806f94cc4e55807950c459) і [frontend](https://github.com/tr3ba/treba-frontend/commit/e75d570a8240d7a05ed8c0f7b1523e530ca3a035) репозиторії. |
| **25-26 липня** | У [backend PR #1](https://github.com/tr3ba/treba-backend/pull/1) заклали архітектурну основу й доменні сутності. |

<a id="daily-august"></a>
## Серпень: Docker і перша доставка

| День | Що відбулося |
|---|---|
| **3 серпня** | Почалася робота над [адміністративною панеллю](https://github.com/tr3ba/treba-backend/pull/2). |
| **8 серпня** | Додали [Dockerfile для backend](https://github.com/tr3ba/treba-backend/pull/3). |
| **22 серпня** | Підключили [користувачів і базу даних](https://github.com/tr3ba/treba-backend/pull/5). |
| **30-31 серпня** | Налаштували публікацію образів в [ECR](https://github.com/tr3ba/treba-backend/pull/6), розгортання backend через [SSM](https://github.com/tr3ba/treba-backend/pull/8) і [доставку frontend](https://github.com/tr3ba/treba-frontend/pull/7). |

<a id="daily-september"></a>
## Вересень: каталог і доступ

| День | Що відбулося |
|---|---|
| **13 вересня** | З'явилися [збереження каталогу й API](https://github.com/tr3ba/treba-backend/pull/12), а в CI додали [перевірку залежностей](https://github.com/tr3ba/treba-backend/pull/14). |
| **17 вересня** | Адмінпанель отримала [список і картку користувача](https://github.com/tr3ba/treba-backend/pull/20). |
| **18 вересня** | Розширили API для [категорій і брендів](https://github.com/tr3ba/treba-backend/pull/24), атрибутів, варіантів і фото товарів. |
| **19 вересня** | Додали [авторизацію користувача](https://github.com/tr3ba/treba-backend/pull/31). |

<a id="daily-october"></a>
## Жовтень: маркетплейс складається разом

| День | Що відбулося |
|---|---|
| **2 жовтня** | У backend з'явилися [продавці й магазини](https://github.com/tr3ba/treba-backend/pull/37) та [кошик](https://github.com/tr3ba/treba-backend/pull/38). |
| **7-8 жовтня** | Frontend отримав [API-шар і сторінки каталогу](https://github.com/tr3ba/treba-frontend/pull/15). |
| **14 жовтня** | Додали [замовлення](https://github.com/tr3ba/treba-backend/pull/55). |
| **20-21 жовтня** | Розвивали [інструменти продавця](https://github.com/tr3ba/treba-backend/pull/64), [звернення до підтримки](https://github.com/tr3ba/treba-backend/pull/66) та [оформлення замовлення через API](https://github.com/tr3ba/treba-frontend/pull/32). |
| **22 жовтня** | Узгодили [заявки продавців у backend](https://github.com/tr3ba/treba-backend/pull/80) з [інтерфейсом](https://github.com/tr3ba/treba-frontend/pull/36). |
| **26 жовтня** | Підключили [Нову Пошту й кур'єрську доставку](https://github.com/tr3ba/treba-backend/pull/86) до [checkout](https://github.com/tr3ba/treba-frontend/pull/42). |
| **28 жовтня** | Завершили [Google/Facebook вхід у backend](https://github.com/tr3ba/treba-backend/pull/91) і [frontend](https://github.com/tr3ba/treba-frontend/pull/45). |
| **29 жовтня** | Адміністративний простір перенесли у [frontend](https://github.com/tr3ba/treba-frontend/pull/50), прибравши старий [backend інтерфейс](https://github.com/tr3ba/treba-backend/pull/96). |
| **31 жовтня** | Доробили [фільтри та дані користувачів в адмінпросторі](https://github.com/tr3ba/treba-frontend/pull/54). |

<a id="daily-november"></a>
## Листопад: замовлення

| День | Що відбулося |
|---|---|
| **5 листопада** | Покупець отримав можливість [скасувати замовлення](https://github.com/tr3ba/treba-frontend/pull/56) зі сторінки замовлення. |

[Докладніше про етапи](project-history.md) · [Помилки та виправлення](../incidents/README.md)
