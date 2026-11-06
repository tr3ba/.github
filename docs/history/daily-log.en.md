<div align="center">

# Treba development log

### Selected days from July to November 2026

[Українська](daily-log.md) · **English**

[Home](../../README.en.md) · [Project history](project-history.en.md) · [Team](../team/README.en.md)

</div>

These are the days when a major part of the project changed. Each entry links to the corresponding PR or commit.

[**July**](#daily-july) · [**August**](#daily-august) · [**September**](#daily-september) · [**October**](#daily-october) · [**November**](#daily-november)

<a id="daily-july"></a>
## July: starting out

| Date | Change |
|---|---|
| **18 July** | The team received the online store assignment and supplied design. |
| **20 July** | Separate [backend](https://github.com/tr3ba/treba-backend/commit/a44ad6dca4be32cb07806f94cc4e55807950c459) and [frontend](https://github.com/tr3ba/treba-frontend/commit/e75d570a8240d7a05ed8c0f7b1523e530ca3a035) repositories were created. |
| **25-26 July** | [Backend PR #1](https://github.com/tr3ba/treba-backend/pull/1) laid down the architecture and first domain entities. |

<a id="daily-august"></a>
## August: Docker and the first delivery path

| Date | Change |
|---|---|
| **3 August** | Work began on the [administrative panel](https://github.com/tr3ba/treba-backend/pull/2). |
| **8 August** | The team opened the [backend Dockerfile PR](https://github.com/tr3ba/treba-backend/pull/3). |
| **22 August** | [Users and database access](https://github.com/tr3ba/treba-backend/pull/5) were connected. |
| **30-31 August** | [ECR publishing](https://github.com/tr3ba/treba-backend/pull/6), [backend deployment with SSM](https://github.com/tr3ba/treba-backend/pull/8), and [frontend delivery](https://github.com/tr3ba/treba-frontend/pull/7) were added. |

<a id="daily-september"></a>
## September: catalog and access

| Date | Change |
|---|---|
| **13 September** | [Catalog storage and API](https://github.com/tr3ba/treba-backend/pull/12) arrived, with [dependency checks](https://github.com/tr3ba/treba-backend/pull/14) in CI. |
| **17 September** | The admin panel gained a [user list and detail view](https://github.com/tr3ba/treba-backend/pull/20). |
| **18 September** | The [catalog API](https://github.com/tr3ba/treba-backend/pull/24) grew to cover categories, brands, attributes, variants, and photos. |
| **19 September** | [User authentication](https://github.com/tr3ba/treba-backend/pull/31) was merged. |

<a id="daily-october"></a>
## October: marketplace flows

| Date | Change |
|---|---|
| **2 October** | The backend gained [sellers and stores](https://github.com/tr3ba/treba-backend/pull/37) and a [cart](https://github.com/tr3ba/treba-backend/pull/38). |
| **7-8 October** | The frontend added its [API layer and catalog pages](https://github.com/tr3ba/treba-frontend/pull/15). |
| **14 October** | [Orders](https://github.com/tr3ba/treba-backend/pull/55) were added. |
| **20-21 October** | The team developed [seller tools](https://github.com/tr3ba/treba-backend/pull/64), [support conversations](https://github.com/tr3ba/treba-backend/pull/66), and [checkout through the API](https://github.com/tr3ba/treba-frontend/pull/32). |
| **22 October** | [Seller applications in the backend](https://github.com/tr3ba/treba-backend/pull/80) were connected to the [frontend](https://github.com/tr3ba/treba-frontend/pull/36). |
| **26 October** | [Nova Poshta and courier delivery](https://github.com/tr3ba/treba-backend/pull/86) reached [checkout](https://github.com/tr3ba/treba-frontend/pull/42). |
| **28 October** | [Google/Facebook sign-in](https://github.com/tr3ba/treba-backend/pull/91) was completed across the [frontend](https://github.com/tr3ba/treba-frontend/pull/45). |
| **29 October** | The [admin workspace moved into Next.js](https://github.com/tr3ba/treba-frontend/pull/50), replacing the [old backend UI](https://github.com/tr3ba/treba-backend/pull/96). |
| **31 October** | [Admin filters and user details](https://github.com/tr3ba/treba-frontend/pull/54) were refined. |

<a id="daily-november"></a>
## November: orders

| Date | Change |
|---|---|
| **5 November** | The buyer gained [order cancellation](https://github.com/tr3ba/treba-frontend/pull/56) from the order page. |

[More context in the project history](project-history.en.md) · [Issues and fixes](../incidents/README.en.md)
