# docker-KoalaBot
Docker build script for KoalaBot


## Usage

Here are some example snippets to help you get started creating a container.

### docker-compose (recommended, [click here for more info](https://docs.linuxserver.io/general/docker-compose))

```yaml
---
version: "3.9"
services:
  transmission:
    image: jaydwee/KoalaBot
    container_name: KoalaBot
    environment:
      - DISCORD_TOKEN = bot_token
      - BOT_OWNER = owner_user_id #optional
      - ENCRIPTION = boolean #optional
      - SQLITE_KEY = key #optional
      - TWITCH_TOKEN = twitch_application_token #optional (TwitchAlert)
      - TWITCH_SECRET = twitch_application_secret #optional (TwitchAlert)
      - GMAIL_EMAIL = example@gmail.com #optional (Verify)
      - GMAIL_PASSWORD = example_password123 #optional (Verify)
    volumes:
      - <path to data>:/config
    restart: unless-stopped
```

### docker cli ([click here for more info](https://docs.docker.com/engine/reference/commandline/cli/))

```bash
docker run \
  --name=Koala \
  -e DISCORD_TOKEN=bot_token \
  -e BOT_OWNER=owner_user_id `#optional` \
  -e ENCRIPTION=boolean `#optional` \
  -e SQLITE_KEY=key `#optional` \
  -e TWITCH_TOKEN=twitch_application_token `#optional (TwitchAlert)` \
  -e TWITCH_SECRET=twitch_application_secret `#optional (TwitchAlert)` \
  -e GMAIL_EMAIL=example@gmail.com `#optional (Verify)` \
  -e GMAIL_PASSWORD=example_password123 `#optional (Verify)` \
  -v <path to data>:/config \
  --restart unless-stopped \
  jaydwee/KoalaBot
```