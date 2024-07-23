# Routing

- File System based Routing
- Every directly represent the url segment i.e. https://exmple.com/about will have a folder in src/routes/about
- Dynamic Routing will be like a folder with src/routes/[slug]
  - You can access this via page variable in the svelte store as `$page.params.slug` page will be imported like `import { page } from '$app/stores'`; 

## Files

- +page.svelte
  - user for: building UI
  - runs on: client & server
- +page.ts
  - user for: data fetching
  - runs on: client & server
- +page.server.ts
  - user for: data fetching
  - runs on: server only
- +layout.ts
  - user for: data fetching
  - runs on: client & server
- +server.ts
  - user for: api routes
  - runs on: server only
- +error.svelte
  - user for: api routes
  - runs on: server only