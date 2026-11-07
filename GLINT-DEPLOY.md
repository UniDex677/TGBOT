# GLINT — Render deployment

The complete mini-app source is stored in `glint-source.tar.br.b64` (a Brotli-compressed tar archive encoded as base64). During a Render build the `render.yaml` build command extracts it and runs `npm install`. This is a self-contained deployment bundle; the original project can also be downloaded as `GlintTelegramGame.zip` from ChatGPT.

Select branch **glint-game** on GitHub, then deploy via Render using `render.yaml` (or a Node Web Service using its commands). Set `DATABASE_URL` to the **internal connection string** for Render PostgreSQL `glint-game-db` (Kwilzz workspace). Obtain `TELEGRAM_BOT_TOKEN` from @BotFather; do not commit it. Keep `NODE_ENV=production` and set `PUBLIC_URL` to the actual service HTTPS URL. The backend automatically creates two independent `glint_*` tables and configures the Telegram webhook when both Bot token and public URL are present.

`GET /health` must return `{"ok":true,"storage":"postgres"}` once running with a database. The database is free-tier and has an expiry date; replace/upgrade appropriately to retain progress beyond the free period.

No cash payments, crypto betting, deposit, or withdrawal are implemented; all points are virtual and nonredeemable.
