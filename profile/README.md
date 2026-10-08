## MonadIAM

A modular platform for Identity and Access Management (IAM) and
Human Resource Management (HRM).

MonadIAM separates authentication, authorization, organizational structure,
and workforce processes into dedicated services, with shared contracts,
notifications, and infrastructure.

> MonadIAM is a personal architectural playground, designed and developed
in my spare time.

----

<details>
<summary><strong>Domains</strong></summary>

#### Identity and Access Management · IAM

Manage accounts, authenticate users, and control access to application resources.

- **Identity / AuthN** — account lifecycle, OAuth 2.0 and OpenID Connect,
  federated login, sessions, token rotation, two-factor authentication,
  account recovery, and reauthentication.
- **Access Control / AuthZ** — hierarchical role-based access control,
  discretionary permission overrides, separation of duties,
  role delegation policies, and realm-scoped access control.

#### Human Resource Management · HRM

Manage employee records and workforce processes within an organization.

- **Workforce** — employees, employment records, positions, and staffing.
- **Working time** — work calendars, schedules, leave policies, and absences.
- **Employee requests** — requests and approval workflows.

HRM is under active development. Domain models and application logic are
being implemented; the HR HTTP API is pending.

#### Shared organizational context

Organizations, departments, teams, projects, memberships, and invitations
provide a common organizational context for IAM and HRM.

Organization membership, access permissions, and employment records are
managed as distinct concepts by their respective services.

</details>

----

<details>
<summary><strong>Services</strong></summary>

| Repository                                                                   | Area        | Responsibility                                                                                |
|:-----------------------------------------------------------------------------|:------------|:----------------------------------------------------------------------------------------------|
| [identity-service](https://github.com/MonadIAM/identity-service)             | IAM · AuthN | Accounts, authentication, federation, sessions, and token lifecycle.                          |
| [access-control-service](https://github.com/MonadIAM/access-control-service) | IAM · AuthZ | Roles, permissions, delegation, separation of duties, and access decisions.                   |
| [notification-service](https://github.com/MonadIAM/notification-service)     | Platform    | Email via AWS SES, SMS via AWS SNS, in-app notifications, preferences, and dispatch tracking. |
| [organization-service](https://github.com/MonadIAM/organization-service)     | IAM / HRM   | Organizational structure, memberships, project assignments, and invitations.                  |
| [hr-service](https://github.com/MonadIAM/hr-service)                         | HRM         | Employee records, staffing, work schedules, leave, and approval workflows.                    |

</details>

----

<details>
<summary><strong>Platform components</strong></summary>

| Repository                                                       | Responsibility                                                                                                                    |
|:-----------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------|
| [shared](https://github.com/MonadIAM/shared)                     | Shared TypeScript definitions, gRPC contracts, Kafka schemas, seed datasets, and schema publication.                              |
| [infra](https://github.com/MonadIAM/infra)                       | Shared local infrastructure for data storage, messaging, secrets, audit archival, and observability.                              |
| [template-service](https://github.com/MonadIAM/template-service) | NestJS service foundation with authentication and authorization integration, audit/change logs, messaging, and retention cleanup. |

</details>

----

#### Getting started

Start with the [local infrastructure](https://github.com/MonadIAM/infra),
then follow the setup instructions in the required service repositories.

Each repository documents its local runtime, configuration,
development commands, and available interfaces.
