# The Vibe Coder's Production Ready Checklist

Hi Friend!

So many of you asked for the checklist of what to do to make a production ready app, so I put it here for easy copy and paste.

I've spent 10 years building apps and working on large B2B SaaS teams that ship some of the products you use everyday. Lately I've seen some pretty stressful newbie mistakes with vibe coded apps and I want everyone to be able to build quality products that make their users happy.

This list isn't exhaustive and doesn't include things that you need to make an "Enterprise Grade" app, so your mileage may vary.

DM me if you have questions or want me to explain anything else.

Happy Building!

💕 xo Paige

## How to use it

The checklist is packaged as a Claude skill. Claude looks at your actual code and config, marks each item Done, Missing, or Can't verify, and puts the high-risk stuff (money, data loss, leaked secrets) first.

**Claude Code:** copy the `vibe-code-launch-check` folder into `~/.claude/skills/` (or `.claude/skills/` in your project). Then ask Claude "is my app ready to launch?"

**Claude.ai:** zip the `vibe-code-launch-check` folder and upload it as a skill.

**Anything else:** paste the contents of `SKILL.md` into your prompt.

The full checklist is in [`vibe-code-launch-check/SKILL.md`](vibe-code-launch-check/SKILL.md).

## Skill too much for you? Here is the list

- add CI/CD
- add unit tests
- add smoke tests
- add regression tests
- validate SEO and AEO (sitemap, robots.txt, structured data)
- add alerting
- include performance monitoring
- create analytics
- check auth on every endpoint
- run a dependency audit
- test it on multiple devices
- test it on slow networks
- set spend caps and billing alerts
- back up your database
- actually test a restore
- have a rollback plan for bad deploys
- keep secrets out of the repo
- rotate any keys that leaked
- add rate limiting
- add error tracking
- add logging
- set up uptime monitoring
- create a staging environment
- set up your custom domain and SSL
- configure email auth (SPF/DKIM/DMARC)
- build real 404, 500, empty, and loading states
- write evals
- test for prompt injection
- add a fallback for when the model API goes down
- handle token limits and context overflow
- make it accessible
- add a privacy policy and terms
- add cookie consent
- let users delete their account and data
- make sure password reset works
- make sure email verification works
- add OG images and a favicon
- optimize images
- set up caching
- write a README so future you knows how it works

## License

Apache 2.0
