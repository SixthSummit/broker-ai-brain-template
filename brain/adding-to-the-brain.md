# Adding to the brain

**Read this** when you add or change anything in the brain other than a log line. What each folder
is for: [[brain/how-this-brain-works]].

## Before you change anything

- **Pull first, and read the file again right before you change it.** All of the broker's bots
  share one copy of the brain, so another bot may have changed it a moment ago.
- **Tell the broker when a change affects how their bots work:** a new rule, a new, changed or
  removed skill, a preference, a new folder. Say it in plain words, without file names. Small
  additions as part of the work, like a fact about a tool, need no announcement.
- **Moving, renaming and deleting are part of the work** (hard rule 6 in `AGENTS.md`): a skill the
  broker no longer uses can go, and a log in the wrong place can move ("Moving or deleting a file"
  below). A record in `data/` is deleted only when the broker asks. Never rename, move or delete
  `AGENTS.md` or the folders and files it names: every bot's instructions point to them.

## How to write it

- **File names:** lowercase words joined by hyphens, ending in `.md`, such as `my-marketing.md`.
  Dated records start with the date: `2026-11-20-smith-pre-approval.md`.
- **Write every note for the bots,** in plain words: what it is about, and what a bot should do
  with it.
- **A preference or a fact learned over time** goes in as a dated line, at the end of its list,
  such as `- 2026-11-20: Prefers a call over email for anything about rates.` Add it at the end
  rather than rewriting the file, so a line another bot adds at the same moment isn't lost. If the
  list still says "(none yet)", replace that line with yours.
- **Change, don't pile up.** When something new replaces something old, update the old line
  instead of adding a second one that contradicts it.

## Where it goes

Go down the list and stop at the first row that fits.

| You are saving | Where | Also update |
|---|---|---|
| An always or never for every bot | `rules/my-rules.md`, after reading the wording back to the broker | |
| How the broker wants one bot to work | "How the broker likes working with me" in `bots/<bot>/job.md` | |
| A way of doing a task, step by step, the same way every time | `skills/<skill-name>.md` ([[skills/create-a-skill]]) | The index in `skills/README.md` |
| Something that happened: a meeting, a call | `data/meetings/` or `data/calls/` ([[skills/meeting-summary]], [[skills/call-summary]]) | |
| A new kind of record | A new subfolder of `data/` | The folder list in `data/README.md` |
| What is in a tool, how it is set up, how to use it | `integrations/<tool>.md` ([[skills/connect-a-new-tool]]) | The tool map in `integrations/README.md` |
| A routine | Grok, with the broker ([[skills/set-up-a-routine]]) | "Set up" in `bots/<bot>/routines.md` |
| How the broker likes to work with all their bots (including how they want their meeting and call summaries), or a suggestion they turned down | `context/how-i-work.md` | |
| Who on the broker's team handles what (their assistant answers lender emails, say) | A dated line in `context/how-i-work.md`, which every bot reads | The person in `context/my-people.md` |
| A partner they work with (realtor, lawyer, lender rep) | `context/my-people.md` | |
| Anything else about the broker or their business | The right file in `context/`: `about-me.md`, `my-business.md` | |
| A new top-level folder | Only with the broker's OK ("Changing the layout" in [[brain/how-this-brain-works]]), when nothing above fits or the broker asks for one, with a `README.md` inside | The map in `AGENTS.md` and in [[brain/how-this-brain-works]], and a row for it in this table, above the rows for `context/` |

Still not sure? Ask the broker in plain words and offer the two likeliest places, for example:
"Should I keep this with your business notes, or as a recipe for this task?"

## Moving or deleting a file

When your work calls for it (hard rule 6). Never `AGENTS.md` or the folders and files it names, and
a record in `data/` only when the broker asks:

1. **Move it with `mv`, delete it with `rm`,** never with `git mv` or `git rm`:
   `mv /workspace/ai-brain/<old path> /workspace/ai-brain/<new path>`.
2. **Find everything that still points to it,** by its name alone, since notes don't always give
   the folder: `grep -rn "<file name without folder or .md>" /workspace/ai-brain --include=*.md`.
   Fix every hit that means this file.
3. **Save it all in one save,** naming the old path, the new path and the files you fixed, as
   "Saving it" says.
4. **Tell the broker** if a Grok routine or a Grok skill names the old path, so it gets updated
   too.

## Saving it

`b=/workspace/ai-brain; git -C $b add <files> && git -C $b commit -qm "<you>: <what changed>" -- <files> && { git -C $b push -q || { git -C $b pull -q --rebase && git -C $b push -q; }; }`

Name the files, as paths inside the brain. `-- <files>` saves only the files you name, even when
another bot is halfway through its own save. Never `git add -A` or `git add .`: anything else in the
folder could be a client document. The save message stays in the brain's history: name the file
and the change, never a client's personal details.

**Git says there is nothing to commit** ("nothing to commit", or "no changes added to commit" when
another bot has unsaved changes): check with `git -C /workspace/ai-brain log -1 -p -- <file>`. If
your change is in the last save of that file, it is already saved. Don't tell the broker anything
failed.

**The pull stops on a conflict:** this happens only when the same lines were changed outside this
computer, on GitHub for example. Open the file and keep what both versions say, merged sensibly. If
they can't be merged, keep both, one after the other, mark them "(two versions: check with the
broker)", and ask the broker which one is right (in a routine run, at the top of the final
message). Remove the `<<<<<<<`, `=======` and `>>>>>>>` lines, then run
`b=/workspace/ai-brain; git -C $b add <file> && GIT_EDITOR=true git -C $b rebase --continue && git -C $b push -q`.

**"index.lock" or "another git process":** see "When a pull fails" in [[brain/joining]].

**Anything else git refuses:** never force it. Tell the broker in plain words what didn't work,
never the git message itself.
