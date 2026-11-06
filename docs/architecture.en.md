<div align="center">

# Treba architecture

### From a product page to an order and a deployed change

[Українська](architecture.md) · **English**

![Next.js](https://img.shields.io/badge/Next.js-16-111827?style=for-the-badge&logo=nextdotjs)
![.NET](https://img.shields.io/badge/dotnet-10-512BD4?style=for-the-badge&logo=dotnet)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonwebservices)

[Home](../README.en.md) · [History](history/project-history.en.md) · [Team](team/README.en.md)

</div>

Treba has a web interface, a separate API, and a PostgreSQL database. The frontend renders the store and account pages. The backend handles business rules, authorization, and persistence.

## How a request moves through the system

~~~mermaid
flowchart LR
    USER["User"] --> NEXT["Next.js / React"]
    NEXT -->|"Catalog"| API["ASP.NET Core / .NET 10 API"]
    NEXT -->|"Sessions, cart, orders"| PROXY["Next.js shop-api / admin-api"]
    PROXY --> API
    API --> EF["EF Core / Npgsql"]
    EF --> DB[("PostgreSQL")]
    style NEXT fill:#002AFF,color:#ffffff,stroke:#002AFF
    style PROXY fill:#002AFF,color:#ffffff,stroke:#002AFF
    style API fill:#FF6E2A,color:#ffffff,stroke:#FF6E2A
~~~

| Part | Responsibility |
|---|---|
| **Frontend** | Next.js, React, and TypeScript pages for the store, buyer and seller accounts, and admin workspace. |
| **Backend API** | ASP.NET Core on .NET 10 for catalog, accounts, orders, sellers, reviews, and integrations. |
| **Data** | Entity Framework Core and Npgsql for PostgreSQL models, queries, and migrations. |

### Main user flows

- **Catalog.** Product pages use the [frontend API layer](https://github.com/tr3ba/treba-frontend/pull/15) and the [backend catalog API](https://github.com/tr3ba/treba-backend/pull/12).
- **Shopping.** The [authenticated cart and checkout](https://github.com/tr3ba/treba-frontend/pull/32) call the backend. A guest cart stays in the browser until sign-in.
- **Access.** Next.js shop-api and admin-api routes help separate customer and staff sessions. [Google/Facebook sign-in](https://github.com/tr3ba/treba-backend/pull/91) complements the regular account flow.
- **Administration.** The interface runs at <code>/admin</code> in the frontend after the [migration from the backend UI](https://github.com/tr3ba/treba-frontend/pull/50). The backend provides the operations behind it.

## How changes are delivered

~~~mermaid
flowchart LR
    GH["GitHub Actions"] --> CHECK["Build and checks"]
    CHECK --> ECR["Docker image / Amazon ECR"]
    ECR --> SSM["AWS Systems Manager"]
    SSM --> EC2["EC2 / new and previous containers"]
    style GH fill:#002AFF,color:#ffffff,stroke:#002AFF
    style CHECK fill:#002AFF,color:#ffffff,stroke:#002AFF
    style ECR fill:#FF6E2A,color:#ffffff,stroke:#FF6E2A
    style EC2 fill:#FF6E2A,color:#ffffff,stroke:#FF6E2A
~~~

Backend and frontend have separate GitHub Actions workflows. They build and publish Docker images to ECR, then deploy to EC2 through Systems Manager. The scripts check the new container and keep the previous one for rollback.

[Backend workflow](https://github.com/tr3ba/treba-backend/blob/main/.github/workflows/deploy-backend.yml) · [Frontend workflow](https://github.com/tr3ba/treba-frontend/blob/main/.github/workflows/deploy-frontend.yml) · [Delivery issues](incidents/README.en.md)

## Environments

| Environment | Use |
|---|---|
| **AWS / EC2** | Docker image delivery through ECR and SSM, then backend and frontend containers. |
| **Docker Compose** | Local application and PostgreSQL setup for development. |
| **Kubernetes Stage 5** | A separate local track with Deployments, probes, ingress, and a migration Job. |

[Backend README](https://github.com/tr3ba/treba-backend/blob/main/README.md) · [Frontend README](https://github.com/tr3ba/treba-frontend/blob/main/README.md) · [Back to the overview](../README.en.md)
