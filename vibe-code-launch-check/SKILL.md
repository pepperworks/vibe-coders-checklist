---
name: vibe-code-launch-check
description: Audit a vibe-coded app for the production basics people skip before launch. Use when someone asks if their app is ready to ship, wants a launch or production readiness review, or asks "what did I forget?"
---

# Vibe Code Launch Check

Audit the app against the checklist below and report what's done, what's missing, and what you couldn't verify.

## How to run the audit

1. Look at the actual codebase, config, and deployment setup before marking anything. Check for test folders, CI config files (e.g. `.github/workflows`), env handling, `robots.txt`, error pages, and so on.
2. Mark every item with one of:
   - **Done**: you found evidence in the code or config. Say where.
   - **Missing**: you looked and it isn't there.
   - **Can't verify**: it lives outside the repo (billing dashboards, DNS, backups, uptime tools). Say so and ask the user to confirm.
3. Never mark something Done based on a guess, a file name alone, or what the user assumes. If you didn't open it, it's not verified.
4. Lead the report with the high-risk tier. Those are the items that cost money, lose data, or leak secrets.
5. After the report, offer to fix the missing items, highest risk first. Don't start fixing until the user says go.
6. Skip items that clearly don't apply (e.g. no AI section for an app with no model calls, no auth items for a static site) and say you skipped them.

## The checklist

### High risk (check these first)
- Spend caps and billing alerts set on every paid API (especially LLM APIs)
- Database is backed up
- A restore from backup has actually been tested
- Rollback plan exists for bad deploys
- No secrets committed to the repo (check git history, not just current files)
- Any keys that were ever exposed have been rotated
- Rate limiting on public endpoints
- Auth checked on every endpoint, not just the UI

### Testing and deploys
- CI/CD pipeline
- Unit tests
- Smoke tests
- Regression tests
- Staging environment separate from production
- Dependency audit (known vulnerabilities, outdated packages)

### Monitoring
- Alerting
- Error tracking
- Logging
- Performance monitoring
- Uptime monitoring
- Analytics

### Infrastructure
- Custom domain and SSL
- Email auth configured (SPF, DKIM, DMARC) so transactional email doesn't land in spam
- Image optimization
- Caching

### AI-specific (only if the app calls a model)
- Evals, not just manual vibe checks
- Prompt injection testing
- Fallback when the model API is down or slow
- Token limit and context overflow handling

### Users and legal
- Accessibility (keyboard nav, screen readers, contrast)
- Privacy policy and terms
- Cookie consent
- Users can delete their account and data
- Password reset works
- Email verification works

### Polish
- Real 404, 500, empty, and loading states
- OG images and favicon
- SEO and AEO validated (sitemap, robots.txt, structured data)
- Tested on multiple devices
- Tested on slow networks
- README so future you knows how it works

## Report format

Start with a one-line verdict (e.g. "Not ready: 3 high-risk gaps"). Then a table or grouped list per section with Done / Missing / Can't verify and a short note on each. End with the top 3 things to fix first.
