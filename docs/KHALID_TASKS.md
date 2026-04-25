# Khalid Tasks

Role: Auth, admin, and security support owner  
Primary ownership: staff authentication, admin routes, permissions, security review, and Convex data access.

## Setup Checklist

- [ ] Read `README.md`.
- [ ] Read `docs/CODEBASE_MAP.md`.
- [ ] Pull the latest `main` branch before starting work.
- [ ] Create a feature branch using `feature/<short-description>` or `fix/<short-description>`.
- [ ] Confirm local environment variables are configured for Convex and Clerk.
- [ ] Confirm you can run `bun run build`.

## Week 1: Auth and Permission Audit

- [ ] Review `convex/auth.config.ts`.
- [ ] Review `convex/staff.ts`.
- [ ] Review `convex/lib/auth.ts`.
- [ ] Review `convex/lib/permissions.ts`.
- [ ] Review `convex/admin.ts`.
- [ ] Review `convex/schema.ts` staff and audit tables.
- [ ] Document staff roles and what each role can do.
- [ ] Define the protected admin route structure.
- [ ] Confirm Clerk webhook requirements with Mikhail.
- [ ] Identify any admin routes or data flows that still need implementation.
- [ ] Open a PR with auth/admin audit notes or implementation changes.

## Week 2: Admin Shell and Protected Access

- [ ] Implement or harden protected admin route layout.
- [ ] Ensure unauthenticated users cannot access admin pages.
- [ ] Ensure authenticated users without staff access cannot access admin data.
- [ ] Ensure role checks happen on the server.
- [ ] Ensure admin UI does not rely on client-only role checks.
- [ ] Add clear unauthorized and forbidden states.
- [ ] Create admin navigation for campaigns, posts, events, impact, forms, donations, and staff.
- [ ] Add or update tests where practical for permission rules.
- [ ] Open a PR for admin route protection.

## Week 3: Admin CRUD and Data Safety

- [ ] Implement or review campaign admin workflows.
- [ ] Implement or review post admin workflows.
- [ ] Implement or review event admin workflows.
- [ ] Implement or review impact metric admin workflows.
- [ ] Implement or review form submission admin workflows.
- [ ] Implement or review staff management workflows.
- [ ] Ensure all admin mutations validate inputs server-side.
- [ ] Ensure destructive actions require confirmation or a safe undo/recovery path.
- [ ] Ensure audit logs capture important admin changes.
- [ ] Review donor data exposure in admin views.
- [ ] Open a PR for admin CRUD and permission hardening.

## Week 4: Security and Launch Review

- [ ] Review public forms for validation and rate limiting.
- [ ] Review admin actions for permission bypass risk.
- [ ] Review donor data handling and public exposure risk.
- [ ] Review environment variable usage.
- [ ] Confirm no secrets are committed.
- [ ] Confirm Clerk production settings are documented.
- [ ] Confirm staff roles are ready for launch.
- [ ] Write security and admin launch notes for Mikhail.
- [ ] Help review intern PRs that touch Convex, forms, or admin data.

## PR Checklist

- [ ] PR explains what changed.
- [ ] PR explains why it changed.
- [ ] PR explains how to test it.
- [ ] `bun run build` passes.
- [ ] Auth and permission behavior is manually verified.
- [ ] Mikhail is requested as final reviewer.
