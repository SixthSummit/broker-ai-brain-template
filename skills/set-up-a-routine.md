# Set up a routine

**Use when:** you offer, create, change or stop a routine, or the broker asks about usage.

## Explaining it

Before you suggest a routine, say what it is in plain words, for example: "A routine is a job I do
by myself on a schedule, like checking your inbox every morning at 8. Every run uses some of your
Grok usage, the same as a chat."

## Steps

1. **Suggest what fits,** from the "Routines to offer" in your `routines.md` and from what you've
   seen of how the broker works. A suggestion, never a default.
2. **Check the other bots' `routines.md` first,** so the broker never pays twice for the same
   thing. If another bot already does it, say so instead.
3. **Agree on when** with the broker: which days and what times, usually inside their working
   hours, always in their time zone (`context/about-me.md`). Pick a minute no other bot's routine
   uses (8:05 rather than 8:00), so two bots don't save to the brain at the same moment. Grok runs
   routines in the time zone set in its own Settings, under **General**, in the **Bot** section
   (**Timezone**): check that it matches the broker's, and if it doesn't, tell them where to change
   it before you rely on the times.
4. **Create it in Grok.** Its instruction always starts with "Routine run, nobody is watching. Pull
   my brain at /workspace/ai-brain and follow AGENTS.md there.", then says what to do in a few
   short lines. `AGENTS.md` says how a routine run works ("Routine runs and hand-offs").
5. **Write it in "Set up" in `bots/<you>/routines.md`:** the name, what it does, when it runs, and
   the exact instruction, so it can be rebuilt if the bot is ever made again.
6. **Changing or stopping one** happens only when the broker asks, and only the bot that runs it
   can do it. For another bot's routine, tell the broker which bot runs it, so they ask that bot;
   it updates its own `routines.md`. Update "Set up" the same moment you change one of yours.

## Keep usage low

- **A few set times a day is usually enough.** A routine that runs every few minutes can use up a
  week of usage in a day.
- **One sweep beats many small checks:** one run at 8:00 rather than one every hour.
- **A check that finds nothing stays silent** and logs nothing, as long as every read worked. A
  brief or a list the broker expects at a set time always arrives, even if it only says there is
  nothing today.

**When the broker asks about usage,** list their bots' routines (from each `routines.md`) and how
often each runs, and suggest which one to slow down or stop first. Change nothing without their
yes, and only your own routines (step 6).

## Notes

(none yet)
