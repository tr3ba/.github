<div align="center">

# Treba project history

### From the first assignment to the marketplace

**18 July - 5 November 2026** · GitHub dates use UTC

[Українська](project-history.md) · **English**

[Home](../../README.en.md) · [Development log](daily-log.en.md) · [Team](../team/README.en.md) · [Issues and fixes](../incidents/README.en.md)

![Backend commits](https://img.shields.io/badge/BACKEND-256_commits-FF6E2A?style=flat-square)
![Frontend commits](https://img.shields.io/badge/FRONTEND-187_commits-002AFF?style=flat-square)
![Profile commits](https://img.shields.io/badge/PROFILE-21_commits-002AFF?style=flat-square)
![Merged PRs](https://img.shields.io/badge/MERGED_PRs-151-8755C8?style=flat-square)

</div>

Treba began as a student team assignment on 18 July 2026. The brief was to build an online store based on a supplied design. The team created separate [backend](https://github.com/tr3ba/treba-backend/commit/a44ad6dca4be32cb07806f94cc4e55807950c459) and [frontend](https://github.com/tr3ba/treba-frontend/commit/e75d570a8240d7a05ed8c0f7b1523e530ca3a035) repositories on 20 July. The original working name, “Rozetta,” came from the Rozetka-inspired assignment.

The sections below follow the changes that shaped the project. Each month links to the PRs behind the main milestones.

[![July](https://img.shields.io/badge/07_JULY-FOUNDATION-7494FF?style=for-the-badge)](#history-july)
[![August](https://img.shields.io/badge/08_AUGUST-DELIVERY-ED7100?style=for-the-badge)](#history-august)
[![September](https://img.shields.io/badge/09_SEPTEMBER-CATALOG-2EA985?style=for-the-badge)](#history-september)
[![October](https://img.shields.io/badge/10_OCTOBER-MARKETPLACE-8755C8?style=for-the-badge)](#history-october)
[![November](https://img.shields.io/badge/11_NOVEMBER-ORDERS-378A96?style=for-the-badge)](#history-november)

<a id="history-july"></a>
## July: the foundation

On 18 July, the students were divided into teams and given the store assignment and design. Two days later the backend and frontend repositories received their initial commits.

[Backend PR #1](https://github.com/tr3ba/treba-backend/pull/1), opened on 25 July and merged on 26 July, introduced the first Clean Architecture structure and domain entities. It established the base on which catalog, account, and order work was built.

<a id="history-august"></a>
## August: data, containers, and delivery

The first [administrative panel](https://github.com/tr3ba/treba-backend/pull/2) started in early August. [Backend Docker work](https://github.com/tr3ba/treba-backend/pull/3), [users and database integration](https://github.com/tr3ba/treba-backend/pull/5), and build workflows followed.

At the end of the month, the team added [ECR image publishing](https://github.com/tr3ba/treba-backend/pull/6), [backend deployment through Systems Manager](https://github.com/tr3ba/treba-backend/pull/8), and the [frontend delivery path](https://github.com/tr3ba/treba-frontend/pull/7). Docker Compose helped bring the application together for local development.

<a id="history-september"></a>
## September: catalog and access

The delivery configuration moved to a [new AWS account](https://github.com/tr3ba/treba-backend/pull/10). The team also cleaned tracked build artifacts from the repository in [backend PR #11](https://github.com/tr3ba/treba-backend/pull/11).

[Catalog persistence and APIs](https://github.com/tr3ba/treba-backend/pull/12) appeared alongside tests and CI checks. Work on [categories, brands, attributes, variants, and product photos](https://github.com/tr3ba/treba-backend/pull/24) expanded the data model. [User authentication](https://github.com/tr3ba/treba-backend/pull/31) was merged on 19 September.

Some CI failures in this period were deliberate demonstrations, including [backend PR #18](https://github.com/tr3ba/treba-backend/pull/18). They are described separately from deployment problems on the [issues and fixes page](../incidents/README.en.md).

<a id="history-october"></a>
## October: a working marketplace takes shape

October brought together features that had previously been developed in parallel.

| Period | Main changes |
|---|---|
| **2-8 October** | [Sellers and stores](https://github.com/tr3ba/treba-backend/pull/37), the [backend cart](https://github.com/tr3ba/treba-backend/pull/38), and [frontend catalog pages connected to the API](https://github.com/tr3ba/treba-frontend/pull/15). |
| **9-15 October** | Integration work, [local Kubernetes Stage 5 materials](https://github.com/tr3ba/treba-backend/pull/52), [wishlists](https://github.com/tr3ba/treba-backend/pull/53), [reviews](https://github.com/tr3ba/treba-backend/pull/54), and [orders](https://github.com/tr3ba/treba-backend/pull/55). The Kubernetes work remained a separate local track; EC2 continued to host the deployment path. |
| **19-25 October** | [Seller import tools](https://github.com/tr3ba/treba-backend/pull/64), [support conversations](https://github.com/tr3ba/treba-backend/pull/66), [frontend checkout through the API](https://github.com/tr3ba/treba-frontend/pull/32), [seller applications](https://github.com/tr3ba/treba-backend/pull/80), and [header and comparison controls](https://github.com/tr3ba/treba-frontend/pull/40). |
| **26-31 October** | [Nova Poshta and courier options](https://github.com/tr3ba/treba-backend/pull/86), [Google/Facebook sign-in](https://github.com/tr3ba/treba-backend/pull/91), [registration verification](https://github.com/tr3ba/treba-backend/pull/94), and [the move of the admin workspace into Next.js](https://github.com/tr3ba/treba-frontend/pull/50). |

The frontend's [product mock data was removed from the API layer](https://github.com/tr3ba/treba-frontend/pull/31) on 21 October. Authenticated cart and checkout flows then used the backend API. Guest cart state remained in the browser until sign-in.

The delivery path needed several repairs as these features came together. The [EC2 disk issue](https://github.com/tr3ba/treba-frontend/pull/37), [migration allowlist fix](https://github.com/tr3ba/treba-backend/pull/84), and [OAuth deployment fix](https://github.com/tr3ba/treba-backend/pull/91) are explained on the [issues and fixes page](../incidents/README.en.md).

<a id="history-november"></a>
## November: buyer order cancellation

On 5 November, [frontend PR #56](https://github.com/tr3ba/treba-frontend/pull/56) added cancellation from the buyer's order page. The action is available for eligible order statuses, sends the selected reason to the API, and updates the displayed status after the response.

## How the parts came together

| Area | Development path |
|---|---|
| **Catalog** | [Backend API](https://github.com/tr3ba/treba-backend/pull/12) → [frontend API layer](https://github.com/tr3ba/treba-frontend/pull/15) → [removal of product mocks](https://github.com/tr3ba/treba-frontend/pull/31). |
| **Shopping** | [Backend cart](https://github.com/tr3ba/treba-backend/pull/38) → [checkout integration](https://github.com/tr3ba/treba-frontend/pull/32) → [delivery choices](https://github.com/tr3ba/treba-backend/pull/86) → [buyer cancellation](https://github.com/tr3ba/treba-frontend/pull/56). |
| **Administration** | [Early panel](https://github.com/tr3ba/treba-backend/pull/2) → [frontend admin workspace](https://github.com/tr3ba/treba-frontend/pull/50) → [retirement of the backend UI](https://github.com/tr3ba/treba-backend/pull/96). |
| **Delivery** | [Docker](https://github.com/tr3ba/treba-backend/pull/3) → [ECR and EC2](https://github.com/tr3ba/treba-backend/pull/8) → [Systems Manager updates](https://github.com/tr3ba/treba-backend/pull/10). |

[Development log](daily-log.en.md) · [Team](../team/README.en.md) · [Back to the overview](../../README.en.md)
