# tg-search-bot

## Project structure

```
telegram-search-bot/
  indexer/        — Telethon indexer + channel discovery
  bot/            — Telegram search bot UI
  ranker/         — Message ranking job
  data/           — SQLite database (gitignored)
  database.py     — Shared DB layer
  .env            — Shared credentials (API keys, DB path)
```

## Setup

```bash
pip install -r requirements.txt

# Shared credentials (Telegram API + DB path)
cp .env.example .env

```

## Run

```bash
# Terminal 1 — index messages from all your Telegram groups
python indexer/indexer.py

# Terminal 2 — search bot UI
python bot/bot.py

# Terminal 3 — ranking job (optional)
python ranker/ranker.py

# Terminal 4 — LLM extractor: fills price/currency/location/service_type (optional)
python extractor/extractor.py
```

## Discover channels

```bash
python indexer/discover.py "jobs malaysia"
python indexer/discover.py "food kuala lumpur"
```

Searches Telegram for public channels matching the keyword. Copy results into `PUBLIC_CHATS` in `indexer/.env.indexer`.

## Bot commands

| Command | Description |
|---|---|
| `/search <query>` | Full-text search across indexed messages |
| `/stats` | Show total messages indexed |
