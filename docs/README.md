# SprintDesk API

The backend API for SprintDesk. The intended stack is Node.js, NestJS, TypeScript, Prisma, and PostgreSQL.

> **Status:** Work in progress. This document describes intended responsibilities and must be updated as endpoints and modules are implemented.

## Responsibilities

- Expose a documented REST API.
- Validate untrusted request data at runtime.
- Apply business rules in services.
- Authenticate requests and authorize access to resources.
- Persist data through Prisma and PostgreSQL.
- Return consistent HTTP status codes and error responses.
- Log useful operational information without leaking secrets or sensitive data.
- Support automated unit and integration testing.

## Intended module boundaries

```text
AuthModule
UsersModule
WorkspacesModule
ProjectsModule
TasksModule
CommentsModule
```

Create modules when they represent meaningful responsibilities. Avoid unnecessary abstractions before the domain requires them.

## Request flow

```text
HTTP request
    |
    v
Controller / route handler
    |
    v
Runtime validation and guards
    |
    v
Service (business rules)
    |
    v
Prisma Client
    |
    v
PostgreSQL
```

The NestJS request lifecycle can also include middleware, pipes, interceptors, and exception filters. Document the pieces actually used by the implementation.

## API design expectations

- Use consistent resource-oriented routes.
- Validate path parameters, query parameters, and request bodies.
- Use appropriate HTTP status codes.
- Define pagination and sorting behavior explicitly.
- Return consistent error shapes.
- Avoid leaking stack traces or internal database details to clients.
- Enforce authorization for every protected resource.
- Keep API contracts documented and tested.

## Database and Prisma

Prisma is the data-access layer, not a replacement for database knowledge. Review generated queries and understand the underlying PostgreSQL behavior.

For schema changes:
1. Update the Prisma schema intentionally.
2. Generate and review a migration.
3. Test the migration against representative data.
4. Consider compatibility with currently deployed application versions.
5. Use a deliberate production migration process.

Use transactions when multiple database changes must succeed or fail together. Do not assume every multi-step operation is automatically atomic.

## Reliability and failure handling

Plan and test behavior for invalid input, unauthenticated requests, missing permissions, missing resources, unique-constraint violations, database timeouts, duplicate requests, concurrent updates, unexpected exceptions, and graceful shutdown.

Retries should be limited to operations and errors where retrying is safe. For non-idempotent operations, consider how duplicate execution will be prevented or detected.

## Security

- Hash passwords with a suitable password-hashing algorithm.
- Keep secrets in environment configuration or a secret manager.
- Validate all incoming data at runtime.
- Enforce authorization in backend code.
- Use least-privilege database credentials.
- Avoid logging passwords, tokens, or sensitive payloads.
- Apply rate limits to appropriate endpoints.
- Configure CORS and cookies deliberately.
- Review authentication and token lifecycle decisions before deployment.

## Development and tests

Add verified commands and required environment variables after the API scaffold is committed. Never document untested commands as confirmed.

Expected test layers:
- Unit tests for business rules.
- Integration tests for database-backed services and endpoints.
- API tests for validation, authentication, and authorization.
- Migration checks for schema changes.

## Observability

As the service matures, document structured logs, request or correlation IDs, health and readiness checks, error-rate and latency metrics, database connection/query monitoring, alerting, and incident investigation procedures.
