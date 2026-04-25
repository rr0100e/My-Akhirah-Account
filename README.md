# My Akhirah Account

My Akhirah Account is a charity website for Islamic giving and community support work in Africa. The project should help donors understand the charity's work, choose trusted appeals, donate securely, receive receipts, and see clear impact updates.

## Current Stack

- Framework: Next.js 16 App Router
- Language: TypeScript
- UI: React 19, Tailwind CSS v4
- Backend: Convex
- Auth: Clerk for staff/admin access
- Payments: Flutterwave checkout and webhooks
- Package manager: Bun

## Project Goals

The finished website should support:

- Clear charity homepage with mission, appeals, trust signals, and impact statistics
- Campaign and programme pages for African charity projects
- Donation flow with one-off giving, campaign/fund selection, fee coverage, and donor details
- Secure Flutterwave payment checkout and webhook reconciliation
- Donation receipts and donor confirmation emails
- Blog/news updates, events, volunteer form, contact form, and newsletter signup
- Staff/admin workflows for campaigns, posts, events, impact metrics, forms, donors, and donations
- Search and filtering for campaigns, posts, and events
- Mobile-first responsive design and accessible UI
- Production deployment with environment variables, monitoring, and launch checks

## Repository Guide

For a detailed map of the current codebase, read [docs/CODEBASE_MAP.md](docs/CODEBASE_MAP.md).

Important areas:

- `src/app/` - Next.js routes, layout, homepage, and API route handlers
- `src/components/` - Shared layout, section, and card components
- `src/lib/server/` - Server-side Convex helpers and homepage data loading
- `src/lib/validation/` - Public form validation
- `convex/` - Backend schema, queries, mutations, actions, payment logic, staff logic, and webhooks
- `convex/_generated/` - Auto-generated Convex files. Do not edit these manually.
- `public/` - Static images and brand assets

## Getting Started

Install dependencies:

```bash
bun install
```

Run the development server:

```bash
bun run dev
```

Build for production:

```bash
bun run build
```

Run linting:

```bash
bun run lint
```

## Environment Setup

Create local environment files from the project manager's shared credentials. Do not commit real secrets.

Expected services:

- Convex project URL and deployment keys
- Clerk application keys and webhook secret
- Flutterwave public key, secret key, and webhook secret
- Email provider credentials for receipts and notifications
- Production site URL for payment redirects and webhook configuration

Rules:

- Never commit `.env`, `.env.local`, API keys, webhook secrets, or payment credentials.
- Use test/sandbox payment credentials until the manager approves production payment testing.
- Any code that handles donations, permissions, webhooks, or donor data must be reviewed by the relevant support owner and Mikhail.

## Team

Manager and final reviewer:

- Mikhail - owns hardest/highest-risk work, reviews code, approves scope, merges PRs, and owns final launch approval

Internship team:

- Yasar
- Khalid
- Muneeb
- Raheema
- Mustaf
- James
- Ahlaam

## Working Rules

- Work on feature branches only. Do not push directly to `main`.
- Branch names should use lowercase kebab-case, such as `feature/donation-checkout` or `fix/contact-validation`.
- Keep PRs focused. A PR should solve one feature, bug, or page.
- Every PR description must include what changed, why it changed, and how to test it.
- Payment, auth, admin, database, and security-sensitive work needs support-owner review before manager review.
- Everyone should request review early when unsure, especially before changing shared types, schema, or payment code.
- Do not edit generated files in `convex/_generated/`.
- Use server-side validation for form submissions, donations, payments, permissions, and admin actions.
- Do not trust client-side values for donation totals, permissions, payment status, or staff roles.
- Prefer small, clear components and keep business logic out of UI components.

## Testing Expectations

When changing behavior, write or update the closest meaningful test first where practical. If test-first is not practical, explain the reason in the PR and provide manual verification steps.

Minimum checks before opening a PR:

```bash
bun run lint
bun run build
```

High-risk areas need stronger verification:

- Donation checkout: test successful, cancelled, failed, and expired payments.
- Webhooks: test duplicate events, invalid signatures, mismatched amounts, and unknown references.
- Forms: test invalid input, rate limiting, and successful submissions.
- Admin: test unauthorized access and each staff role.
- Receipts: test receipt creation, retry behavior, and email failure handling.

## Individual Task Files

- [Mikhail tasks](docs/MIKHAIL_TASKS.md)
- [Yasar tasks](docs/YASAR_TASKS.md)
- [Khalid tasks](docs/KHALID_TASKS.md)
- [Muneeb tasks](docs/MUNEEB_TASKS.md)
- [Raheema tasks](docs/RAHEEMA_TASKS.md)
- [Mustaf tasks](docs/MUSTAF_TASKS.md)
- [James tasks](docs/JAMES_TASKS.md)
- [Ahlaam tasks](docs/AHLAAM_TASKS.md)

## Workstream Ownership

Mikhail owns the hardest/highest-risk work. This includes payments, webhooks, donation reconciliation, receipts, production payment setup, final security approval, final merge approval, and launch approval.

Yasar and Khalid own platform support work and review-heavy work that helps de-risk Mikhail's critical path.

Yasar:

- Payment checkout audit and implementation support
- Webhook test support, reconciliation review, and failure-case review
- Donation data model review, receipt flow review, and audit log review
- Production deployment checklist support

Khalid:

- Clerk staff authentication and role-based permissions
- Admin dashboard structure and protected routes
- Convex schema review, server-side validation, and data access patterns
- Security review support for public forms, admin actions, and donor data

Muneeb, Raheema, and Mustaf own feature work with clear backend/frontend boundaries.

Muneeb:

- Campaign listing page, campaign detail page, and donation entry points
- Campaign filters, featured appeals, and progress displays
- Integration with existing Convex campaign data

Raheema:

- Blog/news pages, event pages, and content detail layouts
- Search/filter UI for posts and events
- Empty states, loading states, and content fallback behavior

Mustaf:

- Contact form, volunteer form, newsletter signup, and form status handling
- Impact/statistics sections and programme pages
- Validation messages and success/error user feedback

James and Ahlaam own UI, content, and QA tasks, then can move to larger page sections after review.

James:

- Footer, static charity information sections, FAQ page, and trust/safeguarding content
- Mobile spacing fixes and accessibility checks on simple components
- Image alt text, link labels, and copy cleanup

Ahlaam:

- About page, team/partners section, policy pages, and reusable content blocks
- Blog/event card polish and responsive layout checks
- Manual QA notes for mobile, tablet, and desktop

## 1 Month Delivery Plan

This plan runs from Saturday, April 25, 2026 to Friday, May 22, 2026.

### Week 1: Foundation and Page Structure

Goal: make the repo easy to work on and complete the public website skeleton.

Payment and platform tasks:

- Mikhail: own donation/payment module decisions and define the exact checkout flow.
- Mikhail: confirm Flutterwave sandbox setup, redirect URLs, webhook URLs, and payment status states.
- Yasar: audit donation/payment modules and support Mikhail with notes.
- Khalid: audit Clerk, staff roles, Convex permissions, and admin access requirements.
- Khalid: define the admin route structure and protected data access rules.

Feature tasks:

- Muneeb: build `/campaigns` and `/campaigns/[slug]` page structure.
- Raheema: build `/blog`, `/blog/[slug]`, `/events`, and `/events/[slug]` page structure.
- Mustaf: build `/contact`, `/volunteer`, `/newsletter`, and `/programmes` page structure.

Content and QA tasks:

- James: build `/faq`, footer improvements, and trust/safeguarding content sections.
- Ahlaam: build `/about`, policy page shells, and reusable content layout blocks.

Manager checkpoints:

- Approve navigation and route map.
- Review first PR from every intern.
- Confirm page ownership and coding standards.

### Week 2: Core Features and Content Workflows

Goal: connect real data and complete normal user journeys except final payment hardening.

Payment and platform tasks:

- Mikhail: implement or harden donation intent creation, amount validation, checkout redirect handling, and failed/cancelled payment states.
- Yasar: review payment changes and help test edge cases.
- Khalid: implement staff/admin layout, protected admin routes, and role checks for content management.

Feature tasks:

- Muneeb: connect campaigns to Convex data, add filters, campaign progress, and donate CTAs.
- Raheema: connect posts/events to Convex data, add search/filter behavior, and polish detail pages.
- Mustaf: connect forms to existing API routes, improve validation display, and add success/error states.

Content and QA tasks:

- James: add FAQ content, donor trust sections, accessibility labels, and responsive footer checks.
- Ahlaam: add about/policy content, partner sections, and responsive checks for cards.

Manager checkpoints:

- Review campaign, blog, event, and form flows.
- Confirm copy accuracy for charity work in Africa.
- Confirm that all public forms have validation and clear user feedback.

### Week 3: Payments, Admin, Receipts, and QA

Goal: finish high-risk flows and make the project testable end to end.

Payment and platform tasks:

- Mikhail: harden Flutterwave webhook signature verification, duplicate webhook handling, amount/currency checks, receipt creation, and audit logs.
- Yasar: help verify webhook test cases and receipt retry behavior.
- Khalid: finish admin CRUD flows for campaigns, posts, events, impact metrics, form submissions, and staff permissions.

Feature tasks:

- Muneeb: add donation UI states for one-off amount selection, campaign/fund selection, fee coverage, anonymous donation, and donor message.
- Raheema: add loading, empty, and error states across content pages; verify SEO metadata for public pages.
- Mustaf: add admin views or manager-facing lists for contact, volunteer, and newsletter submissions.

Content and QA tasks:

- James: run manual QA on mobile and desktop for homepage, campaigns, FAQ, footer, and donation entry points.
- Ahlaam: run manual QA on about, policies, blog, events, cards, and forms; log issues clearly.

Manager checkpoints:

- Test sandbox donation flow from start to receipt.
- Review webhook and payment PRs carefully.
- Confirm admin permissions cannot be bypassed from the client.

### Week 4: Production Polish and Launch

Goal: stabilize, deploy, and prepare the charity website for real donors.

Payment and platform tasks:

- Mikhail: complete production payment checklist, webhook configuration, receipt reliability checks, and final deployment approval.
- Yasar: support deployment verification and payment launch notes.
- Khalid: complete security review, environment variable review, admin role review, and backup/recovery notes.

Feature tasks:

- Muneeb: polish campaign pages, donation entry points, and campaign empty states.
- Raheema: polish blog/events, metadata, internal links, and search behavior.
- Mustaf: polish forms, impact sections, programme pages, and confirmation messages.

Content and QA tasks:

- James: final content pass for spelling, broken links, image alt text, and simple accessibility checks.
- Ahlaam: final responsive QA pass across mobile, tablet, and desktop; verify policy/about pages.

Manager checkpoints:

- Run final review on all critical flows.
- Approve production deployment.
- Confirm payment provider is in live mode only after sandbox sign-off.
- Confirm launch rollback plan and post-launch monitoring owner.

## Definition of Done

A feature is done when:

- It works on mobile and desktop.
- It handles loading, empty, success, and error states where relevant.
- It validates user input on the server.
- It does not expose secrets or trust client-only values.
- It has been reviewed by the correct support owner when it touches payments, auth, admin, donor data, or Convex schema.
- It passes the relevant build/lint checks.
- The PR includes clear testing notes.

## Launch Checklist

- Public pages complete: homepage, about, campaigns, campaign detail, programmes, blog, events, FAQ, contact, volunteer, policies.
- Donation checkout complete with Flutterwave sandbox evidence.
- Webhook verification complete and tested against duplicate/invalid events.
- Receipts generated and delivered or queued for retry.
- Admin access protected with Clerk and role checks.
- Staff can manage campaigns, content, forms, and impact data.
- Donor data is handled carefully and not exposed in public pages.
- SEO metadata and social sharing images are set for key pages.
- Accessibility basics checked: labels, headings, focus states, contrast, alt text.
- Production environment variables configured.
- Production deployment tested.
- Manager approves final release.
