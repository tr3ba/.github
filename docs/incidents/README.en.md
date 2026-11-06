<div align="center">

# Treba issues and fixes

### Problems the team met while building and delivering the project

[Українська](README.md) · **English**

![Case studies](https://img.shields.io/badge/CASE_STUDIES-6-002AFF?style=for-the-badge) ![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub_Actions-FF6E2A?style=for-the-badge&logo=githubactions)

[Home](../../README.en.md) · [History](../history/project-history.en.md) · [Team](../team/README.en.md) · [Resolved vulnerabilities](../security/resolved-vulnerabilities.en.md)

</div>

CI failures, deployment checks, database migrations, and even browser filters all caused problems during development. These six cases show what happened and which changes addressed them. A failed GitHub Actions run does not, by itself, show that the live service was down.

| When (UTC) | Case | Area |
|---|---|---|
| **16-18 September** | [Deliberate CI failure](#case-ci-demo) | Tests |
| **22 October** | [EC2 disk space](#case-ec2-disk) | Deployment |
| **23-24 October** | [Migration allowlist](#case-migration-allowlist) | Database |
| **27-28 October** | [UserExternalLogins table name](#case-external-logins) | Database |
| **29 October** | [Migration test scope](#case-migration-tests) | Tests |
| **29 October** | [Hidden admin workspace](#case-cosmetic-filters) | Frontend |

<a id="case-ci-demo"></a>
<details>
<summary><strong>16-18 September · Deliberate CI failure</strong></summary>

[Backend PR #18](https://github.com/tr3ba/treba-backend/pull/18) includes a failing test followed by its fix. [PR #22](https://github.com/tr3ba/treba-backend/pull/22) was closed without merging. These were controlled demonstrations of CI checks, not production outages.

</details>

<a id="case-ec2-disk"></a>
<details>
<summary><strong>22 October · EC2 disk space</strong></summary>

The team described an EC2 disk at 99% usage in [frontend PR #37](https://github.com/tr3ba/treba-frontend/pull/37). Old rollback containers retained Docker images and left too little space for another deployment. The PR describes cleanup to make room. [Failed run](https://github.com/tr3ba/treba-frontend/actions/runs/39756631924).

</details>

<a id="case-migration-allowlist"></a>
<details>
<summary><strong>23-24 October · Migration allowlist</strong></summary>

Deployment stopped before switching containers because the profile-language migration was absent from the operational allowlist. [Backend PR #84](https://github.com/tr3ba/treba-backend/pull/84) updated the allowlist and added tests. [Failed run](https://github.com/tr3ba/treba-backend/actions/runs/39964848356).

</details>

<a id="case-external-logins"></a>
<details>
<summary><strong>27-28 October · UserExternalLogins table name</strong></summary>

A deployment check looked for <code>public.user_external_logins</code>, while the migration created <code>public."UserExternalLogins"</code>. [Backend PR #91](https://github.com/tr3ba/treba-backend/pull/91) took the table name from EF Core metadata and quoted it correctly in the SQL check. [Failed run](https://github.com/tr3ba/treba-backend/actions/runs/40589126102).

</details>

<a id="case-migration-tests"></a>
<details>
<summary><strong>29 October · Migration test scope</strong></summary>

A delivery test called <code>MigrateAsync</code> without a target migration, applying newer registration changes to a minimal test schema. [Backend PR #95](https://github.com/tr3ba/treba-backend/pull/95) limited the delivery test and added a separate PostgreSQL test for registration verification. [Related failed run](https://github.com/tr3ba/treba-backend/actions/runs/40899897467).

</details>

<a id="case-cosmetic-filters"></a>
<details>
<summary><strong>29 October · Hidden admin workspace</strong></summary>

Browser cosmetic filters hid CSS classes named <code>.ad-sidebar</code> and <code>.ad-main</code>. The page could appear empty without a JavaScript error. [Frontend PR #51](https://github.com/tr3ba/treba-frontend/pull/51) renamed the classes and added a stable workspace marker; [backend PR #97](https://github.com/tr3ba/treba-backend/pull/97) aligned the deployment preflight check.

</details>

## Failed Actions runs

Through 31 October, GitHub Actions recorded **42 failed runs**: 30 backend and 12 frontend. The list below is useful for finding a run; a failure result alone does not establish the cause or user impact.

<details>
<summary><strong>Show all 42 runs</strong></summary>

| UTC | Repository | Workflow | Run | Title |
|---|---|---|---|---|
| 2026-08-30T16:23:55Z | treba-backend | Deploy Backend to EC2 | [33322340169](https://github.com/tr3ba/treba-backend/actions/runs/33322340169) | Deploy Backend to EC2 |
| 2026-09-16T20:51:40Z | treba-backend | Backend Build | [35149052911](https://github.com/tr3ba/treba-backend/actions/runs/35149052911) | test: demonstrate CI failure |
| 2026-09-18T16:37:18Z | treba-backend | Backend Build | [35369554182](https://github.com/tr3ba/treba-backend/actions/runs/35369554182) | test: demonstrate failing CI |
| 2026-09-19T07:18:29Z | treba-backend | Docker Build and Push to ECR | [35428963685](https://github.com/tr3ba/treba-backend/actions/runs/35428963685) | Merge pull request #31 from tr3ba/feat/user-auth |
| 2026-09-19T07:44:35Z | treba-backend | Docker Build and Push to ECR | [35430146627](https://github.com/tr3ba/treba-backend/actions/runs/35430146627) | Merge pull request #32 from tr3ba/Broadcast1Storm-patch-1 |
| 2026-09-19T07:56:51Z | treba-backend | Docker Build and Push to ECR | [35430680167](https://github.com/tr3ba/treba-backend/actions/runs/35430680167) | Merge pull request #33 from tr3ba/Broadcast1Storm-patch-2 |
| 2026-09-19T08:47:07Z | treba-backend | Docker Build and Push to ECR | [35432934335](https://github.com/tr3ba/treba-backend/actions/runs/35432934335) | Merge pull request #34 from tr3ba/Broadcast1Storm-patch-3 |
| 2026-09-19T08:51:24Z | treba-backend | Deploy Backend to EC2 | [35433127480](https://github.com/tr3ba/treba-backend/actions/runs/35433127480) | Deploy Backend to EC2 |
| 2026-10-04T12:15:54Z | treba-backend | Docker Build and Push to ECR | [37201505395](https://github.com/tr3ba/treba-backend/actions/runs/37201505395) | Merge pull request #40 from tr3ba/feat/add-new-api |
| 2026-10-19T14:04:39Z | treba-backend | Backend Build | [39265687730](https://github.com/tr3ba/treba-backend/actions/runs/39265687730) | feat: add admin workspace and Telegram Mini App |
| 2026-10-19T14:17:44Z | treba-backend | Deploy Backend to EC2 | [39267654450](https://github.com/tr3ba/treba-backend/actions/runs/39267654450) | Deploy Backend to EC2 |
| 2026-10-19T14:27:16Z | treba-backend | Deploy Backend to EC2 | [39269078764](https://github.com/tr3ba/treba-backend/actions/runs/39269078764) | Deploy Backend to EC2 |
| 2026-10-19T20:58:47Z | treba-backend | Backend Build | [39323788046](https://github.com/tr3ba/treba-backend/actions/runs/39323788046) | Feature/promotions |
| 2026-10-19T21:08:41Z | treba-backend | Backend Build | [39325147212](https://github.com/tr3ba/treba-backend/actions/runs/39325147212) | Feature/promotions |
| 2026-10-21T16:48:34Z | treba-backend | Backend Build | [39638094309](https://github.com/tr3ba/treba-backend/actions/runs/39638094309) | feat: added payment |
| 2026-10-21T16:48:58Z | treba-backend | Docker Build and Push to ECR | [39638150499](https://github.com/tr3ba/treba-backend/actions/runs/39638150499) | Merge pull request #57 from tr3ba/feat/add-payment |
| 2026-10-21T16:48:58Z | treba-backend | Backend Build | [39638150504](https://github.com/tr3ba/treba-backend/actions/runs/39638150504) | Merge pull request #57 from tr3ba/feat/add-payment |
| 2026-10-21T16:55:51Z | treba-backend | Backend Build | [39639187702](https://github.com/tr3ba/treba-backend/actions/runs/39639187702) | fix: fixed bug after conflict resolving |
| 2026-10-21T16:56:01Z | treba-backend | Docker Build and Push to ECR | [39639213585](https://github.com/tr3ba/treba-backend/actions/runs/39639213585) | Merge pull request #77 from tr3ba/fix/conflict-resolve-bug |
| 2026-10-21T16:56:01Z | treba-backend | Backend Build | [39639213764](https://github.com/tr3ba/treba-backend/actions/runs/39639213764) | Merge pull request #77 from tr3ba/fix/conflict-resolve-bug |
| 2026-10-21T20:01:37Z | treba-backend | Backend Build | [39666708704](https://github.com/tr3ba/treba-backend/actions/runs/39666708704) | Feature/delivery |
| 2026-10-23T13:52:39Z | treba-backend | Deploy Backend to EC2 | [39964848356](https://github.com/tr3ba/treba-backend/actions/runs/39964848356) | Deploy Backend to EC2 |
| 2026-10-26T17:42:43Z | treba-backend | Backend Build | [40371167877](https://github.com/tr3ba/treba-backend/actions/runs/40371167877) | feat: added google and facebook reg |
| 2026-10-26T17:42:57Z | treba-backend | Backend Build | [40371202808](https://github.com/tr3ba/treba-backend/actions/runs/40371202808) | Merge pull request #87 from tr3ba/feat/google&facebook-auth |
| 2026-10-26T17:42:57Z | treba-backend | Docker Build and Push to ECR | [40371202862](https://github.com/tr3ba/treba-backend/actions/runs/40371202862) | Merge pull request #87 from tr3ba/feat/google&facebook-auth |
| 2026-10-27T21:29:07Z | treba-backend | Backend Build | [40587166646](https://github.com/tr3ba/treba-backend/actions/runs/40587166646) | Feat/google&facebook auth |
| 2026-10-27T21:29:24Z | treba-backend | Docker Build and Push to ECR | [40587204575](https://github.com/tr3ba/treba-backend/actions/runs/40587204575) | Merge pull request #89 from tr3ba/feat/google&facebook-auth |
| 2026-10-27T21:29:24Z | treba-backend | Backend Build | [40587204578](https://github.com/tr3ba/treba-backend/actions/runs/40587204578) | Merge pull request #89 from tr3ba/feat/google&facebook-auth |
| 2026-10-27T21:43:19Z | treba-backend | Deploy Backend to EC2 | [40589126102](https://github.com/tr3ba/treba-backend/actions/runs/40589126102) | Deploy Backend to EC2 |
| 2026-10-29T15:16:35Z | treba-backend | Deploy Backend to EC2 | [40899897467](https://github.com/tr3ba/treba-backend/actions/runs/40899897467) | Deploy Backend to EC2 |
| 2026-08-31T17:29:42Z | treba-frontend | Deploy Frontend to EC2 | [33419859722](https://github.com/tr3ba/treba-frontend/actions/runs/33419859722) | Deploy Frontend to EC2 |
| 2026-10-07T14:12:48Z | treba-frontend | Frontend Docker Build and Push to ECR | [37634809686](https://github.com/tr3ba/treba-frontend/actions/runs/37634809686) | Frontend Docker Build and Push to ECR |
| 2026-10-07T14:24:34Z | treba-frontend | Frontend Docker Build and Push to ECR | [37636437332](https://github.com/tr3ba/treba-frontend/actions/runs/37636437332) | Frontend Docker Build and Push to ECR |
| 2026-10-07T14:30:52Z | treba-frontend | Frontend Docker Build and Push to ECR | [37637323018](https://github.com/tr3ba/treba-frontend/actions/runs/37637323018) | Frontend Docker Build and Push to ECR |
| 2026-10-07T14:35:11Z | treba-frontend | Frontend Docker Build and Push to ECR | [37637930055](https://github.com/tr3ba/treba-frontend/actions/runs/37637930055) | Frontend Docker Build and Push to ECR |
| 2026-10-08T12:38:52Z | treba-frontend | Frontend Docker Build and Push to ECR | [37778362588](https://github.com/tr3ba/treba-frontend/actions/runs/37778362588) | Frontend Docker Build and Push to ECR |
| 2026-10-20T15:12:47Z | treba-frontend | Frontend Docker Build and Push to ECR | [39446318836](https://github.com/tr3ba/treba-frontend/actions/runs/39446318836) | Merge pull request #28 from tr3ba/feat/support-roles-and-login |
| 2026-10-20T15:14:36Z | treba-frontend | Deploy Frontend to EC2 | [39446596133](https://github.com/tr3ba/treba-frontend/actions/runs/39446596133) | Deploy Frontend to EC2 |
| 2026-10-20T15:46:00Z | treba-frontend | Deploy Frontend to EC2 | [39451431744](https://github.com/tr3ba/treba-frontend/actions/runs/39451431744) | Deploy Frontend to EC2 |
| 2026-10-20T18:06:13Z | treba-frontend | Frontend Docker Build and Push to ECR | [39471827705](https://github.com/tr3ba/treba-frontend/actions/runs/39471827705) | Merge pull request #30 from tr3ba/feat/fix-public-admin-entry |
| 2026-10-22T09:35:41Z | treba-frontend | Deploy Frontend to EC2 | [39756631924](https://github.com/tr3ba/treba-frontend/actions/runs/39756631924) | Deploy Frontend to EC2 |
| 2026-10-30T15:42:13Z | treba-frontend | Frontend Checks | [41083136581](https://github.com/tr3ba/treba-frontend/actions/runs/41083136581) | feat: improve admin filters and user details |

</details>

[Project history](../history/project-history.en.md) · [Back to the overview](../../README.en.md)
