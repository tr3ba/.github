<div align="center">

**🇬🇧 English** ·
[🇺🇦 Українська](https://github.com/tr3ba/.github/blob/main/profile/README.uk.md) ·
[🇷🇺 Русский](https://github.com/tr3ba/.github/blob/main/profile/README.ru.md)

<br><br>

# 🛒 Treba Marketplace

### Marketplace · Cloud Infrastructure · DevOps

A modern marketplace platform built with a strong focus on  
**cloud infrastructure, automation, security, monitoring and reliability**.

<br>

[![Live Demo](https://img.shields.io/badge/LIVE_DEMO-002AFF?style=for-the-badge&logo=googlechrome&logoColor=white)](http://52.209.28.30/)
[![Backend](https://img.shields.io/badge/BACKEND-FF6E2A?style=for-the-badge&logo=dotnet&logoColor=white)](https://github.com/tr3ba/treba-backend)
[![Frontend](https://img.shields.io/badge/FRONTEND-002AFF?style=for-the-badge&logo=nextdotjs&logoColor=white)](https://github.com/tr3ba/treba-frontend)

<br><br>

![.NET](https://img.shields.io/badge/.NET_8-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat-square&logo=amazonwebservices&logoColor=white)

</div>

---

## 👋 About Treba

**Treba** is a modern full-stack marketplace built as a team project.

The platform combines a **Next.js frontend**, an **ASP.NET Core backend** and a
**PostgreSQL database**, supported by a real AWS cloud environment.

The engineering side of Treba goes beyond application development. The project includes
containerized deployment, automated CI/CD, cloud infrastructure, monitoring,
database recovery, access control and infrastructure security.

<div align="center">

![Backend](https://img.shields.io/badge/Backend-Deployed-002AFF?style=flat-square)
![Frontend](https://img.shields.io/badge/Frontend-Deployed-002AFF?style=flat-square)
![Database](https://img.shields.io/badge/RDS-Connected-FF6E2A?style=flat-square)
![CI/CD](https://img.shields.io/badge/CI%2FCD-Active-002AFF?style=flat-square)
![Monitoring](https://img.shields.io/badge/Monitoring-Active-FF6E2A?style=flat-square)
![Backups](https://img.shields.io/badge/Backups-Enabled-002AFF?style=flat-square)

</div>

---

# 🧩 Core Technologies

<table>
<tr>

<td width="50%" valign="top" align="center">

<h2>🎨 Frontend</h2>

<p>
<img src="https://skillicons.dev/icons?i=nextjs,react,ts&theme=dark" height="55">
</p>

<br>

<strong>Next.js</strong><br>
<sub>Main frontend framework powering the Treba web interface.</sub>

<br><br>

<strong>React</strong><br>
<sub>Component-based architecture for the marketplace interface.</sub>

<br><br>

<strong>TypeScript</strong><br>
<sub>Typed frontend development for safer and more maintainable code.</sub>

<br><br>

</td>

<td width="50%" valign="top" align="center">

<h2>⚙️ Backend</h2>

<p>
<img src="https://skillicons.dev/icons?i=dotnet&theme=dark" height="55">
</p>

<br>

<strong>ASP.NET Core</strong><br>
<sub>Main backend framework used for the Treba API and application services.</sub>

<br><br>

<strong>.NET 8</strong><br>
<sub>Runtime and development platform for backend services.</sub>

<br><br>

<strong>Entity Framework Core</strong><br>
<sub>Database access, models and migrations for the backend.</sub>

<br><br>

</td>

</tr>
</table>

---

# 🗄️ Data Layer

<table>
<tr>

<td width="50%" align="center" valign="top">

<img src="https://skillicons.dev/icons?i=postgres&theme=dark" width="60">

### PostgreSQL

Primary relational database used by the marketplace backend.

</td>

<td width="50%" align="center" valign="top">

<img src="https://skillicons.dev/icons?i=aws&theme=dark" width="60">

### Amazon RDS

Managed AWS database environment hosting PostgreSQL.

</td>

</tr>
</table>

---

# ☁️ AWS & DevOps

<table>
<tr>

<td width="50%" valign="top" align="center">

## 🚀 Delivery & Runtime

<img src="https://skillicons.dev/icons?i=docker,githubactions,aws&theme=dark" height="52">

<br><br>

### Docker

Containerized packaging for backend and frontend services.

<br>

### GitHub Actions

Automated build, delivery and deployment workflows.

<br>

### Amazon ECR

Container registry storing Treba backend and frontend Docker images.

<br>

### Amazon EC2

Cloud server running the deployed application containers.

<br>

</td>

<td width="50%" valign="top" align="center">

## 🛡️ Operations & Infrastructure

<img src="https://skillicons.dev/icons?i=aws&theme=dark" height="52">

<br><br>

### AWS Systems Manager

Controlled remote deployment and command execution on EC2.

<br>

### Amazon CloudWatch

Infrastructure monitoring and alarms for EC2 and RDS.

<br>

### AWS IAM

Access control for automation, infrastructure and runtime services.

<br>

### AWS Secrets Manager

Controlled storage and access for runtime secrets and configuration.

<br>

</td>

</tr>
</table>

---

# 🏗️ System Architecture

```mermaid
flowchart LR

    USER["👤 User"]
    FRONT["Next.js<br/>Frontend"]
    API["ASP.NET Core<br/>Backend API"]
    DB["PostgreSQL<br/>Amazon RDS"]

    USER --> FRONT
    FRONT -->|API| API
    API -->|EF Core / Npgsql| DB

    style USER fill:#ffffff,color:#000000,stroke:#002AFF,stroke-width:2px
    style FRONT fill:#002AFF,color:#ffffff,stroke:#002AFF,stroke-width:2px
    style API fill:#FF6E2A,color:#ffffff,stroke:#FF6E2A,stroke-width:2px
    style DB fill:#ffffff,color:#000000,stroke:#002AFF,stroke-width:2px
```

Treba is separated into **frontend, backend and database layers**.

This makes it possible to deploy, monitor and diagnose each part of the system independently.

---

# 🚀 CI/CD Pipeline

```mermaid
flowchart LR

    DEV["Developer"]
    GH["GitHub"]
    ACTIONS["GitHub<br/>Actions"]
    DOCKER["Docker<br/>Build"]
    ECR["Amazon<br/>ECR"]
    SSM["AWS Systems<br/>Manager"]
    EC2["Amazon<br/>EC2"]

    DEV --> GH
    GH --> ACTIONS
    ACTIONS --> DOCKER
    DOCKER --> ECR
    ECR --> SSM
    SSM --> EC2

    style DEV fill:#ffffff,color:#000000,stroke:#002AFF,stroke-width:2px
    style GH fill:#ffffff,color:#000000,stroke:#002AFF,stroke-width:2px
    style ACTIONS fill:#002AFF,color:#ffffff,stroke:#002AFF,stroke-width:2px
    style DOCKER fill:#002AFF,color:#ffffff,stroke:#002AFF,stroke-width:2px
    style ECR fill:#FF6E2A,color:#ffffff,stroke:#FF6E2A,stroke-width:2px
    style SSM fill:#FF6E2A,color:#ffffff,stroke:#FF6E2A,stroke-width:2px
    style EC2 fill:#FF6E2A,color:#ffffff,stroke:#FF6E2A,stroke-width:2px
```

<div align="center">

**GitHub → GitHub Actions → Docker → Amazon ECR → AWS Systems Manager → Amazon EC2**

</div>

Treba uses an automated delivery process instead of manually copying application files
to the server.

Changes enter the pipeline through GitHub, Docker images are built and stored in
**Amazon ECR**, and deployment commands are executed on **Amazon EC2**
through **AWS Systems Manager**.

---

# 🕓 Development Journey

<table>

<tr>
<td width="22%" align="center">

### 🌱 July

**Foundation**

</td>

<td>

GitHub organization, repositories, branch structure and the first team workflow were created.

`GitHub` · `Branches` · `Pull Requests` · `Review`

</td>
</tr>

<tr>
<td width="22%" align="center">

### 🐳 August

**Containers**

</td>

<td>

The project moved toward reproducible containerized environments and automated workflows.

`Docker` · `Docker Compose` · `GitHub Actions` · `CI/CD`

</td>
</tr>

<tr>
<td width="22%" align="center">

### ☁️ September

**AWS**

</td>

<td>

Backend and frontend received separate cloud delivery paths and the application moved into AWS.

`ECR` · `EC2` · `RDS` · `Systems Manager`

</td>
</tr>

<tr>
<td width="22%" align="center">

### 🛡️ October

**Operations**

</td>

<td>

The focus expanded from deployment to monitoring, recovery,
infrastructure security and deeper testing.

`CloudWatch` · `IAM` · `Backups` · `Security`

</td>
</tr>

</table>

---

# 📊 Monitoring & Recovery

<table>

<tr>

<td align="center" width="33%">

### 📈 CloudWatch

**6 Infrastructure Alarms**

EC2 and RDS monitoring

</td>

<td align="center" width="33%">

### 💾 Automated Backups

**7-Day Retention**

Amazon RDS backups

</td>

<td align="center" width="33%">

### ⏱️ PITR

**Point-in-Time Recovery**

Database recovery support

</td>

</tr>

<tr>

<td align="center">

### 📸 Manual Snapshot

**Recovery Point**

RDS snapshot verified

</td>

<td align="center">

### 💰 AWS Budget

**Cost Monitoring**

Budget alerts configured

</td>

<td align="center">

### 🔐 IAM

**Scoped Permissions**

Controlled infrastructure access

</td>

</tr>

</table>

---

# 🔐 Security & Infrastructure

<table>

<tr>

<td width="50%" valign="top">

### 🛡️ Network Security

- RDS Security Groups
- EC2 → RDS controlled access
- World-open PostgreSQL rule removed
- Runtime listener verification
- Restricted database access

</td>

<td width="50%" valign="top">

### 🔑 Access & Secrets

- IAM roles
- Scoped AWS permissions
- AWS Secrets Manager
- Restricted runtime environment file
- GitHub branch protection

</td>

</tr>

<tr>

<td width="50%" valign="top">

### 🔄 Delivery Security

- Pull Request workflow
- Required review
- CI/CD checks
- ECR image history
- SSM-based deployment

</td>

<td width="50%" valign="top">

### 📡 Operations

- CloudWatch alarms
- Automated database backups
- Point-in-Time Recovery
- Manual snapshots
- Cost monitoring

</td>

</tr>

</table>

---

# 📦 Treba Repositories

<table>
<tr>

<td width="50%" align="center" valign="top">

<img src="https://skillicons.dev/icons?i=dotnet&theme=dark" width="70">

## ⚙️ Backend

**ASP.NET Core**

Backend API, application services and PostgreSQL database access.

<br><br>

[![Open Backend](https://img.shields.io/badge/OPEN_BACKEND-FF6E2A?style=for-the-badge&logo=github&logoColor=white)](https://github.com/tr3ba/treba-backend)

<br><br>

</td>

<td width="50%" align="center" valign="top">

<img src="https://skillicons.dev/icons?i=nextjs&theme=dark" width="70">

## 🎨 Frontend

**Next.js**

Marketplace interface and frontend deployment workflow.

<br><br>

[![Open Frontend](https://img.shields.io/badge/OPEN_FRONTEND-002AFF?style=for-the-badge&logo=github&logoColor=white)](https://github.com/tr3ba/treba-frontend)

<br><br>

</td>

</tr>
</table>

---

<div align="center">

# Treba Marketplace

### Build · Automate · Deploy · Monitor · Improve

<br>

[![Open Treba](https://img.shields.io/badge/OPEN_TREBA-002AFF?style=for-the-badge&logo=googlechrome&logoColor=white)](http://52.209.28.30/)

<br><br>

**Treba © 2026**

</div>
