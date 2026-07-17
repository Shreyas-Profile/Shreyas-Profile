# Shreyas Pavuluri

Building **[Paperloft](https://paperloft.uk)** — an AI-agent platform — and the
**Globalion** skills marketplace that powers it. Every skill is a live MCP
server anyone can plug into Claude Desktop, Cursor, or their own agent.

## Live skills

| Skill | What it does | Live | Registry |
|---|---|---|---|
| [docs-mcp](https://github.com/globalion/docs-mcp) | Vector RAG over Word/Excel/PDF/PowerPoint with page citations. Break-even Stripe billing. | [docs.regiq.in](https://docs.regiq.in) | `io.github.Shreyas-Profile/docs-mcp` |
| [cron-mcp](https://github.com/globalion/cron-mcp) | Cron-as-a-service — schedule prompts on any cron expression, get webhooks when they fire. | [cron.regiq.in](https://cron.regiq.in) | `io.github.Shreyas-Profile/cron-mcp` |
| [browser-mcp](https://github.com/globalion/browser-mcp) | Real Chrome browser as an MCP skill. Per-user isolation, encrypted credential vault. | [browser.regiq.in](https://browser.regiq.in) | `io.github.Shreyas-Profile/browser-mcp` |

## The platform that ties them together

**[paperloft-assist](https://github.com/Shreyas-Profile/paperloft-assist)** — an
AI-agent platform at [paperloft.uk](https://paperloft.uk). Sign in with Google,
toggle any skill on, and Paperloft auto-provisions you a private tenant on that
skill's server. Data stays isolated per user; billing rolls up to Paperloft's
shared pool.

Also runs internal skills: `browser_*` (drives the hosted Chrome), `cron_*`
(scheduled prompts fire back through the chat), `docs_*` (RAG search), and
Nova-reminders (WhatsApp/Telegram delivery, prescription intake, medication
schedules).

## Tech I reach for

**TypeScript + Next.js 16 · Prisma + Postgres (pgvector) · Playwright · Docker
+ Hetzner · Cloudflare Tunnels · Stripe · OpenRouter (Anthropic / Google /
OpenAI) · Model Context Protocol**

## The pattern I've been iterating on

Every new skill ships with:

1. Google-only sign-in (one throttle point)
2. Fair-use caps per key (advertised on the landing page)
3. `Platform` + `PlatformPool` primitives — aggregator platforms can
   provision sub-accounts + fund them from a shared pool (Twilio Subaccounts
   / OpenAI Organizations model)
4. Published to the [official MCP Registry](https://registry.modelcontextprotocol.io)
   + Glama

Same rails for every skill; the only bit that changes per skill is what it
does with your data once it's in.

---

*15 years old · building this to learn how to run real infra with real
users · reachable at shreyas.pavuluri@gmail.com*
