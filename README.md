# Cloud Mail

Self-hosted email system running on Cloudflare Workers — a complete webmail platform at the edge.

## Stack

- **Cloudflare Workers** — serverless runtime
- **D1** (SQLite) — users, emails, settings
- **KV** — sessions & cache
- **R2** — attachment storage
- **Workers AI** — built-in AI features (@cf/meta/llama-3.1-8b-instruct-fast)
- **Resend** — outbound email delivery (token configured via D1 settings table)

## Deploy

1. `npm i -g wrangler`
2. Edit `wrangler.toml`: set your D1 database id, KV namespace id, R2 bucket, account fields, and `jwt_secret`
3. `wrangler deploy`
4. Point your domain's MX + email routing to the worker

## Features

- Multi-user webmail with attachments
- Admin panel & user roles
- Email forwarding rules
- Telegram notifications (optional)
- Built-in AI helpers
- OAuth login (GitHub / Google optional)

Based on the open-source cloud-mail project, customized for zenext.web.id.
