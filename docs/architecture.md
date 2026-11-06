<div align="center">

# Архітектура TREBA

### Від сторінки товару до замовлення та доставки змін

[English](architecture.en.md) · **Українська**

![Next.js](https://img.shields.io/badge/Next.js-16-111827?style=for-the-badge&logo=nextdotjs) ![.NET](https://img.shields.io/badge/dotnet-10-512BD4?style=for-the-badge&logo=dotnet) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker) ![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonwebservices)

[Головна](../README.uk.md) · [Історія](history/project-history.md) · [Команда](team/README.md)

</div>

TREBA складається з вебінтерфейсу, окремого API та PostgreSQL. Frontend показує каталог, кошик, кабінети й адміністративні сторінки. Backend відповідає за бізнес-логіку, доступ і роботу з даними.

## Як проходить запит

```mermaid
flowchart LR
    USER["Користувач"] --> NEXT["Next.js / React"]
    NEXT -->|"Каталог"| API["ASP.NET Core / .NET 10 API"]
    NEXT -->|"Сесії, кошик, замовлення"| PROXY["Next.js shop-api / admin-api"]
    PROXY --> API
    API --> EF["EF Core / Npgsql"]
    EF --> DB[("PostgreSQL")]
    style NEXT fill:#002AFF,color:#ffffff,stroke:#002AFF
    style PROXY fill:#002AFF,color:#ffffff,stroke:#002AFF
    style API fill:#FF6E2A,color:#ffffff,stroke:#FF6E2A
```

| Частина | За що відповідає |
|---|---|
| **Frontend** | Next.js, React і TypeScript. Сторінки магазину, кабінет покупця, продавця та адміністративний простір. |
| **Backend API** | ASP.NET Core і .NET 10. Каталог, облікові записи, замовлення, продавці, відгуки та інтеграції. |
| **Дані** | Entity Framework Core і Npgsql працюють з PostgreSQL. |

### Основні сценарії

- **Каталог.** Сторінки товарів отримують дані через [API-шар frontend](https://github.com/tr3ba/treba-frontend/pull/15) та [API каталогу backend](https://github.com/tr3ba/treba-backend/pull/12).
- **Покупка.** Для авторизованого користувача [кошик і checkout](https://github.com/tr3ba/treba-frontend/pull/32) звертаються до backend. Гостьовий кошик зберігається у браузері до входу.
- **Доступ.** Маршрути shop-api й admin-api допомагають розділити клієнтські та staff-сесії. [Google/Facebook вхід](https://github.com/tr3ba/treba-backend/pull/91) додано окремо від звичайної реєстрації.
- **Адміністрування.** Інтерфейс працює у frontend /admin після [перенесення з backend](https://github.com/tr3ba/treba-frontend/pull/50). Backend надає необхідні API.

## Як доставляються зміни

```mermaid
flowchart LR
    GH["GitHub Actions"] --> CHECK["Перевірки та build"]
    CHECK --> ECR["Docker image / Amazon ECR"]
    ECR --> SSM["AWS Systems Manager"]
    SSM --> EC2["EC2 / candidate та попередній контейнер"]
    style GH fill:#002AFF,color:#ffffff,stroke:#002AFF
    style CHECK fill:#002AFF,color:#ffffff,stroke:#002AFF
    style ECR fill:#FF6E2A,color:#ffffff,stroke:#FF6E2A
    style EC2 fill:#FF6E2A,color:#ffffff,stroke:#FF6E2A
```

Backend і frontend мають окремі GitHub Actions workflows. Після перевірок збираються Docker-образи, публікуються в ECR і розгортаються на EC2 через Systems Manager. Скрипти перевіряють новий контейнер і зберігають попередній для повернення застосунку.

[Backend workflow](https://github.com/tr3ba/treba-backend/blob/main/.github/workflows/deploy-backend.yml) · [Frontend workflow](https://github.com/tr3ba/treba-frontend/blob/main/.github/workflows/deploy-frontend.yml) · [Розбір проблем доставки](incidents/README.md)

## Середовища

| Середовище | Використання |
|---|---|
| **AWS / EC2** | Доставка Docker-образів через ECR і SSM, запуск backend та frontend. |
| **Docker Compose** | Локальний запуск застосунку й PostgreSQL для розробки. |
| **Kubernetes Stage 5** | Окрема локальна гілка експериментів із Deployment, probes, ingress і migration Job. |

[Backend README](https://github.com/tr3ba/treba-backend/blob/main/README.md) · [Frontend README](https://github.com/tr3ba/treba-frontend/blob/main/README.md) · [На головну](../README.uk.md)
