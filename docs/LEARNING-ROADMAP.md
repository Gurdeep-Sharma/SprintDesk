# SprintDesk Learning Roadmap

This roadmap describes intended learning milestones, not proof that the work has been completed. Update each milestone as implementation and testing progress.

## Milestone 1 — TypeScript foundation

- [ ] Type inference, unions, intersections, narrowing, and type guards
- [ ] `type` versus `interface`
- [ ] Generics and utility types
- [ ] `unknown` versus `any`
- [ ] Runtime validation versus compile-time types
- [ ] Typed request and response contracts

**Evidence:** Typed domain models and tests for runtime validation.

## Milestone 2 — React fundamentals

- [ ] Components, props, state, and composition
- [ ] Rendering and reconciliation
- [ ] Effects and cleanup
- [ ] Refs and custom hooks
- [ ] Forms and accessible UI
- [ ] Performance profiling and measured optimization

**Evidence:** Task creation/editing UI with loading, empty, and error states.

## Milestone 3 — Next.js App Router

- [ ] Routing and nested layouts
- [ ] Server Components versus Client Components
- [ ] Server-side data access
- [ ] Loading, error, and Suspense boundaries
- [ ] Route handlers and Server Actions: use cases and trade-offs
- [ ] Caching and revalidation
- [ ] Metadata, environment variables, and security boundaries

**Evidence:** Documented rendering and data-fetching decisions.

## Milestone 4 — Redux Toolkit

- [ ] Store, slices, actions, reducers, and selectors
- [ ] Local state versus shared state
- [ ] Async workflows
- [ ] RTK Query caching and invalidation
- [ ] Error and loading states
- [ ] Redux DevTools and tests

**Evidence:** A justified state-management design rather than putting all state in Redux.

## Milestone 5 — NestJS and Node.js

- [ ] Modules, controllers, providers, and dependency injection
- [ ] DTOs and runtime validation
- [ ] Guards, pipes, interceptors, and exception filters
- [ ] Asynchronous error handling
- [ ] Event loop blocking and CPU-bound work
- [ ] Timeouts, streams, graceful shutdown, and process failures
- [ ] Unit and integration testing

**Evidence:** Tested REST endpoints with consistent error behavior.

## Milestone 6 — PostgreSQL and Prisma

- [ ] Relational data modeling
- [ ] Constraints and foreign keys
- [ ] Prisma schema and generated client
- [ ] Migrations
- [ ] Filtering, sorting, and pagination
- [ ] Transactions and concurrent updates
- [ ] Indexes and query plans
- [ ] N+1 query investigation

**Evidence:** Reviewed schema, migration history, and tests for important database invariants.

## Milestone 7 — Authentication and authorization

- [ ] Password hashing
- [ ] Authentication and authorization
- [ ] Token and cookie lifecycle
- [ ] Workspace membership and role checks
- [ ] Cross-resource access tests
- [ ] Rate limiting and secure configuration

**Evidence:** Tests showing that users cannot access resources without permission.

## Milestone 8 — Reliability and delivery

- [ ] Structured logging and request IDs
- [ ] Health checks and graceful shutdown
- [ ] Docker development environment
- [ ] CI checks
- [ ] Deployment and rollback notes
- [ ] Database failure handling
- [ ] Performance investigation
- [ ] Scaling trade-offs

**Evidence:** Reproducible setup, automated checks, and documented failure-handling decisions.

## Interview readiness

For each major feature, prepare to explain the problem and requirements, implementation and request/data flow, alternatives and trade-offs, validation and failure behavior, testing and observability, performance bottlenecks and what changes at 10x traffic, and what you would redesign and why.
