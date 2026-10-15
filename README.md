# SprintDesk

**A full-stack project management application built to explore production-minded web engineering.**

SprintDesk is a learning and portfolio project for building a project-management SaaS application with a typed frontend, a structured Node.js backend, and a relational database. It is being developed incrementally, with an emphasis on understanding architectural decisions—not just getting features to work.

> **Project status:** Work in progress. The features and architecture below describe the intended direction. A feature should be considered implemented only when it exists in the codebase and is covered by appropriate tests.

## Goals

- Build a realistic full-stack application using TypeScript end to end.
- Understand React rendering, state management, and component design.
- Explore Next.js App Router features, including Server and Client Components.
- Build a maintainable REST API with NestJS and Node.js.
- Model relational data and migrations with PostgreSQL and Prisma.
- Practice authentication, authorization, validation, testing, debugging, and deployment.
- Document trade-offs and failure cases as part of the engineering process.

## Planned technology stack

| Area | Technology |
|---|---|
| Language | TypeScript |
| Web application | Next.js App Router, React |
| Client state and API cache | Redux Toolkit, RTK Query where appropriate |
| Backend API | Node.js, NestJS |
| API style | REST |
| Database | PostgreSQL |
| ORM | Prisma |
| Validation | DTO validation and runtime input validation |
| Testing | Jest, React Testing Library, API/integration tests |
| Local development and deployment | Docker and CI/CD (introduced incrementally) |

## Planned features

- User registration and login
- Workspaces and membership
- Projects
- Tasks with statuses, assignees, filters, sorting, and pagination
- Task comments and activity history
- Role-based authorization
- Dashboard summaries
- Tests, logging, health checks, and deployment documentation

These are planned capabilities, not a claim that they are all available today.

## Architecture direction

```text
Browser
  |
  v
Next.js / React
  |-- Server Components for suitable server-rendered experiences
  |-- Client Components for interactive experiences
  |-- Redux Toolkit / RTK Query where shared client state or API caching helps
  |
  v
NestJS REST API
  |-- Controllers and request validation
  |-- Guards for authentication and authorization
  |-- Services for business logic
  |
  v
Prisma Client
  |
  v
PostgreSQL
```

This separation is a deliberate learning choice, not a claim that every Next.js application needs a separate backend. Architecture decisions will be revisited as the project develops.

## Intended repository structure

```text
sprintdesk/
├── apps/
│   ├── web/                 # Next.js frontend
│   └── api/                 # NestJS REST API
├── docs/
│   ├── architecture.md
│   ├── data-model.md
│   ├── decisions/
│   └── learning-roadmap.md
├── README.md
└── CONTRIBUTING.md
```

This structure is a proposal. Keep it synchronized with the actual repository.

## Getting started

Setup instructions will be added once the initial application scaffold and package manager are committed.

Before publishing runnable setup commands, document:
1. Supported Node.js version.
2. Package manager and lockfile.
3. Required environment variables.
4. How to start PostgreSQL locally.
5. How to apply Prisma migrations.
6. How to run the web app, API, and tests.

Never commit real API keys, database passwords, JWT secrets, or production environment files. Provide an `.env.example` containing placeholders only.

## Engineering principles

- Be explicit about project status; do not claim unimplemented features.
- Validate at runtime. TypeScript types alone do not validate HTTP input.
- Enforce authorization on the server. Hiding frontend controls is not a security boundary.
- Design database constraints intentionally.
- Test failure paths, including invalid input, missing permissions, database errors, and concurrency-sensitive behavior.
- Measure before optimizing.
- Document trade-offs and alternatives.
- Keep secrets out of Git.

## Learning and documentation

SprintDesk is intended to demonstrate both implementation and engineering reasoning. Design notes should explain the problem, options considered, decision, consequences, and conditions that might justify changing the decision.

See [CONTRIBUTING.md](./CONTRIBUTING.md) for development and documentation expectations.

## Security

Please do not report vulnerabilities in public issues with exploitable details. See [SECURITY.md](./SECURITY.md).

## License

No license has been selected yet. Until a license file is added, do not assume that the repository grants permission to reuse, modify, or redistribute its contents.
