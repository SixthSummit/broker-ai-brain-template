# Call summary

**Use when:** a phone call is over and should be remembered, because the broker asks, or a routine
does it after calls.

## Two kinds of summary

The same two kinds as for meetings: one in the brain, so every bot stays up to date, and, if the
broker wants it, one for them to read or send, in their own files. How the broker wants it is in
`context/how-i-work.md`. If it isn't there yet, explain and ask as "Two kinds of summary" in
[[skills/meeting-summary]] says.

## Where the content comes from

The call's transcript or recording notes from the broker's phone tool (see the tool map in
`integrations/README.md`), or the broker's own notes. No source: ask the broker what was said.

## Where it goes

`data/calls/YYYY-MM-DD-<who>-<topic>.md`. `<who>` is the client's last name; only when no client was
on the call, the partner's company. `<topic>` is two or three words. Lowercase, joined by hyphens:
`2026-11-20-smith-renewal-question.md`.

**Check first** whether another bot already wrote it: list `data/calls/` for the same date, and
open any file that could be this call. The same call (the same start time): add to it. A second call
with the same person on the same day: give yours `-2` at the end of its file name (`-3` for a
third).

## What goes in

The same as a meeting: everything that helps the next conversation. Leave out only a client's
personal details (hard rule 1 in `AGENTS.md`) and any password, login, key or token (hard rule 2).
Shorter, because calls are.

```
# Call: <who>, <topic>

- **Date and time:** YYYY-MM-DD HH:MM (the broker's time zone)
- **Who:** Name (client, or a partner's role and company), and who called whom
- **Source:** where the content came from

## What it was about

## What was said and decided

## Next steps

One line each: Action · Owner · When. "no date set" when no date was said.

## Preferences

How the person wants to be contacted, when, and what matters to them.

## What matters next time

What they want, their plans and timeline, their concerns.
```

Leave out a section the call had nothing for.

## After

Tell the broker the next steps in one or two lines, write their own summary too if they want one,
and log one line ([[brain/session-logs]]).

## Notes

(none yet)
