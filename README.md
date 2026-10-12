# Premium Hub Bot + Website

One process: Telegram bot + customer website + PayHub webhook. Same SQLite DB.

## Railway setup

1. Push this folder to GitHub (all files in **repo root**).
2. Railway → New Project → Deploy from GitHub.
3. Add a **Volume** mounted at `/data`.
4. Set variables (Variables tab) — see list below.
5. Redeploy.

### Required variables

```
BOT_TOKEN=
PAYMENT_API_KEY=ph_...
PAYMENT_BASE_URL=https://payment-web-production.up.railway.app
ADMIN_IDS=your_telegram_id
DB_FILE=/data/ars_bot.db
RAILWAY_VOLUME_MOUNT_PATH=/data
PUBLIC_BASE_URL=https://YOUR-SERVICE.up.railway.app
TELEGRAM_BOT_USERNAME=YourBotUsername
PORT=8080
```

### Optional

```
PAYMENT_WEBHOOK_SECRET=
DEV_LOGIN_SECRET=test-secret
JWT_SECRET=long-random-string
BACKUP_DIR=/data/backups
SUPPORT_USERNAME=lostdopay
SHOP_NAME=Premium Hub
```

### PayHub Dashboard

Default notify URL:

```
https://YOUR-SERVICE.up.railway.app/api/v1/payments/webhook
```

### After deploy

- Website: `https://YOUR-SERVICE.up.railway.app/`
- Health: `/health`
- Bot works via Telegram as before
