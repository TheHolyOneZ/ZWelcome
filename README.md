# ZWelcome
ZWelcome is a comprehensive Discord bot cog that provides advanced welcome message functionality with customizable embeds, auto-role assignment, analytics, and extensive configuration options. All data is stored in per-guild SQLite databases with automatic backup support.
> 💡 **Built for the Zygnal Ecosystem — to download and use this extension, you must be part of the Zygnal Ecosystem.**  
> This extension (cog) is part of the **Zygnal Ecosystem** and is only available through its supported platforms.  
> You can use it with:  
> - The **[Discord Bot Framework](https://github.com/TheHolyOneZ/discord-bot-framework)** — ideal for developers who want full control and flexibility *(includes an integrated extension marketplace)*, or  
> - The **[ZygnalBot](https://zygnalbot.de)** — a prebuilt, plug-and-play Discord bot *(also includes an integrated extension marketplace)*.  
>
> Browse and install extensions at [zygnalbot.com/extension](https://zygnalbot.com/extension).  
> For help or community discussions, join us on Discord: [discord.gg/sgZnXca5ts](https://discord.gg/sgZnXca5ts)
# ZWelcome - Advanced Discord Welcome System
**A powerful, feature-rich Discord bot extension for automated member welcomes**
Created by **TheHolyOneZ (TheZ)**
## Overview
ZWelcome is a comprehensive Discord bot cog that provides advanced welcome message functionality with customizable embeds, auto-role assignment, analytics, and extensive configuration options. All data is stored in per-guild SQLite databases with automatic backup support.
## Key Features
### 🎉 Welcome Messages
- **Customizable Embed Templates** - Create beautiful welcome messages with full embed support
- **Dynamic Placeholders** - Personalize messages with user info, server stats, and timestamps
- **Multiple Templates** - Store and manage multiple template configurations
- **Priority System** - Control which template is used with priority rankings
- **Live Preview** - Test your welcome messages before enabling them
### 📺 Channel Management
- **Flexible Channel Setup** - Configure any text channel as your welcome destination
- **Permission Checking** - Automatic validation of bot permissions
- **Test Messages** - Send test welcomes to verify your setup
- **Fallback Support** - Configure backup channels if primary is unavailable
### 🎭 Auto-Role Assignment
- **Instant Role Assignment** - Automatically assign roles to new members
- **Multiple Roles** - Configure unlimited auto-roles
- **Role Hierarchy** - Respects Discord's role hierarchy system
- **Permission Validation** - Checks for proper role management permissions
- **Failed Assignment Logging** - Track and review role assignment issues
### 📊 Analytics & Logging
- **Welcome Tracking** - Log every member join with timestamps
- **Statistics Dashboard** - View 7-day, 30-day, and yearly statistics
- **Invite Tracking** - Track which invite code was used (when permissions allow)
- **Recent Welcome History** - Review the last 10 members who joined
- **Dedicated Log Channel** - Send detailed join logs to a separate channel
- **Member Count Tracking** - Monitor server growth over time
### 💾 Data Management
- **Per-Guild Databases** - Each server has its own SQLite database
- **Automatic Backups** - Daily automatic backups of all guild data
- **Backup Retention** - Configurable backup history (default: 7 backups)
- **Manual Backup** - Trigger backups on-demand
- **Data Persistence** - All configurations survive bot restarts
### ⚙️ Configuration System
- **Interactive GUI Panel** - User-friendly button-based configuration
- **Multi-Page Interface** - Organized settings across 5 dedicated pages
- **Real-Time Updates** - Changes reflect immediately in the panel
- **Permission Management** - Granular control over who can configure
- **Rate Limiting** - Configurable cooldown between welcome messages
## Configuration Panel
Access the main configuration panel with `/zwelcome`. The panel consists of 5 pages:
### 1️⃣ Main Dashboard
**Overview of your welcome system status**
- **System Toggle** - Enable/disable the welcome system
- **Quick Stats** - View active channel, template count, and monthly welcomes
- **Preview Message** - See how your current template looks
- **Backup Data** - Manually trigger a database backup
- **Status Indicators** - Visual confirmation of system state
### 2️⃣ Channel Configuration
**Manage where welcome messages are sent**
- **Set Welcome Channel** - Configure the primary welcome destination
- **Channel Validation** - Automatic permission and type checking
- **Send Test Message** - Preview your welcome in the actual channel
- **Permission Alerts** - Warnings if bot lacks required permissions
### 3️⃣ Message Templates
**Create and manage welcome message templates**
#### Template Creation Methods:
**Modal Creation (Quick)**
- Single form with all fields
- Instant template creation
- Best for simple templates
**Chat-Based Creation (Guided)**
- Step-by-step interactive guide
- 5-minute timeout per step
- Detailed examples and tips
- Real-time guidance and validation
- Preview on completion
#### Template Components:
- **Template Name** - Unique identifier for the template
- **Embed Title** - Optional header text
- **Embed Description** - Main message content (required)
- **Embed Color** - Hex color code for embed border
- **Embed Footer** - Optional footer text
- **Priority System** - Control template selection order
#### Available Placeholders:
- `{user}` - Mentions the user (@Username)
- `{user_name}` - Username only
- `{user_id}` - User's Discord ID
- `{server_name}` - Server name
- `{member_count}` - Total member count
- `{join_time}` - Relative timestamp (e.g., "5 minutes ago")
- `{join_time_raw}` - Full timestamp with timezone
#### Markdown Support:
- `**bold**` - **Bold text**
- `*italic*` - *Italic text*
- `__underline__` - __Underlined text__
- `~~strikethrough~~` - ~~Strikethrough text~~
- `[text](url)` - Clickable hyperlinks
- `> quote` - Quoted text
- `- bullet` - Bullet points
#### Template Management:
- **View Templates** - See all configured templates with priorities
- **Delete Templates** - Remove templates via dropdown menu
- **Preview Templates** - Generate live previews with your data
- **Edit Templates** - Delete and recreate to modify
### 4️⃣ Auto-Role Configuration
**Automatically assign roles to new members**
- **Add Auto-Role** - Configure roles for automatic assignment
- **Remove Auto-Role** - Disable auto-assignment for specific roles
- **Role Validation** - Checks role hierarchy and permissions
- **Active Roles List** - View all currently configured auto-roles
- **Role Status** - Identifies deleted roles automatically
#### Requirements:
- Bot must have "Manage Roles" permission
- Bot's role must be higher than auto-roles in hierarchy
- Roles must exist in the server
### 5️⃣ Logging & Analytics
**Track and monitor member joins**
#### Logging Features:
- **Toggle Logging** - Enable/disable join logging
- **Set Log Channel** - Configure dedicated log channel
- **Detailed Join Logs** - User info, timestamps, invite codes, avatar
- **Member Count Updates** - Track server growth in logs
#### Statistics:
- **7-Day Overview** - Recent join activity with daily average
- **30-Day Overview** - Monthly trends and patterns
- **Yearly Totals** - Long-term growth tracking
- **Recent Welcomes** - Last 10 members who joined
- **Detailed Stats** - In-depth analytics dashboard
## Commands
### `/zwelcome`
**Opens the interactive configuration panel**
- **Permission Required:** Manage Server OR Manager Role (configurable)
- **Timeout:** 10 minutes of inactivity
- **Ephemeral:** No, visible to all (configurable per interaction)
### `/zwstats`
**Displays welcome statistics**
- Shows 7-day, 30-day, and yearly welcome counts
- Lists 5 most recent welcomes
- Daily average calculations
- Visual statistics embed
### `/zwconfig [setting] [value]`
**Advanced configuration options**
#### Available Settings:
**`rate_limit_seconds`** - Cooldown between welcome messages
- Range: 0-60 seconds
- Default: 5 seconds
- Prevents spam during mass joins
**`backup_retention_count`** - Number of backups to keep
- Range: 1-30 backups
- Default: 7 backups
- Older backups are automatically deleted
#### Usage Examples:
- `/zwconfig` - View current settings
- `/zwconfig rate_limit_seconds 10` - Set 10-second cooldown
- `/zwconfig backup_retention_count 14` - Keep 14 backups
## Interactive Elements
### Buttons
**Navigation Buttons (Top Row)**
- 🏠 Main - Dashboard overview
- 📺 Channel - Channel configuration
- ✉️ Message - Template management
- 🎭 Roles - Auto-role settings
- 📊 Logs - Analytics and logging
**Action Buttons (Contextual)**
- Toggle System - Enable/disable welcome system
- Preview Message - See template preview
- Backup Data - Manual backup trigger
- Set Welcome Channel - Configure channel
- Send Test Message - Test in actual channel
- Add Template (Modal) - Quick template creation
- Add Template (Chat) - Guided template creation
- Delete Template - Remove templates
- Add Auto-Role - Configure role assignment
- Remove Auto-Role - Disable role assignment
- Toggle Logging - Enable/disable logging
- Set Log Channel - Configure log destination
- Detailed Stats - View in-depth analytics
### Modals
**Quick input forms for configuration**
- Channel Setup Modal - Enter channel ID
- Template Creation Modal - Quick 5-field template form
- Add Role Modal - Enter role ID to assign
- Remove Role Modal - Enter role ID to remove
- Log Channel Modal - Enter log channel ID
### Dropdowns
**Template Deletion Menu**
- Lists up to 25 templates
- Shows template name and priority
- Instant deletion on selection
## Guided Template Creation
The **Chat-Based Template Creation** provides a step-by-step interactive experience:
### Step-by-Step Process:
**Step 1: Template Name**
- Unique identifier for your template
- No spaces recommended (use hyphens/underscores)
- Must not conflict with existing templates
**Step 2: Embed Title**
- Optional header text
- Supports all placeholders
- Can be skipped
**Step 3: Embed Description**
- Required main content
- Full markdown support
- All placeholders available
- Multi-line supported
**Step 4: Embed Color**
- Hex color code without #
- Pre-defined Discord colors suggested
- Defaults to Discord blue if invalid
- Can be skipped for default
**Step 5: Embed Footer**
- Optional footer text
- Supports all placeholders
- Bot signature automatically added
- Can be skipped
### Guided Creation Features:
- **5-minute timeout per step** - Plenty of time to craft your message
- **Cancel anytime** - Type "cancel" to stop
- **Skip optional fields** - Type "skip" for title/color/footer
- **Live validation** - Instant feedback on inputs
- **Emoji reactions** - Visual confirmation of each step
- **Detailed examples** - Suggestions and templates provided
- **Real-time preview** - See your template after completion
- **Progress tracking** - Visual indicator of current step
## Automatic Features
### On Member Join:
1. **System Check** - Verifies welcome system is enabled
2. **Rate Limit Check** - Respects configured cooldown
3. **Channel Validation** - Confirms channel exists and bot has permissions
4. **Template Generation** - Creates personalized welcome embed
5. **Message Sending** - Posts welcome to configured channel
6. **Invite Tracking** - Attempts to identify which invite was used
7. **Database Logging** - Records join event with metadata
8. **Log Channel Update** - Posts detailed log if logging enabled
9. **Auto-Role Assignment** - Assigns all configured roles
10. **Error Handling** - Gracefully handles any failures
### Invite Tracking:
- Automatically caches server invites on bot load
- Updates cache when invites are created/deleted
- Compares invite usage to identify which was used
- Requires "Manage Server" permission
- Logged to database and log channel when available
### Daily Tasks:
- **Automatic Backups** - All guild databases backed up daily
- **Backup Cleanup** - Old backups deleted per retention settings
- **Error Logging** - Failed backups logged to console
## Permissions
### Required Bot Permissions:
- **Send Messages** - Post welcome messages
- **Embed Links** - Display rich embeds
- **Read Message History** - For message context
- **Manage Roles** - Auto-role assignment (optional)
- **Manage Server** - Invite tracking (optional)
### Required User Permissions:
**For `/zwelcome` and `/zwconfig`:**
- **Manage Server** permission OR
- Assigned "Manager Role" (configurable per guild)
**For `/zwstats`:**
- No special permissions required
## Database Structure
Each guild has a dedicated SQLite database stored at:
```
data/zwelcome/{guild_id}.sqlite
```
### Tables:
**`config`** - Key-value pairs for guild settings
- enabled status
- welcome channel ID
- logging settings
- rate limits
- backup retention
**`templates`** - Welcome message templates
- Template name
- JSON content (title, description, color, footer)
- Condition rules
- Priority ranking
**`welcome_log`** - Historical join records
- User ID and username
- Join timestamp
- Invite code used
- Template applied
**`role_rules`** - Auto-role configurations
- Role ID
- Condition type
- Condition value
### Backups:
Stored at: `data/zwelcome/backups/{guild_id}_{timestamp}.sqlite`
- Created daily automatically
- Can be triggered manually
- Retention configurable (default: 7)
- Includes complete guild data
## Session Handling
### Configuration Panel Sessions:
- **Timeout:** 600 seconds (10 minutes)
- **User Restriction:** Only authorized users can interact
- **State Preservation:** Current page maintained during interactions
- **Multi-User Safe:** Each user has independent session
### Guided Creation Sessions:
- **Timeout:** 300 seconds (5 minutes) per step
- **Cancellation:** Type "cancel" at any step
- **Lock System:** One creation per user at a time
- **Progress Tracking:** Visual updates throughout process
- **Auto-Cleanup:** Locks removed on completion/timeout/error
### Cache Management:
- **Invite Cache:** Refreshed on create/delete events
- **Config Cache:** Loaded once per guild, updated on changes
- **Template Cache:** Loaded from database on demand
- **Cooldown Cache:** In-memory tracking of last welcome times
## Rate Limiting
**Welcome Message Cooldown:**
- Default: 5 seconds between welcomes
- Configurable: 0-60 seconds
- Per-guild basis
- Prevents spam during mass joins or raids
- Cooldown timer stored in memory (resets on bot restart)
**Purpose:**
- Avoid rate limits from Discord API
- Prevent message spam in welcome channel
- Reduce database write load during mass joins
- Improve performance during high-traffic periods
## Error Handling
### Graceful Degradation:
- **Missing Channel:** Welcome skipped, no error
- **Missing Permissions:** Welcome skipped, no error
- **Invalid Template:** Default handling, no crash
- **Role Assignment Failure:** Logged, other roles still assigned
- **Database Error:** Logged to console, operation skipped
### User Feedback:
- **Permission Warnings:** Ephemeral alerts in config panel
- **Validation Errors:** Clear error messages with solutions
- **Setup Guidance:** Helpful tips and requirements shown
- **Status Indicators:** Visual confirmation of settings
## Best Practices
### Template Design:
1. **Keep it concise** - Short, welcoming messages work best
2. **Use placeholders** - Personalize with user/server info
3. **Test thoroughly** - Use preview and test message features
4. **Consider markdown** - Bold key information
5. **Set appropriate colors** - Match your server theme
### Channel Setup:
1. **Dedicated channel** - Create a welcome-specific channel
2. **Slow mode** - Consider enabling slow mode
3. **Channel topic** - Explain it's automated
4. **Pin examples** - Pin a test message as reference
### Auto-Roles:
1. **Essential roles only** - Don't overwhelm new members
2. **Check hierarchy** - Ensure bot role is high enough
3. **Test assignments** - Use test accounts to verify
4. **Monitor logs** - Check for failed assignments
### Logging:
1. **Private log channel** - Don't let everyone see logs
2. **Enable logging** - Valuable for moderation
3. **Review regularly** - Check for patterns
4. **Track invites** - Identify recruitment sources
### Maintenance:
1. **Regular backups** - Use manual backup before major changes
2. **Review templates** - Update seasonal or outdated content
3. **Check statistics** - Monitor server growth trends
4. **Update configs** - Adjust rate limits as server grows
## Troubleshooting
### Welcome Messages Not Sending:
- Verify system is enabled (Main page)
- Check welcome channel is set (Channel page)
- Confirm bot has Send Messages permission
- Test with "Send Test Message" button
- Check rate limit isn't preventing sends
- Verify at least one template exists
### Auto-Roles Not Assigning:
- Confirm bot has Manage Roles permission
- Check bot's role is higher than auto-roles
- Verify roles still exist in server
- Review log channel for error messages
- Test with a single role first
### Configuration Panel Not Responding:
- Check you have Manage Server permission
- Verify you have Manager Role if configured
- Try running `/zwelcome` again
- Check bot's permissions in channel
- Ensure bot is online and responsive
### Template Not Showing:
- Verify template was saved (check Message page)
- Use Preview button to test
- Check for JSON parsing errors
- Delete and recreate if corrupted
- Review placeholder syntax
### Statistics Missing:
- Ensure logging is enabled
- Check data/zwelcome folder exists
- Verify database file for your guild exists
- Try running `/zwstats` command
- Check for database permission issues
## Support & Feedback
For issues, questions, or feature requests:
1. Use the thumbs down button on bot responses
2. Contact **TheHolyOneZ** (Creator)
3. Visit **zygnalbot.com/extension/**
4. Check the official Zygnalbot Marketplace
## License
This extension is licensed under a **Custom License Agreement**.
Key restrictions:
- ❌ No modification of code
- ❌ No removal of creator attribution
- ❌ No redistribution or resale
- ❌ No code reuse in derivative works
- ✅ Private hosting allowed
- ✅ Reading for educational purposes
- ✅ Bug reporting (fixes by creator only)
See the full license in the source file for complete terms.
---
**ZWelcome** - Professional welcome automation for Discord servers
*Made with ❤️ by TheHolyOneZ (TheZ)*
