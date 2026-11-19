# Session logs

Each bot keeps a daily log of what it did, so the broker's other bots can see it during the day
and pick up where it left off. The Daily Brief builds its rundown from these logs.

**Where:** `data/session-logs/<you>/YYYY-MM-DD.md`, one file per bot per day, dated in the
broker's time zone (`context/about-me.md`).

## What to log

**Real work only:** something you did, wrote, changed, booked, flagged or summarised, or a routine
run that found something. Not a lookup, not a question you answered, and not a routine run that
found nothing.

**One line per job:** `- HH:MM · what you did · who or what it was about · what's next`

```
- 08:05 · wrote 2 replies · Smith, Nguyen · Smith wants a call Tuesday
- 17:32 · checked tomorrow's calendar · clash at 10:00 · the broker picks which meeting moves
```

Client names are fine. The client details in hard rule 1 of `AGENTS.md` are not, and neither is
any password, login, key or token (hard rule 2).

## Add a line and save it

Fill in `<you>`, `<tz>` (the time zone setting in `context/about-me.md`, such as `Etc/GMT+7` or
`America/Edmonton`) and the line between the two `LINE` markers. Nothing between those markers is
run as a command, so dollar signs and apostrophes are safe.

```
b=/workspace/ai-brain; tz="<tz>"; f="$b/data/session-logs/<you>/$(TZ=$tz date +%F).md"
git -C "$b" pull -q --rebase
mkdir -p "$b/data/session-logs/<you>"
{ printf -- '- %s · ' "$(TZ=$tz date +%H:%M)"; cat <<'LINE'
<what you did> · <who or what it was about> · <what's next>
LINE
} >> "$f"
git -C "$b" add "$f" && git -C "$b" commit -qm "<you>: log" -- "$f" && { git -C "$b" push -q || { git -C "$b" pull -q --rebase && git -C "$b" push -q; }; }
```

The line goes at the end of the file, so two bots logging at the same moment both keep theirs. If a
git step fails, your line is already in the file: never run the whole block again, or it goes in
twice. Wait, then run only its last line again. If that says there is nothing to commit, your line
is already saved on this computer and goes up with the next save that works: see "When a pull
fails" in [[brain/joining]].

## Reading logs

Any bot may read any bot's log when a task needs it. Read only the bots and the days the task
needs, never all of them out of habit.
