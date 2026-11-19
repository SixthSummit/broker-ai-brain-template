# Inbox Manager: first run

**The goal:** within the first week, an inbox the broker trusts you with: they know what needs
them without digging, and most replies are already written in their voice.

Before you start, the brain is connected, and if you are the broker's first bot, the brain is
introduced ([[brain/joining]]).

## Your job

Show the broker, in a few lines, what you do (from `bots/inbox-manager/job.md`), and ask whether
that is the job they want from you, or what they would change. Write any change into your `job.md`
before you go on, or, if they keep it as it is, add `- YYYY-MM-DD: Job agreed as written.` under
"How the broker likes working with me". If your name in Grok isn't the one in your row of the
table in `bots/README.md`, put it there.

## What you need

- **Email with clients connected** (the tool map in `integrations/README.md`). Not yet:
  [[skills/connect-a-new-tool]]. If it can't be connected now, do what you can without it, then
  pause your onboarding (see "Finish").
- **The calendar** helps, for free times when someone asks to meet. Not urgent.

## Look before you suggest

Before you suggest anything, look at the last two weeks of the inbox:

- How much comes in a day, and from whom: clients, lenders, realtors, lawyers, newsletters.
- How the broker organises it today: folders, labels, categories, flags, or nothing at all.
- How much sits unanswered, how old it is, and how fast they usually reply.

Senders, subjects, dates and folders are enough: open an email only when they don't tell you what
it is.

Tell the broker what you saw in three or four lines, in plain words.

## Suggest

Based on what you saw, offer a few options at a time and let the broker pick:

- **Going through new mail on a schedule:** how often (twice, three or four times a day), weekdays
  only or weekends too ([[skills/set-up-a-routine]]).
- **Sorting:** with the folders or labels they already have, or a simple set you propose, such as
  "needs me", "waiting on someone" and "for information".
- **Replies:** writing a reply in their voice for every email that needs one.
- **What to flag straight away:** they decide what counts. Possible fraud is always flagged (hard
  rule 4 in `AGENTS.md`).
- **Learning their voice** from their sent mail ([[skills/write-in-my-voice]]).

## Save what you learn

- What they chose goes in "How the broker likes working with me" in `bots/inbox-manager/job.md`.
- If they want their mail sorted or answered the same way every time, offer to save it as a skill
  ([[skills/create-a-skill]]).
- Every routine they say yes to goes in "Set up" in `bots/inbox-manager/routines.md`.

## Finish

1. In `bots/inbox-manager/job.md`, set "Onboarding" to `done, YYYY-MM-DD`. If the email couldn't
   be connected, set it to `paused, waiting for email` instead, and finish the rest once the tool
   map shows it connected.
2. Log "Joined the brain", plus what is connected and which routines are on
   ([[brain/session-logs]]).
