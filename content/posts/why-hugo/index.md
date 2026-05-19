---
title: "Why I Chose Hugo for This Blog"
date: 2026-05-20
description: "A quick breakdown of why Hugo + GitHub Pages beats hosted blog platforms for developers."
tags: ["hugo", "static-site", "development"]
categories: ["development"]
draft: false
---

When I decided to start blogging, I had a choice to make: pick an existing platform, or build something myself.

I went with Hugo. Here's why.

## The case against hosted platforms

WordPress, Ghost, Substack — they all work. But they all come with tradeoffs:

- **Vendor lock-in.** Your content lives on someone else's infrastructure.
- **Cost.** Custom domains, advanced features, and storage add up.
- **Overhead.** Databases, plugins, updates, security patches.

For writing, I want to focus on writing. Not on managing a platform.

## Static sites are the right abstraction

A static site generator takes markdown files and produces HTML. That's it. No database, no server-side runtime, no moving parts in production.

The result is fast, cheap to host (or free on GitHub Pages), and trivially portable. If Hugo disappears tomorrow, my content is still just markdown files I can take anywhere.

## Why Hugo specifically

I considered a few options:

| Generator | Language | Build speed | Theme ecosystem |
|-----------|----------|-------------|-----------------|
| Hugo      | Go       | Excellent   | Good            |
| Eleventy  | JS       | Good        | Moderate        |
| Jekyll    | Ruby     | Slow        | Large           |
| Astro     | JS       | Good        | Growing         |

Hugo wins on build speed. A site with thousands of posts builds in under a second. That matters less for a new blog, but I like knowing the tool won't become a bottleneck.

## The Blowfish theme

[Blowfish](https://blowfish.page/) is clean, actively maintained, and has sensible defaults. Dark mode, syntax highlighting, responsive layout, search — it handles all of this without me configuring anything I don't care about.

## The deployment pipeline

Push to GitHub → GitHub Actions builds the site → deploys to GitHub Pages. The whole thing is automated and free.

```yaml
# .github/workflows/hugo.yml (simplified)
- name: Build
  run: hugo --minify

- name: Deploy
  uses: actions/deploy-pages@v4
```

Total cost: $0. Total maintenance burden: near zero.

---

If you're a developer starting a blog, this setup is hard to beat.
