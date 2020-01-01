# Umami

## Source development guide

### Product and architecture

Website analytics with event collection, reports, dashboards and a browser tracking script.

Next.js application and API routes in `src/`, Prisma database schema in `prisma/`, tracker and recorder bundles built by Rollup, and reusable clients in `packages/`. PostgreSQL stores analytics data.

### Requirements and local development

pnpm 12.3.4, Node compatible with the installed Next.js package, PostgreSQL and a configured database URL.

Run these commands from the repository root unless a `cd` is shown:

```sh
pnpm install
pnpm dev
```

These are source-defined entry points. Full dependency installation and service startup were not run during the portfolio maintenance audit; successful application deployment is not claimed.

### Environment configuration

Inspect `scripts/check-env.js` and the component-specific environment templates before startup. Supply local database, service URLs and integration credentials through untracked environment files or a secret manager. Do not copy production credentials into tracked files.

### Testing

```sh
pnpm test
pnpm lint
```

The full application suite requires the dependencies and services described above. Source paths and documented script names were inspected, and `git diff --check` passed. Application tests and builds were not executed.

### Deployment and integrations

Start with `docker-compose.yml` and review image versions, persistent data paths, authentication, exposed ports and backups before production use. Integration implementations and configuration are in the source directories described above; generated API clients must stay in sync with server contracts.

### Source provenance and license

Imported from [umami-software/umami](https://github.com/umami-software/umami); upstream functionality and copyright belong to the original contributors. Local Git history begins with a 2026 source snapshot import, not historical authorship. The exact imported upstream revision is unknown. The upstream GitHub repository was created on 2020-07-17; the local year directory is organizational metadata.

Read [LICENSE](LICENSE) and nested license/notice files before redistribution; enterprise and bundled third-party components may use different terms. Restored root license text was retrieved verbatim from the official upstream repository during this maintenance pass.
