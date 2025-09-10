# StudyTorrent Telegram Bot (Final)

Production-ready Telegram bot using python-telegram-bot v21+, long polling, Replit keep-alive, strict dual-channel gate, full button menus (Class → Batch → Resources), and a runtime Admin Menu to edit everything via SQLite.

## Replit Setup (10 minutes)
1) Add files and open the Repl.
2) Secrets:
   - TELEGRAM_BOT_TOKEN = <bot token>
   - OWNER_USER_ID = <numeric owner id>
   - MAIN_CHANNEL_ID = @TeachTorrent
   - DISCUSSION_CHANNEL_ID = @TeachTorrentChat
   - BOT_MODE = production
3) Run the Repl; web tab should show “StudyTorrent bot alive”.
4) UptimeRobot: HTTP monitor to https://<your-repl>.repl.co every 5 minutes.

## Features
- Join Gate: Users must be in @TeachTorrent and @TeachTorrentChat; “Verify” re-check button included.
- Menus: Tap-only navigation: Classes (9/10/11/12) → Batches (editable) → Lectures/Notes/DPPs/Tests.
- Admin Menu: Owner (and optional channel admins) can add/rename/delete/reorder classes, batches, and resource labels; manage commands visibility and order.
- Admin Tools: /dm all <message> and /dm <chat_id> <message> with safe rate limits and failure pruning.

## Commands
- /start, /help, /ping, /about, /admin, /dm

## Database
- SQLite at data/studytorrent.db; auto-created on first run; DB tables for classes, batches, resources, users, commands, settings, logs.

## Notes
- For large broadcasts, consider chunking and backoff; failed chat_ids are pruned.
- For webhooks/serverless later, switch from run_polling to setWebhook approach.
