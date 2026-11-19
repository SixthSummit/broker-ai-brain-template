# Calendar Watch: first run

**The goal:** the broker walks into every meeting ready, and never finds out about a clash or a
missing link at the last minute.

Before you start, the brain is connected, and if you are the broker's first bot, the brain is
introduced ([[brain/joining]]).

## Your job

Show the broker, in a few lines, what you do (from `bots/calendar-watch/job.md`), and ask whether
that is the job they want from you, or what they would change. Write any change into your `job.md`
before you go on, or, if they keep it as it is, add `- YYYY-MM-DD: Job agreed as written.` under
"How the broker likes working with me". If your name in Grok isn't the one in your row of the
table in `bots/README.md`, put it there.

## What you need

- **The calendar connected** (the tool map in `integrations/README.md`). Not yet:
  [[skills/connect-a-new-tool]]. If it can't be connected now, do what you can without it, then
  pause your onboarding (see "Finish").
- **The email and the client list** make prep notes better. Not urgent.

## Look before you suggest

Look at the next two weeks of the calendar:

- How full it is, and which meetings are with clients.
- Recurring blocks: office hours, school runs, time off.
- How meetings get booked: a booking link, by email, by an assistant.
- Anything wrong right now: clashes, missing links, invites not answered.

Tell the broker what you saw in three lines, and mention anything wrong first.

## Suggest

Based on what you saw, a few options at a time:

- **An evening check of tomorrow:** clashes, missing links, unanswered invites.
- **Prep notes before client meetings,** and what they'd want in them, for example: who the person
  is, where their file stands, the last emails, the one thing to get out of the meeting.
- **Breaks between meetings,** if their days run back to back.
- **Meeting summaries.** Find out whether they use a notetaker for their meetings (an app that
  records or transcribes calls), and which one. If they do, offer to connect it
  ([[skills/connect-a-new-tool]]). If they don't, their meeting app may record or transcribe on
  its own (Zoom, Teams and Google Meet can, on some plans), or they can keep a few notes. Offer to
  join meetings yourself only if you are able to (not every Grok plan allows it), and never ask
  the broker about their plan. Then offer summaries, and explain the two kinds in "Two kinds of
  summary" in [[skills/meeting-summary]]: one in the brain so every bot stays up to date, and, if
  they want it, one for the broker to read or send, in the kind of document they use.

## Save what you learn

- What they chose goes in "How the broker likes working with me" in `bots/calendar-watch/job.md`.
- Once the prep notes settle into a format, offer to save it as a skill ([[skills/create-a-skill]]).
- Every routine they say yes to goes in "Set up" in `bots/calendar-watch/routines.md`
  ([[skills/set-up-a-routine]]).

## Finish

1. In `bots/calendar-watch/job.md`, set "Onboarding" to `done, YYYY-MM-DD`. If the calendar
   couldn't be connected, set it to `paused, waiting for calendar` instead, and finish the rest once
   the tool map shows it connected.
2. Log "Joined the brain", plus what is connected and which routines are on
   ([[brain/session-logs]]).
