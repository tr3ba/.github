<div align="center">

# Історія TREBA

### Від першого завдання до маркетплейсу

[English](project-history.en.md) · **Українська**

**18 липня - 5 листопада 2026 року**<br>
Дати подій GitHub наведено в **UTC**

[![Backend](https://img.shields.io/badge/BACKEND-256_commits-FF6E2A?style=flat-square)](https://github.com/tr3ba/treba-backend)
[![Frontend](https://img.shields.io/badge/FRONTEND-187_commits-002AFF?style=flat-square)](https://github.com/tr3ba/treba-frontend)
[![Profile](https://img.shields.io/badge/PROFILE-21_commits-002AFF?style=flat-square)](https://github.com/tr3ba/.github)

</div>

<div align="center">

[Головна](../../README.uk.md) · [Журнал](daily-log.md) · [Команда](../team/README.md) · [Виправлення](../incidents/README.md)

</div>

18 липня команда отримала завдання створити маркетплейс за наданим дизайном. 20 липня з’явилися перші коміти backend і frontend. Основні події до початку листопада зібрано в [журналі розробки](daily-log.md).

<table width="100%">
<tr>
<td width="25%" align="center">

<sub>ПЕРШЕ ЗАВДАННЯ</sub>

### 18.07.2026

Формування команди

</td>
<td width="25%" align="center">

<sub>ОСТАННЯ ПОДІЯ ЖУРНАЛУ</sub>

### 05.11.2026

Скасування замовлення покупцем

</td>
<td width="25%" align="center">

<sub>ІСТОРІЯ КОДУ</sub>

### 464

Коміти трьох репозиторіїв

</td>
<td width="25%" align="center">

<sub>ІСТОРІЯ ЗМІН</sub>

### 151

Злитих PR

</td>
</tr>
</table>

<div align="center">

[![Липень](https://img.shields.io/badge/01_ЛИПЕНЬ-ОСНОВА-7494FF?style=for-the-badge)](#history-july)
[![Серпень](https://img.shields.io/badge/02_СЕРПЕНЬ-КОНТЕЙНЕРИ-ED7100?style=for-the-badge)](#history-august)
[![Вересень](https://img.shields.io/badge/03_ВЕРЕСЕНЬ-API_ТА_CI-2EA985?style=for-the-badge)](#history-september)
[![Жовтень](https://img.shields.io/badge/04_ЖОВТЕНЬ-ІНТЕГРАЦІЯ-8755C8?style=for-the-badge)](#history-october)
[![Листопад](https://img.shields.io/badge/05_ЛИСТОПАД-ЗАМОВЛЕННЯ-D5A22F?style=for-the-badge)](#history-november)

[Журнал за днями](daily-log.md) · [Команда](../team/README.md)

</div>

TREBA розвивався від двох початкових репозиторіїв до маркетплейсу з каталогом, покупками, продавцями, підтримкою й адміністративним простором. Паралельно формувалася доставка через Docker, GitHub Actions та AWS. Тут зібрано етапи розвитку; окремі дати та ключові зміни є в [журналі розробки](daily-log.md).

**18 липня 2026 року** студентів розподілили на команди й дали завдання зробити клон інтернет-магазину Rozetka. Команда отримала готовий дизайн сайту. Робоча назва «Розетта» виникла з цього завдання. **20 липня** з'явилися backend і frontend репозиторії та перші коміти. Це початок хронології GitHub.

<details>
<summary><strong>Зміст історії</strong></summary>

- [Коли все почалося](#history-origin)
- [Коротка карта етапів](#history-stages)
- [Липень: основа](#history-july)
- [Серпень: база даних, контейнери й доставка](#history-august)
- [Вересень: каталог, CI та авторизація](#history-september)
- [Жовтень: інтеграція та розвиток маркетплейсу](#history-october)
- [Листопад: скасування замовлення](#history-november)
- [Як змінювалися компоненти](#history-components)
- [Збої та виправлення](#history-incidents)
- [Журнал розробки](daily-log.md)

</details>

---

<a id="history-origin"></a>

## Коли все почалося

**18 липня:** студентів поділили на команди, представили завдання зробити клон інтернет-магазину Rozetka та надали дизайн сайту.

**20 липня:** створили окремі репозиторії backend і frontend. Їхні точні дати та перші коміти наведено нижче.

<details>
<summary><strong>Дати створення та початкові коміти</strong></summary>

| Подія | Дата й час UTC | Посилання |
|---|---|---|
| Створено backend-репозиторій | 20.07.2026 11:15:46 | [GitHub](https://api.github.com/repos/tr3ba/treba-backend) |
| Початковий коміт backend | 20.07.2026 11:15:46 | [a44ad6d](https://github.com/tr3ba/treba-backend/commit/a44ad6dca4be32cb07806f94cc4e55807950c459) |
| Створено frontend-репозиторій | 20.07.2026 11:18:31 | [GitHub](https://api.github.com/repos/tr3ba/treba-frontend) |
| Початковий коміт frontend | 20.07.2026 11:18:32 | [e75d570](https://github.com/tr3ba/treba-frontend/commit/e75d570a8240d7a05ed8c0f7b1523e530ca3a035) |
| Створено репозиторій профілю `.github` | 06.10.2026 20:43:53 | [GitHub](https://api.github.com/repos/tr3ba/.github) |

Перші коміти backend і frontend зробив **Broadcast1Storm**. Репозиторій `.github` з’явився пізніше для оформлення профілю проєкту.

</details>

<a id="history-stages"></a>

## Коротка карта етапів

<table width="100%">
<tr>
<td width="50%" valign="top">

### 01 · 18-26 липня

Початкові репозиторії, структура backend і доменні сутності.

</td>
<td width="50%" valign="top">

### 02 · Серпень

Адмінпанель, користувачі й підключення БД, Docker, перші workflows доставки в ECR/EC2.

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 03 · Вересень

Новий AWS account, API каталогу, тести й перевірки CI, авторизація.

</td>
<td width="50%" valign="top">

### 04 · 2-15 жовтня

Продавці, кошик, склад, API-шар frontend, адаптивність, безпека конфігурації, Kubernetes, бажання, відгуки та замовлення.

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 05 · 19-25 жовтня

Імпорт товарів, підтримка, реальні дані замість моків, checkout, заявки продавців, порівняння товарів.

</td>
<td width="50%" valign="top">

### 06 · 26-31 жовтня

Доставка, OAuth, верифікація й відновлення доступу, перенесення адмінпростору, подальші виправлення.

</td>
</tr>
<tr>
<td colspan="2" valign="top">

### 07 · 5 листопада

Скасування замовлення покупцем у вебінтерфейсі.

</td>
</tr>
</table>

---

<a id="history-july"></a>

## Липень 2026: основа проєкту

<details>
<summary><strong>Липень · початок і каркас backend</strong> · розгорнути історію</summary>

### 18 липня: команди й завдання

Студентів розподілили на команди. Завданням було створити клон інтернет-магазину Rozetka за наданим дизайном.

### 20 липня: окремі backend і frontend

Створено два репозиторії, виконано `Initial commit` і додано службові `.gitkeep`. Від початку код двох частин зберігався окремо. Перші коміти: [backend](https://github.com/tr3ba/treba-backend/commit/a44ad6dca4be32cb07806f94cc4e55807950c459) і [frontend](https://github.com/tr3ba/treba-frontend/commit/e75d570a8240d7a05ed8c0f7b1523e530ca3a035).

### 25-26 липня: каркас backend

25 липня Quixar створив [BE #1](https://github.com/tr3ba/treba-backend/pull/1) з основою **Clean Architecture** та доменними сутностями. PR злили **26 липня о 07:16:55 UTC**. Отже, дата початку цієї зміни й дата її включення відрізняються.

**Результат етапу:** у GitHub є початкова структура проєкту та архітектурна основа backend. Подальші функції й доставка розвивалися поверх неї.

</details>

<a id="history-august"></a>

## Серпень 2026: від каркаса до контейнерної доставки

<details>
<summary><strong>Серпень · дані, Docker і доставка</strong> · розгорнути історію</summary>

### 3-24 серпня: адмінпанель і дані

- **3 серпня** відкрито [BE #2](https://github.com/tr3ba/treba-backend/pull/2) з адмінпанеллю; злиття відбулося **24 серпня**. Робота тривала кілька тижнів.
- **22 серпня** злиті [BE #4](https://github.com/tr3ba/treba-backend/pull/4) і [BE #5](https://github.com/tr3ba/treba-backend/pull/5): оновлено правила ігнорування файлів, додано користувачів і підключення бази даних.

### 8-19 серпня: Docker і перша автоматична збірка

**8 серпня** відкрито [BE #3](https://github.com/tr3ba/treba-backend/pull/3) із Dockerfile backend; PR злитий **19 серпня**. Між цими датами історія містить виправлення тегу .NET-образу **13 серпня**, README **15 серпня** та `build-backend.yml` **17 серпня**.

Того ж **8 серпня** відкрито [FE #1](https://github.com/tr3ba/treba-frontend/pull/1) з першою спробою Dockerfile frontend. Його **не злили**: PR закрили 24 вересня. Контейнеризація frontend, яка потрапила через злитий PR, наведена нижче за **31 серпня**.

### 30 серпня: backend → ECR → EC2

Злиті [BE #6](https://github.com/tr3ba/treba-backend/pull/6), [BE #7](https://github.com/tr3ba/treba-backend/pull/7) та [BE #8](https://github.com/tr3ba/treba-backend/pull/8): публікація Docker-образів в Amazon ECR, автоматизоване розгортання backend на EC2 і виправлення доставки через AWS Systems Manager. Того ж дня був і невдалий запуск розгортання в Actions.

### 31 серпня: frontend і спільне локальне середовище

Злиті [FE #2](https://github.com/tr3ba/treba-frontend/pull/2) та [FE #3](https://github.com/tr3ba/treba-frontend/pull/3) із завантаженням frontend-файлів, потім [FE #4](https://github.com/tr3ba/treba-frontend/pull/4) зі структурою каталогів. [FE #5](https://github.com/tr3ba/treba-frontend/pull/5), [FE #6](https://github.com/tr3ba/treba-frontend/pull/6) і [FE #7](https://github.com/tr3ba/treba-frontend/pull/7) додають Docker-конфігурацію, публікацію образів і EC2 deployment. [FE #8](https://github.com/tr3ba/treba-frontend/pull/8) та [FE #9](https://github.com/tr3ba/treba-frontend/pull/9) уточнюють порт 80 і healthcheck.

На backend злитий [BE #9](https://github.com/tr3ba/treba-backend/pull/9) із **Stage 2 Docker Compose environment**.

**Результат етапу:** обидві частини отримали конфігурацію контейнеризації та доставки; у репозиторіях уже видно окремі виправлення розгортання.

</details>

<a id="history-september"></a>

## Вересень 2026: каталог, перевірки й авторизація

<details>
<summary><strong>Вересень · каталог, CI та авторизація</strong> · розгорнути історію</summary>

### 1 вересня: міграція AWS account

[BE #10](https://github.com/tr3ba/treba-backend/pull/10) і [FE #10](https://github.com/tr3ba/treba-frontend/pull/10) змінюють конфігурацію доставки обох застосунків для нового AWS account.

### 10 вересня: прибирання репозиторію

[BE #11](https://github.com/tr3ba/treba-backend/pull/11) прибирає відстежувані артефакти збірки та оновлює `.gitignore`; серед комітів також є прибирання IDE-артефактів і вирішення конфлікту.

### 13-14 вересня: каталог і повніший CI

- [BE #12](https://github.com/tr3ba/treba-backend/pull/12): збереження каталогу й API.
- [BE #13](https://github.com/tr3ba/treba-backend/pull/13): Docker smoke test і `.dockerignore`.
- [BE #14](https://github.com/tr3ba/treba-backend/pull/14): перевірка вразливостей NuGet.
- [BE #15](https://github.com/tr3ba/treba-backend/pull/15): тест і крок тестування CI.
- [BE #16](https://github.com/tr3ba/treba-backend/pull/16): workflow backend-релізу за тегом: відкрито **13 вересня**, злитий **14 вересня**.

### 16-17 вересня: документація, демонстрація CI та доступ до даних

16 вересня злиті [BE #17](https://github.com/tr3ba/treba-backend/pull/17) з DevOps-документацією та [BE #18](https://github.com/tr3ba/treba-backend/pull/18) з демонстрацією падіння й виправлення CI. 17 вересня [BE #19](https://github.com/tr3ba/treba-backend/pull/19) прибирає облікові дані БД із development-конфігурації, а [BE #20](https://github.com/tr3ba/treba-backend/pull/20) розширює адмінпанель списком і деталями користувачів.

### 18-19 вересня: API сутностей каталогу й авторизація

18 вересня додано конфігурацію збереження сутностей каталогу ([BE #23](https://github.com/tr3ba/treba-backend/pull/23)), API категорій і брендів ([BE #24](https://github.com/tr3ba/treba-backend/pull/24)), атрибутів ([BE #25](https://github.com/tr3ba/treba-backend/pull/25)), варіантів ([BE #26](https://github.com/tr3ba/treba-backend/pull/26)), фото ([BE #27](https://github.com/tr3ba/treba-backend/pull/27)), значень атрибутів ([BE #28](https://github.com/tr3ba/treba-backend/pull/28)) і тегів ([BE #30](https://github.com/tr3ba/treba-backend/pull/30)). Окремо [BE #29](https://github.com/tr3ba/treba-backend/pull/29) додає database health endpoint, [BE #21](https://github.com/tr3ba/treba-backend/pull/21): теги release-образів.

[BE #22](https://github.com/tr3ba/treba-backend/pull/22): ще одна демонстрація failing CI, **закрита без злиття**.

19 вересня злитий [BE #31](https://github.com/tr3ba/treba-backend/pull/31) з авторизацією користувачів. Далі [BE #32](https://github.com/tr3ba/treba-backend/pull/32), [BE #33](https://github.com/tr3ba/treba-backend/pull/33), [BE #34](https://github.com/tr3ba/treba-backend/pull/34), [BE #35](https://github.com/tr3ba/treba-backend/pull/35) і [BE #36](https://github.com/tr3ba/treba-backend/pull/36) змінюють публікацію образів, `Program.cs` та deployment. Actions того дня містять невдалі запуски; без логів не приписуємо кожному одну й ту саму причину.

### 24 вересня: закриття раннього frontend Docker PR

[FE #1](https://github.com/tr3ba/treba-frontend/pull/1), відкритий 8 серпня, закрито без злиття. Це окрема подія від уже злитої Docker-конфігурації [FE #5](https://github.com/tr3ba/treba-frontend/pull/5).

**Результат етапу:** backend має ширший API каталогу й авторизацію; доставка доповнена тестами, smoke check, скануванням і документацією.

</details>

<a id="history-october"></a>

## Жовтень 2026: інтеграція та розвиток маркетплейсу

<details>
<summary><strong>Жовтень · інтеграція та маркетплейс</strong> · розгорнути історію</summary>

<details>
<summary><strong>2-15 жовтня · базові сценарії, API та інфраструктура</strong></summary>

### 2-4 жовтня: продавці, кошик і склад

2 жовтня [BE #37](https://github.com/tr3ba/treba-backend/pull/37) додає продавців і магазини, [BE #38](https://github.com/tr3ba/treba-backend/pull/38): кошик. 3 жовтня [BE #39](https://github.com/tr3ba/treba-backend/pull/39) додає inventory; на frontend [FE #11](https://github.com/tr3ba/treba-frontend/pull/11): сторінку кошика, додавання товарів і виправлення банера/зображень категорій.

### 5-8 жовтня: API-шар і адаптивний інтерфейс

Коміти frontend від **5 жовтня** починають API-клієнт, DTO, мапери, завантаження категорій і товарів. [FE #15](https://github.com/tr3ba/treba-frontend/pull/15) відкрито 7 жовтня й злито **8 жовтня**. Опис PR ще містить перемикач між моками й backend; повне прибирання моків: пізніша подія.

[FE #16](https://github.com/tr3ba/treba-frontend/pull/16) з адаптивною шапкою, головною, мобільним каталогом, підвалом і кабінетом також злитий **8 жовтня**. Паралельно 6-7 жовтня змінюються конфігурація доставки, Dockerfile та документація обох застосунків.

### 6 жовтня: публічний профіль TREBA

Створено репозиторій `.github`, його [початковий коміт](https://github.com/tr3ba/.github/commit/115f8be5aab8e56f5ab2871d68b100542040f86d), README та мовні версії. Backend і frontend існували з липня.

### 9-10 жовтня: інтеграція, конфігурація та Kubernetes

9 жовтня [FE #21](https://github.com/tr3ba/treba-frontend/pull/21) уточнює дозволений домен зображень; [BE #50](https://github.com/tr3ba/treba-backend/pull/50) покращує інтеграцію з frontend, [BE #51](https://github.com/tr3ba/treba-backend/pull/51) прибирає відстежувані development-секрети й додає безпечні шаблони.

10 жовтня [BE #52](https://github.com/tr3ba/treba-backend/pull/52) додає матеріали для локального Kubernetes Stage 5. Основна доставка застосунку залишалася на EC2.

### 12-15 жовтня: бажання, відгуки, замовлення та Stage 5

13 жовтня злиті [BE #53](https://github.com/tr3ba/treba-backend/pull/53) зі списком бажань і [BE #54](https://github.com/tr3ba/treba-backend/pull/54) з відгуками. 14 жовтня [BE #55](https://github.com/tr3ba/treba-backend/pull/55) додає замовлення, [BE #56](https://github.com/tr3ba/treba-backend/pull/56): локальний Kubernetes CD.

[FE #22](https://github.com/tr3ba/treba-frontend/pull/22) з ізольованою Stage 5 ECR-збіркою відкрито **12 жовтня**, але злито **15 жовтня**. Того ж 15 жовтня злитий [FE #23](https://github.com/tr3ba/treba-frontend/pull/23) з початковим кабінетом продавця. Коміти `.github` цього дня оновлюють мовні README.

</details>

<details>
<summary><strong>17-25 жовтня · продавці, підтримка та реальні дані</strong></summary>

### 17-19 жовтня: платежі, імпорт і адміністративні інструменти

[BE #57](https://github.com/tr3ba/treba-backend/pull/57) із платежами відкрито **17 жовтня**, але злитий лише **21 жовтня**.

19 жовтня злиті [BE #58](https://github.com/tr3ba/treba-backend/pull/58), [BE #59](https://github.com/tr3ba/treba-backend/pull/59) і [BE #60](https://github.com/tr3ba/treba-backend/pull/60) з адміністративним простором, Telegram Mini App та виправленнями його доставки. [BE #61](https://github.com/tr3ba/treba-backend/pull/61) додає імпорт товарів і категоризацію, [BE #62](https://github.com/tr3ba/treba-backend/pull/62): promotions, [BE #63](https://github.com/tr3ba/treba-backend/pull/63): зв'язок відгуків із замовленнями. [BE #64](https://github.com/tr3ba/treba-backend/pull/64) з інструментами продавців та чергою імпорту відкрито 19-го й злито **20 жовтня**.

На frontend [FE #24](https://github.com/tr3ba/treba-frontend/pull/24) додає лендинг продавців `/sell` і прибирає старий кабінет продавця.

### 20 жовтня: підтримка, сторінка продавця й бажання

[FE #25](https://github.com/tr3ba/treba-frontend/pull/25) додає публічну сторінку продавця, [FE #27](https://github.com/tr3ba/treba-frontend/pull/27): галерею фото, [FE #29](https://github.com/tr3ba/treba-frontend/pull/29): список бажань.

[BE #66](https://github.com/tr3ba/treba-backend/pull/66), [BE #67](https://github.com/tr3ba/treba-backend/pull/67), [BE #68](https://github.com/tr3ba/treba-backend/pull/68) і [FE #26](https://github.com/tr3ba/treba-frontend/pull/26) розвивають приватну підтримку та питання про товар, розділяючи звернення до TREBA й продавця. [BE #69](https://github.com/tr3ba/treba-backend/pull/69), [FE #28](https://github.com/tr3ba/treba-frontend/pull/28) і [FE #30](https://github.com/tr3ba/treba-frontend/pull/30) змінюють вхід до адміністративних інструментів і перенаправлення.

[BE #65](https://github.com/tr3ba/treba-backend/pull/65) змінює адміністративні операції та відповідну схему API; [BE #70](https://github.com/tr3ba/treba-backend/pull/70) виправляє запуск Mini App через proxy. [BE #71](https://github.com/tr3ba/treba-backend/pull/71), [BE #72](https://github.com/tr3ba/treba-backend/pull/72) й [BE #73](https://github.com/tr3ba/treba-backend/pull/73) доповнюють імпорт і сценарії входу.

### 21 жовтня: перехід від моків до API

Ключова віха: [FE #31](https://github.com/tr3ba/treba-frontend/pull/31): моки прибрано з клієнтського API-шару. [FE #32](https://github.com/tr3ba/treba-frontend/pull/32) підключає кошик і оформлення замовлення до backend; це пізніше за первинну сторінку кошика 3 жовтня.

На backend [BE #74](https://github.com/tr3ba/treba-backend/pull/74), [BE #75](https://github.com/tr3ba/treba-backend/pull/75) та [BE #76](https://github.com/tr3ba/treba-backend/pull/76) змінюють адміністративні інструменти, імпорт, фото модерації та дерево категорій. Злиті [BE #57](https://github.com/tr3ba/treba-backend/pull/57) із платежами й [BE #77](https://github.com/tr3ba/treba-backend/pull/77) з виправленням після конфліктів. [FE #34](https://github.com/tr3ba/treba-frontend/pull/34) переводить фото на `next/image` і використовує компонент іконок для SVG. [BE #78](https://github.com/tr3ba/treba-backend/pull/78) з доставкою цього дня лише відкрито; його злиття: 24 жовтня.

### 22 жовтня: заявки продавців, кабінет і стабілізація

[FE #33](https://github.com/tr3ba/treba-frontend/pull/33), відкритий 21-го, злитий **22 жовтня** й додає повне дерево категорій із фото. [BE #80](https://github.com/tr3ba/treba-backend/pull/80) та [FE #36](https://github.com/tr3ba/treba-frontend/pull/36) пов'язують заявки продавців, пошук/фільтри, кабінет покупця й сповіщення.

[FE #35](https://github.com/tr3ba/treba-frontend/pull/35) змінює перенаправлення за ролями. [BE #79](https://github.com/tr3ba/treba-backend/pull/79) включає backend-тести до основного solution, [BE #81](https://github.com/tr3ba/treba-backend/pull/81) виправляє прив'язування параметрів запиту каталогу. [BE #82](https://github.com/tr3ba/treba-backend/pull/82) і [FE #39](https://github.com/tr3ba/treba-frontend/pull/39) змінюють перемикачі функцій та видалення чатів; [FE #38](https://github.com/tr3ba/treba-frontend/pull/38) повертає іконки категорій.

[FE #37](https://github.com/tr3ba/treba-frontend/pull/37) описує звільнення диска EC2 від образів, утримуваних rollback-контейнерами.

### 23-25 жовтня: локалізація, міграції та порівняння

23 жовтня [BE #83](https://github.com/tr3ba/treba-backend/pull/83) виправляє імпорт продавців, оновлює локалізацію й адмінінтерфейс. [BE #84](https://github.com/tr3ba/treba-backend/pull/84), відкритий 23-го, злитий **24 жовтня** та виправляє allowlist міграції мов профілю. 24-го також злиті [BE #85](https://github.com/tr3ba/treba-backend/pull/85) з тестами й [BE #78](https://github.com/tr3ba/treba-backend/pull/78) з доставкою.

Frontend [FE #41](https://github.com/tr3ba/treba-frontend/pull/41) із порівнянням товарів злитий **25 жовтня в гілку `feature/header-icons`**; [FE #40](https://github.com/tr3ba/treba-frontend/pull/40) того ж дня зливає зміни шапки в `main`.

</details>

<details>
<summary><strong>26-31 жовтня · доставка, доступ і новий адмінпростір</strong></summary>

### 26 жовтня: Нова Пошта та кур'єр TREBA

[BE #86](https://github.com/tr3ba/treba-backend/pull/86) і [FE #42](https://github.com/tr3ba/treba-frontend/pull/42) додають сценарії Нової Пошти та кур'єрської доставки TREBA. [BE #88](https://github.com/tr3ba/treba-backend/pull/88) і [FE #43](https://github.com/tr3ba/treba-frontend/pull/43) уточнюють пошук міст/пунктів, фільтри та відображення checkout. [BE #87](https://github.com/tr3ba/treba-backend/pull/87) містить перші зміни реєстрації через Google/Facebook у цьому наборі PR.

### 27-28 жовтня: OAuth, сесії й відгуки після отримання

27 жовтня злитий [FE #44](https://github.com/tr3ba/treba-frontend/pull/44) з мобільною адаптацією, відкритий напередодні. [BE #89](https://github.com/tr3ba/treba-backend/pull/89) продовжує Google/Facebook auth, [BE #90](https://github.com/tr3ba/treba-backend/pull/90) змінює тест міграції deployment.

28 жовтня [BE #91](https://github.com/tr3ba/treba-backend/pull/91) виправляє розбіжність назви таблиці `UserExternalLogins` у deployment-перевірці й завершує описані в PR сценарії OAuth; [FE #45](https://github.com/tr3ba/treba-frontend/pull/45) додає відповідний клієнтський вхід і реєстрацію.

[BE #92](https://github.com/tr3ba/treba-backend/pull/92) та [FE #46](https://github.com/tr3ba/treba-frontend/pull/46) розділяють адміністративні й клієнтські сесії. [BE #93](https://github.com/tr3ba/treba-backend/pull/93) та [FE #48](https://github.com/tr3ba/treba-frontend/pull/48) уточнюють доставку й відгуки після отримання замовлення. [FE #47](https://github.com/tr3ba/treba-frontend/pull/47) змінює оформлення checkout, промокод і посилання на редагування товарів.

### 29 жовтня: верифікація та перенесення адмінпростору

[BE #94](https://github.com/tr3ba/treba-backend/pull/94) й [FE #49](https://github.com/tr3ba/treba-frontend/pull/49) додають верифіковану реєстрацію та відновлення пароля через email/SMS. [BE #95](https://github.com/tr3ba/treba-backend/pull/95) ізолює тести міграцій.

Архітектурна віха: [FE #50](https://github.com/tr3ba/treba-frontend/pull/50) переносить адміністративний простір у frontend, а [BE #96](https://github.com/tr3ba/treba-backend/pull/96) виводить старий backend-інтерфейс із використання. Пізніше [FE #51](https://github.com/tr3ba/treba-frontend/pull/51) прибирає назви CSS-класів, які блокувалися косметичними фільтрами, а [BE #97](https://github.com/tr3ba/treba-backend/pull/97) узгоджує deployment-перевірки. [FE #52](https://github.com/tr3ba/treba-frontend/pull/52) оновлює дизайн адмінпростору та додає UK/EN-перемикання.

### 30 жовтня: відповіді на відгуки та допрацювання адміністративних сценаріїв

[BE #98](https://github.com/tr3ba/treba-backend/pull/98) додає відповіді на відгуки й розширює імпорт за посиланням, [BE #99](https://github.com/tr3ba/treba-backend/pull/99): роль у деталях користувача. На frontend [FE #53](https://github.com/tr3ba/treba-frontend/pull/53) змінює адміністративні сценарії та перегляд імпорту.

[FE #54](https://github.com/tr3ba/treba-frontend/pull/54) із фільтрами та деталями користувача **відкрито 30 жовтня**, але він ще не злитий цього дня.

### 31 жовтня: фільтри та деталі користувача

Злитий [FE #54](https://github.com/tr3ba/treba-frontend/pull/54) із доопрацюванням фільтрів, локалізації та деталей користувача в адміністративному просторі.

</details>

---

</details>

<a id="history-november"></a>

## Листопад 2026: керування замовленням

**5 листопада** злитий [FE #56](https://github.com/tr3ba/treba-frontend/pull/56). Покупець отримав можливість скасувати замовлення зі своєї сторінки замовлення. Інтерфейс показує дію для статусів «Оформлено» та «Очікує оплати», передає причину через API й оновлює статус після відповіді сервера.

---

<a id="history-components"></a>

## Як змінювалися компоненти

<details>
<summary><strong>Послідовність розвитку компонентів</strong></summary>

| Напрям | Послідовність і зміни |
|---|---|
| Каталог | [API каталогу](https://github.com/tr3ba/treba-backend/pull/12) у вересні → [frontend API-шар](https://github.com/tr3ba/treba-frontend/pull/15) у жовтні → [прибирання моків](https://github.com/tr3ba/treba-frontend/pull/31) → [дерево категорій](https://github.com/tr3ba/treba-backend/pull/76). |
| Покупки | [Backend-кошик](https://github.com/tr3ba/treba-backend/pull/38) → [сторінка кошика](https://github.com/tr3ba/treba-frontend/pull/11) → [оформлення замовлення](https://github.com/tr3ba/treba-frontend/pull/32) → [доставка](https://github.com/tr3ba/treba-backend/pull/86) → [скасування покупцем](https://github.com/tr3ba/treba-frontend/pull/56). |
| Продавці | [Магазини](https://github.com/tr3ba/treba-backend/pull/37) → [кабінет продавця](https://github.com/tr3ba/treba-frontend/pull/23) → [публічна сторінка](https://github.com/tr3ba/treba-frontend/pull/25) → [імпорт товарів](https://github.com/tr3ba/treba-backend/pull/64). |
| Доступ | [Авторизація](https://github.com/tr3ba/treba-backend/pull/31) → [Google/Facebook](https://github.com/tr3ba/treba-backend/pull/91) → [email/SMS-верифікація та відновлення](https://github.com/tr3ba/treba-backend/pull/94). |
| Адміністрування | [Початкова панель](https://github.com/tr3ba/treba-backend/pull/2) → [перенесення інтерфейсу у frontend](https://github.com/tr3ba/treba-frontend/pull/50) → [оновлення backend](https://github.com/tr3ba/treba-backend/pull/96). |
| Доставка коду | [Docker](https://github.com/tr3ba/treba-backend/pull/3) → [ECR/EC2](https://github.com/tr3ba/treba-backend/pull/8) → [оновлення AWS account](https://github.com/tr3ba/treba-backend/pull/10) → [локальний Kubernetes Stage 5](https://github.com/tr3ba/treba-backend/pull/56). |

</details>

<a id="history-incidents"></a>

## Збої та виправлення

<details>
<summary><strong>Підтверджені збої та їхні виправлення</strong></summary>

Історія містить не лише нові можливості, а й невдалі перевірки та виправлення:

- **16 і 18 вересня:** навмисні демонстрації failing CI: [BE #18](https://github.com/tr3ba/treba-backend/pull/18), [BE #22](https://github.com/tr3ba/treba-backend/pull/22).
- **22 жовтня:** [FE #37](https://github.com/tr3ba/treba-frontend/pull/37) описує диск EC2, заповнений на 99%, і прибирання образів, утримуваних rollback-контейнерами.
- **23-24 жовтня:** [BE #84](https://github.com/tr3ba/treba-backend/pull/84) описує блокування deployment через відсутність міграції мов профілю в allowlist.
- **27-28 жовтня:** [BE #91](https://github.com/tr3ba/treba-backend/pull/91) пояснює проблему назви таблиці `UserExternalLogins` під час deployment.
- **29 жовтня:** [BE #95](https://github.com/tr3ba/treba-backend/pull/95) пояснює некоректну межу застосування міграцій у тесті; [FE #51](https://github.com/tr3ba/treba-frontend/pull/51): порожній адмінпростір через косметичні фільтри.

[Докладні розбори помилок і виправлень](../incidents/README.md) зібрано на окремій сторінці.

</details>

---

[Переглянути команду та її PR](../team/README.md) · [Відкрити журнал за днями](daily-log.md)
