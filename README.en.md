<div align="center">

[🇺🇦 Українська](profile/README.md) · **🇬🇧 English**

<br>

# 🛒 Treba Marketplace

### Marketplace · Cloud infrastructure · DevOps

A team marketplace with a product catalog, cart, orders, and dedicated spaces for buyers, sellers, and administrators. The interface, API, and delivery pipeline evolved as separate parts of the same project.

<br>

[![Demo](https://img.shields.io/badge/DEMO-002AFF?style=for-the-badge&logo=googlechrome&logoColor=white)](https://treba.duckdns.org)
[![Backend](https://img.shields.io/badge/BACKEND-FF6E2A?style=for-the-badge&logo=dotnet&logoColor=white)](https://github.com/tr3ba/treba-backend)
[![Frontend](https://img.shields.io/badge/FRONTEND-002AFF?style=for-the-badge&logo=nextdotjs&logoColor=white)](https://github.com/tr3ba/treba-frontend)

<br>

![.NET](https://img.shields.io/badge/.NET_10-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js_16.2.12-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React_19.2.4-61DAFB?style=flat-square&logo=react&logoColor=000000)
![TypeScript](https://img.shields.io/badge/TypeScript_5.x-3178C6?style=flat-square&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat-square&logo=amazonwebservices&logoColor=white)

</div>

---

## Explore the project

| | |
|---|---|
| **🕓 [Project history](docs/history/project-history.en.md)**<br>How Treba grew from its first repositories to a marketplace. | **👥 [Team](docs/team/README.en.md)**<br>Who worked on the interface, API, and delivery. |
| **🏗️ [Architecture](docs/architecture.en.md)**<br>How the web app, API, database, and deployment fit together. | **🛠️ [Issues and fixes](docs/incidents/README.en.md)**<br>Deployment problems, CI failures, and the changes that addressed them. |

## About Treba

Treba began as a student team project in July 2026. The original brief was to build an online store from a supplied design. The code grew into a marketplace with catalog and order flows, seller tools, support, and an administrative workspace. Backend and frontend live in separate repositories.

The frontend is built with Next.js, React, and TypeScript. The backend is an ASP.NET Core API using PostgreSQL through Entity Framework Core and Npgsql. Docker, GitHub Actions, Amazon ECR, EC2, and Systems Manager form the delivery path described in the repositories.

## What is in the project

| Area | Implemented work |
|---|---|
| **Catalog** | [Catalog persistence and APIs](https://github.com/tr3ba/treba-backend/pull/12), [categories and product data](https://github.com/tr3ba/treba-backend/pull/24), and [frontend catalog pages](https://github.com/tr3ba/treba-frontend/pull/15). |
| **Shopping** | [Cart and checkout](https://github.com/tr3ba/treba-frontend/pull/32) connected to the API, [orders](https://github.com/tr3ba/treba-backend/pull/55), and [buyer order cancellation](https://github.com/tr3ba/treba-frontend/pull/56). |
| **Accounts** | [Registration and password recovery](https://github.com/tr3ba/treba-backend/pull/94) with email or SMS verification, plus [Google and Facebook sign-in](https://github.com/tr3ba/treba-frontend/pull/45). |
| **Sellers** | [Seller applications](https://github.com/tr3ba/treba-backend/pull/80), a [seller page](https://github.com/tr3ba/treba-frontend/pull/25), and [product import](https://github.com/tr3ba/treba-backend/pull/64). |
| **Delivery and support** | [Nova Poshta and Treba courier options](https://github.com/tr3ba/treba-backend/pull/86), [support conversations](https://github.com/tr3ba/treba-backend/pull/66), and [reviews after delivery](https://github.com/tr3ba/treba-backend/pull/93). |
| **Administration** | The administrative workspace moved into [Next.js /admin](https://github.com/tr3ba/treba-frontend/pull/50). |

The [history](docs/history/project-history.en.md) gives the sequence behind these features. The [development log](docs/history/daily-log.en.md) is a shorter day-by-day view.

## 🧩 Core technologies

<table width="100%">
<tr><th width="50%">🎨 Frontend</th><th width="50%">⚙️ Backend</th></tr>
<tr>
<td width="50%" align="center" valign="top"><br><img src="https://skillicons.dev/icons?i=nextjs&theme=dark" width="64" height="64" alt="Next.js"><br><strong>Next.js</strong> <code>16.2.12</code><p>Pages, routing, and server-side features.</p></td>
<td width="50%" align="center" valign="top"><br><img src="https://skillicons.dev/icons?i=dotnet&theme=dark" width="64" height="64" alt="ASP.NET Core"><br><strong>ASP.NET Core</strong> <code>.NET 10</code><p>The API for catalog, accounts, and orders.</p></td>
</tr>
<tr>
<td width="50%" align="center" valign="top"><br><img src="https://skillicons.dev/icons?i=react&theme=dark" width="64" height="64" alt="React"><br><strong>React</strong> <code>19.2.4</code><p>Interactive storefront and workspace components.</p></td>
<td width="50%" align="center" valign="top"><br><img src="https://skillicons.dev/icons?i=dotnet&theme=dark" width="64" height="64" alt="Entity Framework Core"><br><strong>Entity Framework Core</strong> <code>10</code><p>Data models, queries, and migrations.</p></td>
</tr>
<tr>
<td width="50%" align="center" valign="top"><br><img src="https://skillicons.dev/icons?i=ts&theme=dark" width="64" height="64" alt="TypeScript"><br><strong>TypeScript</strong> <code>5.x</code><p>Types across UI and API calls.</p></td>
<td width="50%" align="center" valign="top"><br><img src="https://skillicons.dev/icons?i=postgres&theme=dark" width="64" height="64" alt="Npgsql"><br><strong>Npgsql</strong> <code>10.0.3</code><p>PostgreSQL access for Entity Framework Core.</p></td>
</tr>
</table>

## 🗄️ Data layer

<table width="100%">
<tr>
<td width="50%" align="center" valign="top"><br><img src="https://skillicons.dev/icons?i=postgres&theme=dark" width="64" height="64" alt="PostgreSQL"><br><strong>PostgreSQL</strong><p>The marketplace's relational database, accessed by the backend through EF Core and Npgsql.</p></td>
<td width="50%" align="center" valign="top"><br><img src="https://awsfundamentals.com/assets/aws-icons/Arch_Amazon-RDS_64.svg" width="64" height="64" alt="Amazon RDS"><br><strong>Amazon RDS</strong><p>The managed PostgreSQL service in the AWS architecture.</p></td>
</tr>
</table>

## ☁️ AWS and DevOps

<table width="100%">
<tr><th width="50%">🚀 Delivery and runtime</th><th width="50%">🛡️ Operations and infrastructure</th></tr>
<tr>
<td width="50%" align="center" valign="top"><br><img src="https://skillicons.dev/icons?i=docker&theme=dark" width="64" height="64" alt="Docker"><br><strong>Docker</strong><p>Containers for backend and frontend.</p></td>
<td width="50%" align="center" valign="top"><br><img src="https://awsfundamentals.com/assets/aws-icons/Arch_AWS-Systems-Manager_64.svg" width="64" height="64" alt="AWS Systems Manager"><br><strong>Systems Manager</strong><p>Remote deployment commands.</p></td>
</tr>
<tr>
<td width="50%" align="center" valign="top"><br><img src="https://skillicons.dev/icons?i=githubactions&theme=dark" width="64" height="64" alt="GitHub Actions"><br><strong>GitHub Actions</strong><p>Build, test, image publishing, and delivery workflows.</p></td>
<td width="50%" align="center" valign="top"><br><img src="https://awsfundamentals.com/assets/aws-icons/Arch_Amazon-CloudWatch_64.svg" width="64" height="64" alt="Amazon CloudWatch"><br><strong>CloudWatch</strong><p>Infrastructure monitoring and alarms.</p></td>
</tr>
<tr>
<td width="50%" align="center" valign="top"><br><img src="https://awsfundamentals.com/assets/aws-icons/Arch_Amazon-Elastic-Container-Registry_64.svg" width="64" height="64" alt="Amazon ECR"><br><strong>Amazon ECR</strong><p>Registry for application images.</p></td>
<td width="50%" align="center" valign="top"><br><img src="https://awsfundamentals.com/assets/aws-icons/Arch_AWS-Identity-and-Access-Management_64.svg" width="64" height="64" alt="AWS IAM"><br><strong>IAM</strong><p>Access to cloud resources.</p></td>
</tr>
<tr>
<td width="50%" align="center" valign="top"><br><img src="https://awsfundamentals.com/assets/aws-icons/Arch_Amazon-EC2_64.svg" width="64" height="64" alt="Amazon EC2"><br><strong>Amazon EC2</strong><p>Host for the deployed containers.</p></td>
<td width="50%" align="center" valign="top"><br><img src="https://awsfundamentals.com/assets/aws-icons/Arch_AWS-Secrets-Manager_64.svg" width="64" height="64" alt="AWS Secrets Manager"><br><strong>Secrets Manager</strong><p>Runtime secret access.</p></td>
</tr>
</table>

## 🏗️ System architecture

~~~mermaid
flowchart LR
    USER["Buyer or seller"] --> WEB["Next.js / React"]
    WEB --> API["ASP.NET Core API"]
    API --> DATA["EF Core / Npgsql"]
    DATA --> DB[("PostgreSQL")]
    WEB --> ROUTES["Next.js shop-api / admin-api"]
    ROUTES --> API
~~~

Catalog pages read from the API. Authenticated cart and order flows use the backend; a guest cart stays in the browser until sign-in. The administrative interface runs in the frontend, while its operations are served by the API. [Read the architecture page](docs/architecture.en.md).

## 🚀 Delivery pipeline

~~~mermaid
flowchart LR
    GH["GitHub Actions"] --> CHECK["Build and checks"]
    CHECK --> ECR["Docker image / ECR"]
    ECR --> SSM["Systems Manager"]
    SSM --> EC2["EC2 container"]
~~~

Backend and frontend have separate workflows. Their deployment scripts use image tags derived from commits, check the new container, and keep the previous container available for rollback. Examples: [backend deployment](https://github.com/tr3ba/treba-backend/actions/runs/41083558386) and [frontend deployment](https://github.com/tr3ba/treba-frontend/actions/runs/41191308177).

## 🕓 Development history

From the first assignment in July to buyer order cancellation in November, these are the main steps. Choose a month for its PRs and context in the [full project history](docs/history/project-history.en.md).

<table width="100%">
<tr><td width="50%" align="center"><a href="docs/history/project-history.en.md#history-july"><img src="assets/history/july.en.svg" width="460" alt="July 2026: project foundation"></a></td><td width="50%" align="center"><a href="docs/history/project-history.en.md#history-august"><img src="assets/history/august.en.svg" width="460" alt="August 2026: containers and delivery"></a></td></tr>
<tr><td width="50%" align="center"><a href="docs/history/project-history.en.md#history-september"><img src="assets/history/september.en.svg" width="460" alt="September 2026: catalog and access"></a></td><td width="50%" align="center"><a href="docs/history/project-history.en.md#history-october"><img src="assets/history/october.en.svg" width="460" alt="October 2026: marketplace integration"></a></td></tr>
<tr><td colspan="2" align="center"><a href="docs/history/project-history.en.md#history-november"><img src="assets/history/november.en.svg" width="460" alt="November 2026: order cancellation"></a></td></tr>
</table>

[Full history](docs/history/project-history.en.md) · [Development log](docs/history/daily-log.en.md)

## 🛠️ Issues and fixes

The team worked through deployment and integration problems along the way: an EC2 disk filled with retained images, database migration checks that blocked deployment, OAuth table naming, and an admin page hidden by browser filters. The [issues and fixes page](docs/incidents/README.en.md) links each case to the relevant PR. It also separates deliberate CI failure demonstrations from actual deployment problems.

## 👥 Team

| Member | Main work | Example |
|---|---|---|
| [amonezeer](docs/team/README.en.md#author-amonezeer) | API, seller and admin tools, integration | [Seller tools and import](https://github.com/tr3ba/treba-backend/pull/64) |
| [F1eshka](docs/team/README.en.md#author-f1eshka) | Storefront and buyer experience | [Catalog pages](https://github.com/tr3ba/treba-frontend/pull/15) |
| [thewhitemage13](docs/team/README.en.md#author-thewhitemage13) | Catalog, cart, reviews | [Catalog API](https://github.com/tr3ba/treba-backend/pull/12) |
| [Quixar](docs/team/README.en.md#author-quixar) | Backend foundation, access, orders | [Architecture foundation](https://github.com/tr3ba/treba-backend/pull/1) |
| [Broadcast1Storm](docs/team/README.en.md#author-broadcast1storm) | Docker, CI/CD, AWS | [SSM delivery](https://github.com/tr3ba/treba-backend/pull/8) |

[Meet the team](docs/team/README.en.md)

## 📦 Repositories

[![Open Backend](https://img.shields.io/badge/OPEN_BACKEND-FF6E2A?style=for-the-badge&logo=github&logoColor=white)](https://github.com/tr3ba/treba-backend)
[![Open Frontend](https://img.shields.io/badge/OPEN_FRONTEND-002AFF?style=for-the-badge&logo=github&logoColor=white)](https://github.com/tr3ba/treba-frontend)
