# Integrations

The broker's tools: where their clients, emails, meetings, files and deals live, and how their
bots reach them. Every broker uses a different mix of tools, and sets each one up their own way. So
this folder starts nearly empty, and fills up as the broker tells you which tool does which job.

## How it works

- **The tool map below** says which tool does which job, and whether it is connected. Check it
  before you use a tool for a task.
- **Connected apps work for every bot.** They belong to the broker's whole Grok account, so once
  one bot has connected an app, every bot can use it. **A key is different:** a key given through
  the secure secret card stays with the one bot that received it. For a tool reached with a key,
  its file says which bots hold the key, and another bot that needs the tool asks the broker for
  the key with the card.
- **Each tool has its own file** (`<tool>.md`, such as `velocity.md`): what lives there, what it is
  used for, how to connect, what the broker uses bots for there, where things are in this broker's
  setup, and its traps. Read it before you work in that tool. Learn a tool's setup by looking and
  asking. Never assume it works the way it does for another broker.
- **A tool that isn't connected yet:** [[skills/connect-a-new-tool]]. When the tool map names it,
  connect it by name. When the map names no tool for the job, ask by the job, and name a few usual
  options only as examples, so the broker can answer in a word.
- **Data stays in the tool.** These files say where things are and how to get them. They never hold
  copies of client records (hard rule 1 in `AGENTS.md`).

## The tool map

**Tool** is what the broker uses for the job, `not asked yet` until a bot asks. A tool that is
already named is one this broker uses: connect it by name ("Let's set up your Velocity"), without
asking which tool they use. **Connected** is `yes, YYYY-MM-DD` once a bot has used the tool
successfully, or `no`, with a short reason when there is one (`no, key requested YYYY-MM-DD`). A
tool reached with a key is connected for you only when its file lists you among the bots holding
the key: otherwise ask for it with your own card, whatever this column says. When the broker uses
nothing for a job, write `not used` in both.

| Job | Tool | Connected | File |
|---|---|---|---|
| Email with clients | not asked yet | no | |
| Calendar | not asked yet | no | |
| Files and documents | not asked yet | no | |
| Client list (CRM) | not asked yet | no | |
| Mortgage applications | Velocity | no | `velocity.md` |
| Tracking conditions and documents | not asked yet | no | |
| Phone calls and texts | not asked yet | no | |
| Video meetings | not asked yet | no | |
| Meeting notes or recordings | not asked yet | no | |
| E-signatures | not asked yet | no | |
| Marketing and social media | not asked yet | no | |

Add a row when the broker uses a tool for a job that isn't listed.
