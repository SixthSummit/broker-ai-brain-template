# Growing the brain

**Read this** after a bot's first run, when the broker asks what else their bots could do, and
every now and then when a chat leaves room for it. The broker doesn't know what a brain could hold,
so you are the one who notices what is missing and suggests the next step. You are their guide,
not only on the first day.

## What a complete brain looks like

Check these against the brain as it is today:

- **Context:** every file in `context/` filled in, with no "not filled in yet" left that a bot
  actually needs.
- **Tools:** every job in the tool map in `integrations/README.md` has a tool or says `not used`,
  and every tool the broker uses has its own file.
- **Voice:** `skills/write-in-my-voice.md` is learned.
- **Skills:** each task the broker wants done the same way every time has its own skill.
- **Data:** meetings and calls that matter end up as summaries in `data/`, if the broker wants
  that.
- **Rules:** every always or never the broker has said is in `rules/my-rules.md`.
- **Routines:** each bot runs the routines that save the broker time, and its `routines.md` lists
  them.
- **Bots:** every bot the broker uses is connected to the brain and has its folder in `bots/`.

## Moments to suggest something

| You notice | Suggest |
|---|---|
| The broker explains how they want a task done, or corrects you the same way twice | Saving it as a skill: [[skills/create-a-skill]] |
| A tool comes up that the tool map doesn't have | Connecting it and writing its file: [[skills/connect-a-new-tool]] |
| The broker had a meeting or a call worth remembering | A summary in `data/`, and maybe a routine that writes one after every meeting: [[skills/meeting-summary]] |
| The broker asks for the same thing at the same time every week | A routine: [[skills/set-up-a-routine]] |
| A context file you need is still empty | The one or two questions that fill it, in the flow of the work |
| The broker says "always" or "never" | A line in `rules/my-rules.md`, after you read the wording back to them |
| The broker mentions a bot that isn't in the table in `bots/README.md` | First ask whether it is one of the bots in the table under a new name (then put the new name in its row). If not, connecting it: they tell that bot "Connect to my AI brain at /workspace/ai-brain and follow AGENTS.md there", or you make their next bot for them ("Making a bot for the broker" in [[brain/joining]]) |

## How to suggest

- **One suggestion at a time,** at a natural moment, never in the middle of an urgent task.
- **Lead with what it does for the broker,** in one sentence, for example: "Want me to save this
  as a recipe, so all your bots do it this way from now on?"
- **Explain new words when you first use them** ([[brain/how-this-brain-works]]).
- **A no is a no.** Write it in `context/how-i-work.md`, such as
  `- 2026-11-20: Doesn't want meeting summaries.`, so no bot asks again, unless the broker brings
  it up.
- **At most one brain suggestion per chat,** unless the broker asks for more.
