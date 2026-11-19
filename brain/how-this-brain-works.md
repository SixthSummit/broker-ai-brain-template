# How this brain works

**Read this** when you explain the brain to the broker, when you are not sure where something new
belongs, and before you change the brain's layout. Not on every task.

## What the brain is for

The goal: every bot that works for this broker knows their business as well as an assistant who
has worked with them for years. It knows who they are, which tools they use and what is in them,
how they want each task done, and what already happened. Nothing the broker teaches one bot is
lost: it goes in the brain, and every other bot reads it. The broker never has to explain the same
thing twice.

A brain is never finished. It starts almost empty and fills up as you work with the broker. Part
of your job is to help it grow: [[brain/growing-the-brain]].

## Explaining it to the broker

Most brokers have never heard of an AI brain. Use plain words and everyday comparisons, never
technical terms like repository, markdown or git. For example:

- **The brain:** "a shared notebook all your assistants read before they start work, and write in
  when they learn something about you or your business."
- **Context:** "the pages about you and your business."
- **Integrations:** "a short guide to each of your tools: what's in it and how we use it."
- **Skills:** "recipes. When you show me how you like a task done, I write the recipe down, so
  every one of your bots does it your way, every time."
- **Bots:** "each assistant's job description."
- **Data:** "the diary: what we did each day, and notes from your meetings and calls."
- **Rules:** "the house rules every assistant follows."
- **Routines:** "jobs a bot does by itself on a schedule, like checking your inbox every
  morning."

Explain one idea at a time, at the moment it matters. Never give the whole tour at once unless the
broker asks for it.

## What each folder holds

**`context/`: who the broker is and how their business runs.**
- `about-me.md`: name, city, time zone, working hours, languages, background, and the dates the
  bots keep (when the brain was introduced, when its key expires, when the broker was last reminded
  about it).
- `how-i-work.md`: how they like to work with all of their bots, who on their team handles what,
  and the suggestions they turned down. Every bot reads it at the start of a chat.
- `my-business.md`: their clients, what they focus on, where business comes from, how a deal moves
  through their business, the brokerage they work under, their goals.
- `my-people.md`: the partners they work with often (realtors, lawyers, appraisers, lender reps),
  with contact details. Clients never go here: they live in the broker's client list.
- A new file here when a topic about the broker or the business outgrows the files above, such as
  `my-marketing.md`.

**`integrations/`: the broker's tools.** `README.md` holds the tool map: which tool does which job,
and whether it is connected. Then one file per tool: what lives there, what it is used for, how to
connect, what the broker uses bots for there, where things are, and its traps. Tools differ from
broker to broker, and so do their setups, so a tool's file describes this broker's setup, learned
by looking and asking.

**`skills/`: recipes.** One file per task the broker wants done a certain way, usable by any bot.
`README.md` is the index: check it before every task. A skill is born when the broker shows you how
they want something done: [[skills/create-a-skill]].

**`bots/`: one folder per bot.** `job.md` (what the bot is for, which tools and skills it uses,
where its onboarding stands, and how the broker likes working with it), `onboarding.md` (how it
gets ready to work on its first run) and `routines.md` (the routines it can offer, and the ones
that are set up).

**`data/`: what happened.** `session-logs/<bot>/` holds each bot's daily log. `meetings/` and
`calls/` hold summaries. Never raw transcripts or copies of records: those stay in the tool they
came from. A new kind of record gets its own subfolder: [[data/README]].

**`rules/`: the house rules.** `ground-rules.md` holds the rules every bot follows, with the
reasons. `my-rules.md` holds the broker's own always-and-never rules, added as they come up.

**`brain/`: how the brain works.** This file, plus how it grows, how a bot joins it, how to log and
how to add to it.

## What is not in the brain

- **The broker's client files, records, emails and documents.** They stay in their tools.
  `integrations/` says where they are and how to reach them.
- **Your day-to-day output.** Replies, prep notes, lists and briefs are shown in the chat or written
  in the broker's own tools. The brain keeps your log line, and the summaries of meetings and calls.
- **A client's personal details** (hard rule 1 in `AGENTS.md`) **and every password, login, key and
  token** (hard rule 2).
- **Routines themselves.** They run inside Grok. Each bot's `routines.md` is the record of them.
- **Your own Grok memory.** It is yours alone. Anything another bot should know goes in the brain.

## Where something new goes

The list, most specific first, is in "Where it goes" in [[brain/adding-to-the-brain]].

## Changing the layout

The broker may reorganise their brain. A layout change is a new top-level folder, or regrouping
what a folder holds: before one, explain in one or two lines what you will change and why, and get
their OK. Adding, moving, renaming or deleting notes is ordinary work, not a layout change (hard
rule 6). Keep the folders above, and never rename, move or delete `AGENTS.md` or the folders and
files it names: every bot's instructions point to them. This holds even when the broker asks: say
in one line that their bots find their way by these names, so they stay. Then offer another way to
get what they are after, such as always calling skills "recipes" when you talk to them, and write
what you agree as a dated line in `context/how-i-work.md`. Add a new folder only when nothing existing fits or the broker
asks for one, and give it a `README.md` that says what it holds. How:
[[brain/adding-to-the-brain]].
