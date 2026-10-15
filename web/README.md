# SprintDesk Web

The web frontend for SprintDesk. The intended stack is Next.js App Router, React, and TypeScript.

> **Status:** Work in progress. Update this document to match the actual implementation before treating the app as runnable or feature-complete.

## Responsibilities

- Render application pages and layouts.
- Provide accessible, interactive task and project-management experiences.
- Manage client-side interaction state.
- Call the backend API where appropriate.
- Display loading, empty, success, and error states.
- Provide route metadata and SEO behavior for suitable pages.

Business rules and authorization must still be enforced by the backend.

## Planned routes

```text
/login
/dashboard
/workspaces
/workspaces/[workspaceId]
/projects/[projectId]
/projects/[projectId]/tasks/[taskId]
/settings/members
```

These are proposed routes; verify that each exists before describing it as available.

## Frontend design principles

### Server Components and Client Components

Use Server Components by default when server rendering and server-side data access fit the use case. Add the `'use client'` directive only where client-side interactivity or browser APIs are required.

A Client Component is not automatically a separate service. Both component types belong to the Next.js application.

### State placement

Choose state based on its purpose:
- Component state for local interaction.
- URL search parameters for shareable filters and navigation state when appropriate.
- Redux Toolkit for genuinely shared client state.
- RTK Query for API data caching and request lifecycle when it fits the feature.
- Server-side data access for suitable server-rendered experiences.

Avoid putting every value in Redux or duplicating the same server data in multiple stores without a clear reason.

### Performance

- Measure render behavior before optimizing.
- Use stable list keys.
- Avoid effects that can be replaced with derived values or event handlers.
- Handle request cancellation or stale responses where necessary.
- Use memoization only when it addresses a demonstrated problem.
- Provide loading and error UI for asynchronous work.

### Accessibility

- Use semantic HTML.
- Ensure forms have labels and useful validation messages.
- Support keyboard navigation.
- Maintain visible focus states.
- Do not rely on color alone to communicate status.

## API configuration

Configure the API base URL through environment variables. Document the exact variable name in `.env.example` and the setup guide once implemented.

Only variables intentionally exposed to the browser should use the framework's public prefix. Never expose database credentials, signing secrets, or private API keys to client-side code.

## Development

Add verified commands after the app scaffold is committed. Do not publish placeholder commands as though they have been tested.

Document commands for starting the development server, linting, type-checking, running component tests, and building the production bundle.

## Testing expectations

Test user-visible behavior where practical. Include coverage for form validation, loading and error states, empty lists and pagination, permission-dependent UI, task creation/editing, and accessible interaction patterns.

The backend must independently enforce permissions regardless of what the UI displays.
