<div align="center">

# Команда TREBA

### П'ятеро учасників, один маркетплейс

[English](README.en.md) · **Українська**

![Учасники](https://img.shields.io/badge/УЧАСНИКІВ-5-7C4DFF?style=for-the-badge) ![Злиті PR](https://img.shields.io/badge/ЗЛИТИХ_PR-151-FF6E2A?style=for-the-badge)

[Головна](../../README.uk.md) · [Історія](../history/project-history.md) · [Архітектура](../architecture.md)

</div>

TREBA виріс із паралельної роботи над інтерфейсом, API та доставкою застосунку. Нижче коротко показано, за які частини відповідали учасники і де можна побачити їхні зміни.

## Учасники

| Людина | Напрям | Приклади роботи |
|---|---|---|
| <img src="https://github.com/amonezeer.png?size=96" width="44" alt=""> [amonezeer](#author-amonezeer) | API, адмінпростір, інтеграція | [Імпорт і продавці](https://github.com/tr3ba/treba-backend/pull/64), [новий адмінпростір](https://github.com/tr3ba/treba-frontend/pull/50) |
| <img src="https://github.com/F1eshka.png?size=96" width="44" alt=""> [F1eshka](#author-f1eshka) | Інтерфейс магазину, UX | [Каталог через API](https://github.com/tr3ba/treba-frontend/pull/15), [адаптивність](https://github.com/tr3ba/treba-frontend/pull/16) |
| <img src="https://github.com/thewhitemage13.png?size=96" width="44" alt=""> [thewhitemage13](#author-thewhitemage13) | Каталог, кошик, відгуки | [API каталогу](https://github.com/tr3ba/treba-backend/pull/12), [кошик](https://github.com/tr3ba/treba-backend/pull/38) |
| <img src="https://github.com/Quixar.png?size=96" width="44" alt=""> [Quixar](#author-quixar) | Архітектура, доступ, замовлення | [Основа backend](https://github.com/tr3ba/treba-backend/pull/1), [замовлення](https://github.com/tr3ba/treba-backend/pull/55) |
| <img src="https://github.com/Broadcast1Storm.png?size=96" width="44" alt=""> [Broadcast1Storm](#author-broadcast1storm) | Docker, CI/CD, AWS | [Docker](https://github.com/tr3ba/treba-backend/pull/3), [доставка через SSM](https://github.com/tr3ba/treba-backend/pull/8) |

<a id="author-amonezeer"></a>
## amonezeer

**API · адмінпростір · інтеграція**

Працював над адміністративними сценаріями, інструментами продавця, імпортом товарів і підтримкою. Коли адмінпростір переїхав у frontend, узгоджував зміни з backend API.

[Імпорт і продавці](https://github.com/tr3ba/treba-backend/pull/64) · [Підтримка та діалоги](https://github.com/tr3ba/treba-backend/pull/66) · [Адмінпростір у frontend](https://github.com/tr3ba/treba-frontend/pull/50) · [Профіль GitHub](https://github.com/amonezeer)

<a id="author-f1eshka"></a>
## F1eshka

**Інтерфейс магазину · UX**

Розвивав сторінки каталогу, мобільну версію, кошик і оформлення замовлення. Підключення реального API замінило початкові демонстраційні дані.

[Каталог і API](https://github.com/tr3ba/treba-frontend/pull/15) · [Адаптивний інтерфейс](https://github.com/tr3ba/treba-frontend/pull/16) · [Кошик і замовлення](https://github.com/tr3ba/treba-frontend/pull/32) · [Скасування замовлення](https://github.com/tr3ba/treba-frontend/pull/56) · [Профіль GitHub](https://github.com/F1eshka)

<a id="author-thewhitemage13"></a>
## thewhitemage13

**Каталог · кошик · відгуки**

Реалізував серверні можливості для товарів і категорій, продавців, кошика та відгуків. Ці API стали основою покупок і наповнення маркетплейсу.

[API каталогу](https://github.com/tr3ba/treba-backend/pull/12) · [Продавці та магазини](https://github.com/tr3ba/treba-backend/pull/37) · [Кошик](https://github.com/tr3ba/treba-backend/pull/38) · [Профіль GitHub](https://github.com/thewhitemage13)

<a id="author-quixar"></a>
## Quixar

**Основа backend · доступ · замовлення**

Заклав архітектурну основу backend і доменні сутності. Далі працював над авторизацією, залишками, замовленнями та оплатою.

[Архітектурна основа](https://github.com/tr3ba/treba-backend/pull/1) · [Авторизація](https://github.com/tr3ba/treba-backend/pull/31) · [Замовлення](https://github.com/tr3ba/treba-backend/pull/55) · [Профіль GitHub](https://github.com/Quixar)

<a id="author-broadcast1storm"></a>
## Broadcast1Storm

**Контейнери · CI/CD · AWS**

Працював над Docker-образами, автоматичною збіркою та доставкою backend і frontend до AWS. Окремо розвивав перевірки CI й експериментальний локальний Kubernetes Stage 5.

[Docker backend](https://github.com/tr3ba/treba-backend/pull/3) · [ECR](https://github.com/tr3ba/treba-backend/pull/6) · [Розгортання через SSM](https://github.com/tr3ba/treba-backend/pull/8) · [Frontend delivery](https://github.com/tr3ba/treba-frontend/pull/7) · [Профіль GitHub](https://github.com/Broadcast1Storm)

---

[Усі backend PR](https://github.com/tr3ba/treba-backend/pulls?q=is%3Apr) · [Усі frontend PR](https://github.com/tr3ba/treba-frontend/pulls?q=is%3Apr) · [Історія проєкту](../history/project-history.md)
