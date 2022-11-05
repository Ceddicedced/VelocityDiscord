# VelocityDiscord

Velocity global chat/discord bridge

Default config generated on startup:

```toml
# Don't change this
config_version = "1.4"

[discord]
# Bot token from https://discordapp.com/developers/applications/
token = "TOKEN"
# Channel ID to send Minecraft chat messages to
channel = "000000000000000000"

# Show messages from bots in Minecraft chat
show_bot_messages = false
# Show clickable links for attachments in Minecraft chat
show_attachments_ingame = true

# OPTIONAL - Use a Discord webhook to have the bot use the player's username and avatar when sending messages
# Requires a webhook URL to be set below
use_webhook = false

[discord.webhook]
# Full webhook URL to send more fancy Minecraft chat messages to
webhook_url = ""
# Full URL of an avatar service to get the player's avatar from
# Placeholders {uuid} and {username} are available
avatar_url = "https://crafatar.com/avatars/{uuid}?overlay"
# The format of the webhook's username
# Placeholders {username} and {server} are available
webhook_username = "{username}"

# Minecraft > Discord message formats
# Uses the same formatting as the Discord client
[discord.chat]
# The format set in the following key "discord.chat.message" is ignored when a webhook is used
# Placeholders {username}, {server}, and {message} are available
message = "{username}: {message}"
# Placeholders {username} and {server} are available
join_message = "**{username} joined the game**"
leave_message = "**{username} left the game**"
# Placeholders {username}, {current}, and {previous} are available
server_switch_message = "**{username} moved to {current} from {previous}**"
# Placeholders {username} and {death_message} are available
death_message = "**{username} {death_message}**"
# Placeholders {username}, {advancement_title}, and {advancement_description} are available
advancement_message = "**{username} has made the advancement __{advancement_title}__**\n_{advancement_description}_"

[discord.commands.list]
enabled = true
server_format = "[{server_name} {online_players}/{max_players}]"
player_format = "- {username}"
no_players = "No players online"
codeblock_lang = "asciidoc"

# Discord > Minecraft message formats
# Uses XML-like formatting with https://docs.adventure.kyori.net/minimessage#format
[minecraft]
discord_chunk = "<dark_gray>[<{discord_color}>Discord<dark_gray>]<reset>"
username_chunk = "<{role_color}><hover:show_text:{username}#{discriminator}>{nickname}</hover><reset>"
message = "{discord_chunk} {username_chunk}<dark_gray>: <reset>{message} {attachments}"
attachments = "<dark_gray><click:open_url:{url}>[<{attachment_color}>Attachment<dark_gray>]</click><reset>"
# Colors for the <{discord_color}> and <{attachment_color}> tags
discord_color = "#7289da"
attachment_color = "#4abdff"
```
