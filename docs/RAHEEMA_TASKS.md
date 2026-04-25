# Raheema Tasks

Role: Blog, events, and content search owner  
Primary ownership: blog/news pages, event pages, content search/filter UI, metadata, and content states.

## Setup Checklist

- [ ] Read `README.md`.
- [ ] Read `docs/CODEBASE_MAP.md`.
- [ ] Pull the latest `main` branch before starting work.
- [ ] Create a feature branch using `feature/<short-description>` or `fix/<short-description>`.
- [ ] Confirm you can run `bun run build`.
- [ ] Ask Khalid before changing Convex schema or admin permissions.

## Week 1: Blog and Event Page Structure

- [ ] Review `src/components/cards/BlogCard.tsx`.
- [ ] Review `src/components/cards/EventCard.tsx`.
- [ ] Review `convex/posts.ts`.
- [ ] Review `convex/events.ts`.
- [ ] Build `/blog` page shell.
- [ ] Build `/blog/[slug]` page shell.
- [ ] Build `/events` page shell.
- [ ] Build `/events/[slug]` page shell.
- [ ] Add loading and empty states for blog and events.
- [ ] Open a PR for blog and event page structure.

## Week 2: Content Data and Filters

- [ ] Connect `/blog` to real Convex post data.
- [ ] Connect `/blog/[slug]` to real Convex post data.
- [ ] Connect `/events` to real Convex event data.
- [ ] Connect `/events/[slug]` to real Convex event data.
- [ ] Display titles, excerpts, published dates, tags, categories, event dates, and locations where available.
- [ ] Add search/filter UI for posts.
- [ ] Add search/filter UI for events.
- [ ] Keep search or filter state in the URL where practical.
- [ ] Add clear empty states for no matching content.
- [ ] Open a PR for content data and filters.

## Week 3: States and SEO

- [ ] Add polished loading states for blog listing.
- [ ] Add polished loading states for event listing.
- [ ] Add clear error states for failed content loading.
- [ ] Add metadata for blog listing.
- [ ] Add metadata for blog detail pages.
- [ ] Add metadata for event listing.
- [ ] Add metadata for event detail pages.
- [ ] Check heading hierarchy on all blog and event pages.
- [ ] Check image alt text on all blog and event cards.
- [ ] Open a PR for states and metadata.

## Week 4: Polish and Internal Links

- [ ] Polish blog listing layout on mobile.
- [ ] Polish blog listing layout on desktop.
- [ ] Polish event listing layout on mobile.
- [ ] Polish event listing layout on desktop.
- [ ] Add internal links from homepage cards to detail pages.
- [ ] Check blog and event links are not broken.
- [ ] Check cards handle long titles and excerpts.
- [ ] Run manual QA for blog and events on mobile, tablet, and desktop.
- [ ] Open final polish PR.

## PR Checklist

- [ ] PR explains what changed.
- [ ] PR explains why it changed.
- [ ] PR explains how to test it.
- [ ] `bun run build` passes.
- [ ] Blog and event pages work on mobile and desktop.
- [ ] Mikhail is requested as final reviewer.
