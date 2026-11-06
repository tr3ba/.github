<div align="center">

# Помилки та виправлення TREBA

### Як команда знаходила й виправляла проблеми

[English](README.en.md) · **Українська**

![Розбори](https://img.shields.io/badge/РОЗБОРИ-6-002AFF?style=for-the-badge) ![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub_Actions-FF6E2A?style=for-the-badge&logo=githubactions)

[Головна](../../README.uk.md) · [Історія](../history/project-history.md) · [Команда](../team/README.md) · [Виправлені вразливості](../security/resolved-vulnerabilities.md)

</div>

Під час розробки команда стикалася зі збоями CI, труднощами розгортання, міграціями бази даних та помилками інтерфейсу. Нижче шість конкретних випадків і зміни, які допомогли їх розв’язати. Невдалий запуск Actions не завжди означає збій самого сервісу.

## Карта розборів

| Період UTC | Випадок | Категорія |
|---|---|---|
| 16-18.09 | [Навмисний збій CI](#case-ci-demo) | Демонстрація CI |
| 22.10 | [Нестача місця на EC2](#case-ec2-disk) | Розгортання |
| 23-24.10 | [Allowlist міграції](#case-migration-allowlist) | Міграції |
| 27-28.10 | [Назва UserExternalLogins](#case-external-logins) | База даних |
| 29.10 | [Межі тестів міграцій](#case-migration-tests) | Тести |
| 29.10 | [Порожній адміністративний UI](#case-cosmetic-filters) | Інтерфейс |

Наприкінці сторінки є згорнутий журнал невдалих запусків Actions.

<a id="case-ci-demo"></a>

<details>
<summary><strong>16-18.09 · Навмисний збій CI</strong></summary>

**Що сталося**

Це навчальні демонстрації перевірок, а не встановлені аварії production.

**Що змінили**

У backend #18 є коміт демонстрації failure та наступне виправлення; PR #22 закритий без злиття.

**Посилання:** [BE #18](https://github.com/tr3ba/treba-backend/pull/18), [BE #22](https://github.com/tr3ba/treba-backend/pull/22).

**Що врахували:** Не змішувати контрольовані негативні тести з експлуатаційними інцидентами.

</details>

<a id="case-ec2-disk"></a>

<details>
<summary><strong>22.10 · Нестача місця на EC2</strong></summary>

**Що сталося**

У [frontend PR #37](https://github.com/tr3ba/treba-frontend/pull/37) команда описала диск EC2, заповнений на 99%: старі rollback-контейнери утримували образи.

**Що змінили**

У PR описано звільнення місця для нового розгортання.

**Посилання:** [FE #37](https://github.com/tr3ba/treba-frontend/pull/37), [failure run](https://github.com/tr3ba/treba-frontend/actions/runs/39756631924).

**Що врахували:** Політика зберігання rollback-контейнерів впливає на використання диска; перевірка потребує журналів і стану хоста.

</details>

<a id="case-migration-allowlist"></a>

<details>
<summary><strong>23-24.10 · Allowlist міграції</strong></summary>

**Що сталося**

За backend PR #84 deployment зупинився до переключення контейнерів: міграції мов профілю не було в дозволеному переліку.

**Що змінили**

У PR узгодили allowlist із міграцією та додали тести. PR відкрили 23 жовтня, зміни злили 24 жовтня.

**Посилання:** [BE #84](https://github.com/tr3ba/treba-backend/pull/84), [failure run](https://github.com/tr3ba/treba-backend/actions/runs/39964848356).

**Що врахували:** Перелік дозволених операційних міграцій має змінюватися разом із відповідною схемою та тестами.

</details>

<a id="case-external-logins"></a>

<details>
<summary><strong>27-28.10 · Назва UserExternalLogins</strong></summary>

**Що сталося**

Під час розгортання перевірка зверталася до `public.user_external_logins` замість `public."UserExternalLogins"`, що описано в backend #91.

**Що змінили**

Назву таблиці почали брати з метаданих EF Core й коректно екранувати для SQL-перевірки.

**Посилання:** [BE #91](https://github.com/tr3ba/treba-backend/pull/91), [failure run](https://github.com/tr3ba/treba-backend/actions/runs/40589126102).

**Що врахували:** Операційні перевірки мають використовувати ті самі ідентифікатори таблиць, що й міграції/ORM.

</details>

<a id="case-migration-tests"></a>

<details>
<summary><strong>29.10 · Межі тестів міграцій</strong></summary>

**Що сталося**

У backend #95 delivery-тест викликав `MigrateAsync` без цільової міграції. Через це нова міграція реєстрації потрапляла в мінімальну схему без потрібних таблиць.

**Що змінили**

Тест доставки обмежили міграцією AddManagedShipmentLifecycle. Для AddRegistrationVerification додали окремий тест із PostgreSQL. Посилання на невдалий запуск показує часовий контекст, але його точну причину встановлює лише job log.

**Посилання:** [BE #95](https://github.com/tr3ba/treba-backend/pull/95), [failure run](https://github.com/tr3ba/treba-backend/actions/runs/40899897467).

**Що врахували:** Тест окремої міграції не повинен неявно застосовувати всі подальші зміни схеми.

</details>

<a id="case-cosmetic-filters"></a>

<details>
<summary><strong>29.10 · Порожній адміністративний UI</strong></summary>

**Що сталося**

У frontend #51 виявили, що косметичні правила блокувальника приховували `.ad-sidebar` та `.ad-main`. Сторінка могла виглядати порожньою навіть без JavaScript-помилки.

**Що змінили**

CSS-класи перейменували на `treba-admin-*` і додали стабільний маркер `data-treba-workspace`; backend #97 узгодив preflight-перевірку.

**Посилання:** [FE #51](https://github.com/tr3ba/treba-frontend/pull/51), [BE #97](https://github.com/tr3ba/treba-backend/pull/97).

**Що врахували:** UI-регресія та збій CI: різні категорії; перевіряти слід і відображення, і deployment-контракт.

</details>


## Журнал невдалих запусків

До 31 жовтня у GitHub Actions зафіксовано **42 невдалі запуски**: 30 backend і 12 frontend. Час у таблиці означає створення запуску.

<details>
<summary><strong>Показати всі 42 невдалі запуски</strong></summary>

### Запуски GitHub Actions

Таблиця охоплює запуски до 31.10.2026. Висновок Actions `failure` означає невдалий workflow; пояснення причини наведено лише там, де воно є у пов'язаному PR. Посилання відкривають записи запусків у GitHub.

| Репозиторій | Запусків | Failure |
|---|---:|---:|
| backend | 416 | 30 |
| frontend | 180 | 12 |

### Пояснення з PR

- [BE #84](https://github.com/tr3ba/treba-backend/pull/84): описує зупинку EC2 deployment через відсутність міграції мов профілю в allowlist; [невдалий run](https://github.com/tr3ba/treba-backend/actions/runs/39964848356).
- [BE #91](https://github.com/tr3ba/treba-backend/pull/91): описує розбіжність імені таблиці `UserExternalLogins` у перевірці привілеїв і міграції; [невдалий run](https://github.com/tr3ba/treba-backend/actions/runs/40589126102).
- [BE #95](https://github.com/tr3ba/treba-backend/pull/95): описує падіння build/Docker через тест міграції delivery, що викликав усі нові міграції в мінімальній схемі; [невдалий run](https://github.com/tr3ba/treba-backend/actions/runs/40899897467) є часово пов'язаним, але причина саме цього run потребує job log.
- [FE #37](https://github.com/tr3ba/treba-frontend/pull/37): описує диск EC2, заповнений на 99%, і rollback-контейнери, що тримали старі образи; [невдалий run](https://github.com/tr3ba/treba-frontend/actions/runs/39756631924).
- [BE #18](https://github.com/tr3ba/treba-backend/pull/18), [#22](https://github.com/tr3ba/treba-backend/pull/22): названі демонстраціями CI failure; не слід рахувати їх production-аваріями.

### Повний перелік невдалих запусків

| UTC | Репозиторій | Workflow | Run | Заголовок |
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

### Про статуси запусків

Статус `failure` показує невдалий workflow. Причину окремого запуску слід дивитися в його job log; сам статус не описує впливу на користувачів.


</details>
