# comments

Shared GitHub Discussions backend for comments across Alan Synn websites.

Comments are rendered with giscus and stored as GitHub Discussions.

## Mapping contract

Every embedding site must use:

mapping = specific

with the term:

<site-key>:<content-kind>:<stable-content-id>

Examples:

- alansynn:blog:example-post
- project-x:docs:introduction

Do not use pathname as the shared-repository mapping strategy because
different sites may have identical paths.

## Origins

Allowed embedding origins are explicitly listed in `giscus.json`.

When adding a new website:

1. Add its exact canonical origin to `giscus.json`.
2. Choose a unique permanent site key.
3. Use the shared `Comments` Discussion category.
4. Use `specific` mapping.

The `Comments` category must stay in **Announcement** format and must not
be made answerable (never Q&A or Poll): the Announcement format means
visitors cannot create top-level Discussions in this repo — giscus
creates every thread itself from a `specific` term — while replies
(comment posting) remain open. Changing the format would let anyone
open arbitrary Discussions here.

5. Never reuse another site's mapping namespace.

Avoid wildcard origin rules unless there is a concrete requirement.

## Moderation

All comments are stored in GitHub Discussions.

Moderate comments directly through GitHub.

This repository contains no application backend and no user database.
