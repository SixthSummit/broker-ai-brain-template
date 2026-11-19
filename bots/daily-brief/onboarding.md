# Daily Brief: first run

**The goal:** a brief the broker actually reads every day, because it shows exactly what they need
and nothing else.

Before you start, the brain is connected, and if you are the broker's first bot, the brain is
introduced ([[brain/joining]]).

## Your job

Show the broker, in a few lines, what you do (from `bots/daily-brief/job.md`), and ask whether that
is the job they want from you, or what they would change. Write any change into your `job.md`
before you go on, or, if they keep it as it is, add `- YYYY-MM-DD: Job agreed as written.` under
"How the broker likes working with me". If your name in Grok isn't the one in your row of the
table in `bots/README.md`, put it there.

## What you need

- **The calendar and the email connected** (the tool map in `integrations/README.md`). Not yet:
  [[skills/connect-a-new-tool]]. If one can't be connected now, do what you can without it, then
  pause your onboarding (see "Finish").
- **The mortgage applications connected for you,** when the tool map names a tool for them
  (Velocity): deals closing soon and conditions still open belong in a brief. Velocity is reached
  with a key, so it is connected for you only when you hold the key (`integrations/velocity.md`
  says how to check). Not yet: the same skill, by name ("Let's set up your Velocity"), with your own
  key card. If it can't be connected now, carry on without it.
- **The other bots' logs** in `data/session-logs/`. Fewer bots means a shorter brief: that's fine.

## Look before you suggest

Look at today's (or tomorrow's) calendar, the inbox, the deals closing soon in the mortgage
applications tool if it is connected, and what the other bots logged in the last day or two. Then
build a sample brief from that real data, right now, so the broker sees what they would get.

## Find out

Show the sample, and find out what the broker wants from it:

- **What goes in,** for example: meetings and who they're with, emails waiting for a reply,
  replies the other bots wrote, deals closing soon and conditions still open, anything a bot
  flagged, one thing to do first.
- **When:** a morning brief, an evening wrap, a weekly look-ahead, or a mix. Weekdays only?
- **How long:** a few lines, or more detail.

## Save what you learn

- What they chose goes in "How the broker likes working with me" in `bots/daily-brief/job.md`.
- Once the format settles, offer to save it as a skill ([[skills/create-a-skill]]).
- Every routine they say yes to goes in "Set up" in `bots/daily-brief/routines.md`
  ([[skills/set-up-a-routine]]).

## Finish

1. In `bots/daily-brief/job.md`, set "Onboarding" to `done, YYYY-MM-DD`. If the calendar or the
   email couldn't be connected, set it to `paused, waiting for <tool>` instead, and finish the rest
   once the tool map shows it connected.
2. Log "Joined the brain", plus what is connected and which routines are on
   ([[brain/session-logs]]).
