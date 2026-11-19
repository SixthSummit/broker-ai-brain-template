# Meeting summary

**Use when:** a meeting is over and should be remembered, because the broker asks, or a routine
does it after each meeting.

## Two kinds of summary

1. **For the brain:** so every bot knows what was said and stays up to date. It goes in
   `data/meetings/` and follows this skill.
2. **For the broker:** in the kind of document they use (a Google Doc, a Word file, a PDF), saved
   where they want it in their own files, never in the brain. The full version is for their own
   reading. A version for someone else goes to that one person, one version each, written with
   [[skills/write-in-my-voice]]. The client's holds the topic, what was agreed, their next steps and
   the ones they are waiting on, the broker's included. A partner's, such as the realtor's, holds
   only what they need to act on (the timeline, whether the financing is on track), never the
   details in hard rule 1 unless the client agreed. Never the broker's private notes, or to-dos
   nobody there is waiting on.

When the broker first asks for summaries, or says yes to them, explain the difference in plain
words, for example: "I'll keep a summary in your brain so all your bots stay up to date. Want one
for yourself as well, to read or to send? Which kind of document, and where should it go?" Write
their answer in `context/how-i-work.md`, so every bot that writes summaries does it the same way.

## Where the content comes from

The best source you have, in this order: a transcript or notes from the broker's meeting tool or
notetaker (see the tool map in `integrations/README.md`), your own notes if you joined the meeting,
or the broker's own notes. Never a short auto-summary when a transcript exists. No source at all:
ask the broker for their notes.

## Where it goes

`data/meetings/YYYY-MM-DD-<who>-<topic>.md`. `<who>` is the client's last name; only when no client
was there, the partner's company. `<topic>` is two or three words. Lowercase, joined by hyphens:
`2026-11-20-smith-pre-approval.md`.

**Check first** whether another bot already wrote it: list `data/meetings/` for the same date, and
open any file that could be this meeting. The same meeting (the same start time): add to it instead
of writing a second one. A different meeting with the same name on the same day: give yours `-2` at
the end of its file name (`-3` for a third).

## What goes in

Keep everything that will help the next conversation: what the people want, their plans and
timeline, their worries, what was agreed and promised. Leave out only a client's personal details
(hard rule 1 in `AGENTS.md`) and any password, login, key or token (hard rule 2). Where a summary
needs one of those details, write where it lives instead: "income details in the client list".
Leave out small talk.

```
# Meeting: <topic>

- **Date and time:** YYYY-MM-DD HH:MM to HH:MM (the broker's time zone)
- **Who was there:** Name (client) · Name (co-borrower) · Name (realtor, Company)
- **Source:** where the content came from

## Topic

What the meeting was about, in one or two sentences.

## Decisions

What was decided, by whom, and why.

## Next steps

One line each: Action · Owner · When. Write "no date set" when no date was said. Never invent one.

## Preferences

How people said they want things done: how they like to be contacted, when, what matters to them.

## Key insights

What matters for the next conversation: what they want, their timeline, their concerns, anything
that changes the plan.
```

Leave out a section the meeting had nothing for. After a client's name, write only what they are on
the file (client, co-borrower, guarantor), never their job or employer. Partners get their role and
company.

## After

- Tell the broker in a few lines: the decisions, and the next steps with theirs first.
- Write the broker's own summary too, if they want one, and a version for each person who should
  get one, if they ask (see "Two kinds of summary").
- Log one line ([[brain/session-logs]]).

## Notes

(none yet)
