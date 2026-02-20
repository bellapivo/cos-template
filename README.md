# Your AI Chief of Staff

A personal AI system that actually knows you — your priorities, your people, your rules — and gets smarter every day you use it.

Built on [Claude Code](https://docs.anthropic.com/en/docs/claude-code), this is a starter template for building your own AI Chief of Staff. Clone it, personalize it, and let Claude run your life (with your permission).

## What This Is

Most AI tools are generic. You explain your whole life, get a mediocre answer, and start over tomorrow because it forgot everything.

This is different:

- **Persistent memory** — It remembers your projects, people, and preferences across every session
- **Custom tools** — It builds scripts that automate YOUR specific workflows
- **Real integrations** — It connects to your actual calendar, email, Notion, and more
- **Your rules** — You set hard boundaries it follows every time

## What You Need

- A Mac or PC with a terminal (Mac: search "Terminal" in Spotlight)
- [Node.js](https://nodejs.org/) installed (download the LTS version, run the installer)
- An Anthropic API key or Claude Pro subscription ([get one here](https://console.anthropic.com/))

## Setup — Step by Step

### 1. Install Claude Code

Open your terminal and paste this:

```bash
npm install -g @anthropic-ai/claude-code
```

### 2. Clone This Template

```bash
git clone https://github.com/bellapivo/cos-template.git MyCOS
cd MyCOS
```

This creates a folder called `MyCOS` with everything you need.

### 3. Launch Claude

```bash
claude
```

That's it. Claude reads your `CLAUDE.md` file automatically and starts working.

### 4. Let Claude Interview You

The first time you launch, Claude will ask you questions to personalize the system:

- What's your name and what do you do?
- What do you need help with?
- Who are the key people in your life?
- What are your hard rules?

It updates your files based on your answers. The more specific you are, the better it gets.

## What's In The Box

```
MyCOS/
├── CLAUDE.md                    ← Your instruction file. This is what makes Claude YOURS.
├── memory/
│   ├── memory.md                ← Quick reference — contacts, IDs, preferences (auto-loads every session)
│   ├── context.txt              ← What's happening right now — projects, priorities, open loops
│   └── conversations/           ← Daily session logs so it picks up where you left off
├── Tools/                       ← Scripts Claude builds for you over time
└── docs/
    └── mcp-setup.md             ← How to connect Claude to your calendar, email, Notion, etc.
```

### CLAUDE.md — Your Instruction Manual

This is the most important file. It tells Claude:

- Who you are and what you do
- Your key people and relationships
- Hard rules (like "never send emails without my approval")
- Your daily schedule and time blocks
- How you want Claude to communicate

**There's no line limit**, but keep it focused. Start with 20 lines. Add more as you learn what works. Most people end up around 100-300 lines.

### Memory — How It Remembers

Claude saves everything in plain text files in your `memory/` folder:

- **memory.md** auto-loads every session. Keep it under **200 lines** — anything beyond that gets cut off. Use it for essential reference info only.
- **context.txt** is your "current state" — Claude updates it every session with what's active, what's open, and what's next.
- **conversations/** stores daily logs. Claude reads yesterday's log when it starts today's session.

Want to track something detailed (nutrition, projects, contacts)? Create a separate file like `memory/nutrition.md` and reference it from memory.md.

### Tools — Automating Your Life

When you describe a repetitive task, Claude can write a script to automate it. These save in your `Tools/` folder.

Examples of tools people build:
- Daily calendar summary
- Email drafting with your voice/tone
- Task management (create, update, check off)
- Meeting prep (pull context on attendees)
- Weekly planning rituals

You don't need to know how to code. Just say: **"Build me a tool that [does this thing]."**

### MCPs — Connecting Real Apps

MCPs (Model Context Protocol) are plugins that let Claude talk to your actual apps. See [docs/mcp-setup.md](docs/mcp-setup.md) for setup instructions.

Popular MCPs:
- Google Calendar — read and create events
- Gmail — draft and send emails (with your approval)
- Notion — read and update databases
- Google Drive — search and read documents

## Daily Usage

### Starting a session

Just type `claude` in your terminal. It will:

1. Load your CLAUDE.md instructions
2. Check your memory for current context
3. Show you a daily snapshot (priorities, open loops, schedule)
4. Ask: "What's the ONE thing that matters today?"

### Ending a session

Say "done for the day" and Claude will:

1. Summarize what you accomplished
2. List open loops
3. Save everything to memory
4. Preview tomorrow

## Tips

- **Be specific.** "I'm a founder" tells Claude nothing. "I run a DTC skincare brand, 3 employees, fundraising in 6 months" is gold.
- **Start with ONE workflow.** Don't try to automate everything on day one. Pick one thing you do daily. Automate that. Add more next week.
- **Use it every day.** Consistency compounds. A week off means lost context and momentum.
- **Update memory.** If Claude gets something wrong, correct it. Say "remember that [X]" and it'll save it.
- **When something breaks,** paste the error message. Don't troubleshoot alone.

## The #1 Rule

When you're overwhelmed, ask Claude:

**"What's the ONE thing that matters today?"**

Not 10 things. Not 5. One.

---

Built by [Bella Pivo](https://bellapivo.com) | [@bella.pivo](https://tiktok.com/@bella.pivo)

Inspired by building my own AI Chief of Staff as an analyst at [FoundersEdge](https://foundersedge.com), a preseed VC firm in Boston.
