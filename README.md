# MR REAN Telegram Bot — Railway staging

## Security status
This project is **not approved for deployment as-is**. The original archive contained a hard-coded Telegram bot token and commands/files with crash/DDoS behavior. The token fallback has been removed here, but the source still needs a manual security review and removal of any abusive functionality before publishing or deploying.

## Before any deployment
1. Revoke the exposed token in **@BotFather** and create a new token.
2. Remove or rewrite every crash, DDoS, spam, or abuse command. Do not deploy those features.
3. Test only with a private test bot and test chat.
4. Confirm the bot uses only Telegram-compliant, authorized behavior.

## Railway setup (after review)
1. Push this folder to a private GitHub repository.
2. In Railway, create a project and deploy from that repository.
3. Add the variable `TELEGRAM_BOT_TOKEN` in Railway Variables; do not put it in GitHub.
4. Deploy with the existing `npm start` command.
5. Check logs for `Bot started successfully` and verify commands in a private test chat.

Railway uses ephemeral filesystems. JSON/list files written by the bot may be lost on redeploy; use a database or persistent external storage if those files are important.
