# Connecting Your Real Apps (MCPs)

MCPs (Model Context Protocol) are plugins that let Claude talk to your actual apps — calendar, email, Notion, etc. Without them, Claude is smart but isolated. With them, it can actually DO things.

## How MCPs Work

1. You install an MCP once
2. It asks you to authorize access (like logging into Google)
3. After that, Claude can read and write to that app every session
4. You control what it can access — it only has the permissions you grant

## Recommended Setup Order

Start with one. Add more as you need them.

### 1. Google Calendar (Most Useful First)

Lets Claude read your schedule, create events, and check for conflicts.

**What it can do:**
- Show today's calendar
- Create events (you approve first)
- Find free time slots
- Flag scheduling conflicts

**Setup:**
```bash
claude mcp add google-workspace -- npx -y @anthropic-ai/google-workspace-mcp --account=YOUR_EMAIL@gmail.com
```

Replace `YOUR_EMAIL@gmail.com` with your actual email. It will open a browser window to authorize access.

### 2. Gmail

Lets Claude draft and manage emails — always with your approval before sending.

**What it can do:**
- Search your inbox
- Draft emails in your voice
- Reply to threads
- Flag important messages

Gmail typically comes bundled with the Google Workspace MCP above. If you set up Google Calendar, you likely already have Gmail access.

### 3. Notion

Lets Claude read and update your Notion databases, pages, and tasks.

**What it can do:**
- Search your workspace
- Create and update pages
- Manage task databases
- Pull meeting notes

**Setup:**
```bash
claude mcp add notion -- npx -y @anthropic-ai/notion-mcp
```

You'll need a Notion integration token:
1. Go to [notion.so/my-integrations](https://www.notion.so/my-integrations)
2. Create a new integration
3. Copy the token
4. Share your databases/pages with the integration

### 4. Google Drive

Lets Claude search and read your documents, spreadsheets, and slides.

**What it can do:**
- Search for files by name or content
- Read documents and spreadsheets
- Create new files

**Setup:**
```bash
claude mcp add google-drive -- npx -y @anthropic-ai/google-drive-mcp --account=YOUR_EMAIL@gmail.com
```

## Tips

- **Start with just one MCP.** Calendar is the most immediately useful.
- **You always approve actions.** Claude will show you what it wants to do before doing it.
- **If auth breaks,** try relaunching Claude. Most auth issues fix themselves on restart.
- **MCPs load fresh each session.** The first time Claude uses an MCP in a session, it may take a moment to connect.

## Checking What's Connected

In any Claude session, you can ask: "What MCPs do I have connected?" and it will list everything available.

## Finding More MCPs

The MCP ecosystem is growing. Check:
- [MCP Server Registry](https://github.com/modelcontextprotocol/servers) — official and community MCPs
- Ask Claude: "Is there an MCP for [app name]?" — it often knows
