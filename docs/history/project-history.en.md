<div align="center">

# Treba project history

### From the first assignment to the marketplace

**18 July - 14 November 2026** · Earlier GitHub dates use UTC; server entries for 11–14 November use Europe/Kyiv. Commit and PR counters below retain the 5 November snapshot.

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

<a id="history-devops-november"></a>

### 11–14 November: server protection, recovery, and CI

Dates in this subsection use Europe/Kyiv. Server results come from checks executed through Termius; PR links establish repository changes.

**11 November — private routing.** Caddy took ports 80/443. Frontend and backend moved to Docker networks without publishing application ports. Deployment scripts preserve the networks and the previous container for rollback; backend changes were merged on 13 November in [#103](https://github.com/tr3ba/treba-backend/pull/103).

**12 November — off-host backups.** Separate encrypted restic repositories on Google Drive were configured for the TREBA database with local uploads and for selected server configuration. An isolated PostgreSQL restore passed with 71 tables. File recovery and a complete EC2 rebuild remain separate acceptance checks.

**13 November — reboot verification and maintenance.** The host booted kernel 7.0.0-1017-aws. Private routes, HTTPS, and frontend metadata denial passed after reboot and after a controlled frontend release. Rclone was updated to 1.76.0 and GitHub CLI to 2.104.0. After archiving 45 historical images, cleanup recovered 10.93 GiB while retaining running containers and volumes.

Our backup script's deployment fingerprint was corrected for Docker returning the same mounts in a different order. The complete server backup, file restore verification, and OS update chain passed. The final schedule is daily data backups at 03:00 and Thursday configuration backups at 04:00, with automatic reboot disabled.

**14 November — backend image and CI.** Following the [glibc Dockerfile fix in #107](https://github.com/tr3ba/treba-backend/pull/107), the verified linux/amd64 image completed ECR Basic scanning with no OS package findings. This does not establish application-wide security. New backend migrations passed on a restored database copy, including compatibility with the previous backend; the production database was not modified.

On 13 November, image publishing moved to separate OIDC roles in [backend #104](https://github.com/tr3ba/treba-backend/pull/104) and [frontend #62](https://github.com/tr3ba/treba-frontend/pull/62). [Backend #108](https://github.com/tr3ba/treba-backend/pull/108) and [frontend #63](https://github.com/tr3ba/treba-frontend/pull/63) pin actions to full SHAs, move them to Node.js 24, and add dependency audits that block HIGH/CRITICAL advisories. [Backend CI](https://github.com/tr3ba/treba-backend/actions/runs/43575140496) and [Frontend Checks](https://github.com/tr3ba/treba-frontend/actions/runs/43575146561) passed. [PR #109](https://github.com/tr3ba/treba-backend/pull/109) adds the [backup and recovery guide, Ukrainian](https://github.com/tr3ba/treba-backend/blob/main/docs/backup-and-recovery.md).

On 14 November, GitHub recorded successful [Deploy Backend](https://github.com/tr3ba/treba-backend/actions/runs/43580432609) and [Deploy Frontend](https://github.com/tr3ba/treba-frontend/actions/runs/43580590690) runs. Both workflows are active again and automatically follow successful image publishing from `main`.

**Remaining acceptance work.** Separate EC2 acceptance of the latest releases is not established by the recorded server checks above. A complete EC2 rebuild, removal of the old AWS key from all workflows, and durable backup OAuth authorization remain unconfirmed. A prepared private S3 bucket and 172 verified photos do not establish integration in the deployed backend. Shared Next.js and Caddy request-size protection also needs a coordinated release.

## How the parts came together

| Area | Development path |
|---|---|
| **Catalog** | [Backend API](https://github.com/tr3ba/treba-backend/pull/12) → [frontend API layer](https://github.com/tr3ba/treba-frontend/pull/15) → [removal of product mocks](https://github.com/tr3ba/treba-frontend/pull/31). |
| **Shopping** | [Backend cart](https://github.com/tr3ba/treba-backend/pull/38) → [checkout integration](https://github.com/tr3ba/treba-frontend/pull/32) → [delivery choices](https://github.com/tr3ba/treba-backend/pull/86) → [buyer cancellation](https://github.com/tr3ba/treba-frontend/pull/56). |
| **Administration** | [Early panel](https://github.com/tr3ba/treba-backend/pull/2) → [frontend admin workspace](https://github.com/tr3ba/treba-frontend/pull/50) → [retirement of the backend UI](https://github.com/tr3ba/treba-backend/pull/96). |
| **Delivery** | [Docker](https://github.com/tr3ba/treba-backend/pull/3) → [ECR and EC2](https://github.com/tr3ba/treba-backend/pull/8) → [Systems Manager updates](https://github.com/tr3ba/treba-backend/pull/10). |

[Development log](daily-log.en.md) · [Team](../team/README.en.md) · [Back to the overview](../../README.en.md)
