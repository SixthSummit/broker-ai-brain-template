# Joining the brain

**Read this** when `/workspace/ai-brain` is missing or `git pull` there fails, when "Brain
introduced" in `context/about-me.md` says `not yet`, when you are a new bot, when git lists changes
nobody saved, and when the broker asks you to make a new bot.

## Connect this computer

The brain is the broker's own private GitHub repository, cloned at `/workspace/ai-brain`. All of the
broker's bots share one computer, so the brain is connected once, for all of them. Its key also
lives in one file outside the brain, `/workspace/.ai-brain-key`, so every bot can use it: a key
given through the secure secret card stays with the one bot that received it. Never print the key,
and never put it anywhere else: not in the brain, the remote address, a log, your memory or a chat.
`git remote -v` must always show the plain address. These steps are also in the Grok setup of the
bots that came with the brain, because a computer without the brain can't read this file.

1. **Check for the key file:** `test -s /workspace/.ai-brain-key && echo set || echo missing`.
   - `set`: go to step 2. If the broker has just given you a new key with the card, first write it
     to the file with the command below: it replaces the old one.
   - `missing`: ask the broker for the brain key with the secure secret card, never in the chat,
     saved as `AI_BRAIN_TOKEN`. It is the key they made on GitHub when their brain was set up. If
     they don't have it anymore, help them make a new one ("Renewing the brain key"). Then save it
     to the file:
     `(umask 077; printf '%s' "$AI_BRAIN_TOKEN" > /workspace/.ai-brain-key) && test -s /workspace/.ai-brain-key && echo saved`
2. **Connect, if `/workspace/ai-brain` is missing.** If the folder is there but
   `git -C /workspace/ai-brain rev-parse HEAD` fails, another bot may be connecting it right now:
   wait a minute and check again. Still failing: a connect stopped halfway, so move the folder
   aside with `mv /workspace/ai-brain /workspace/ai-brain-broken-$(date +%F)` and connect. To
   connect, ask the broker for the address of their brain on GitHub. It looks like
   `https://github.com/<their username>/<brain name>.git` and isn't secret, so the chat is fine. If
   they don't know it: on github.com, their profile picture, then "Your repositories", then open
   the brain, and copy the address from the browser. Then run:
   ```
   git clone -q -c credential.helper= -c credential.helper='!f() { test "$1" = get || exit 0; echo username=x-access-token; echo "password=$(cat /workspace/.ai-brain-key)"; }; f' <brain address> /workspace/ai-brain
   b=/workspace/ai-brain; git -C $b config user.name "Grok Bot" && git -C $b config user.email "grok-bot@ai-brain.invalid" && git -C $b config rebase.autoStash true && git -C $b config pull.rebase true
   ```
   The empty `credential.helper=` makes git use the brain key only, even if another GitHub login is
   saved on this computer. `rebase.autoStash` lets a pull go through while another bot is halfway
   through an edit. `pull.rebase` makes every pull, even a plain `git pull`, work the same way. If
   the clone fails: "Repository not found" means a wrong address, or a key made for another
   repository; "Authentication failed" means a wrong or expired key ("Renewing the brain key").
3. **Check the key and note when it expires.** GitHub says both, without the key being printed
   (the username and the brain name are in `git -C /workspace/ai-brain remote get-url origin`):
   `printf 'Authorization: Bearer %s' "$(cat /workspace/.ai-brain-key)" | curl -s -o /dev/null -D - -H @- https://api.github.com/repos/<their username>/<brain name> | grep -i -E '^(HTTP/|github-authentication-token-expiration)'`
   The first line must show `200`. If not, the key doesn't work: "When a pull fails". The second
   line gives the expiry date: write it next to "Brain key expires" in `context/about-me.md`, and
   save it (the command is in "Saving a change" in `AGENTS.md`). No second line: the key has no
   expiry date, so write `never`.
4. **Tell the broker in one line that their brain is connected,** then read `AGENTS.md`.

## Renewing the brain key

Walk the broker through it, one step at a time, in plain words. On GitHub, signed in to their own
account:

1. Their profile picture (top right), then **Settings**, then **Developer settings** (bottom of the
   left menu), then **Personal access tokens**, then **Fine-grained tokens**.
2. **If their "AI brain" key is listed,** expired or about to: open it and choose **Regenerate
   token**, with **No expiration**. It keeps the same brain and permission.
3. **If there is none:** choose **Generate new token**. Name it "AI brain" (if that name is taken,
   add the year: "AI brain 2027"), under **Expiration** choose **No expiration**, under
   **Repository access** choose "Only select repositories" and pick their brain, and under
   **Permissions** give the repository's **Contents** "Read and write". Nothing else.
4. **Copy the key** and paste it in the secure secret card, saved as `AI_BRAIN_TOKEN`. Then write
   it to the key file with the command at the end of step 1 of "Connect this computer" (run it even
   though the file is there: it replaces the old key), check it with
   `git -C /workspace/ai-brain pull -q --rebase`, and note the new expiry (step 3 there). If the
   check fails, don't start over: step 3 there tells why. `401`: the key was pasted incompletely,
   so paste it again. `404`: the key wasn't given this brain. `200` while the pull still fails: it
   lacks Contents "Read and write". Fix those two in the key's settings on GitHub.

## When a pull fails

- **Another bot was using git at the same moment** (a first failure such as "Cannot fast-forward
  your working tree", "Cannot rebase onto multiple branches", "would be overwritten by merge", or a
  rejected push): wait 10 to 40 seconds, a different number each time, and run the same command
  again, up to three times, before you look further.
- **A login error, or "Repository not found":**
  - **The key has expired** if "Brain key expires" in `context/about-me.md` has passed and the key
    file is older than that date (`find /workspace/.ai-brain-key ! -newermt '<that date>'` prints
    it). The brain on this computer still works for every bot: only saves to GitHub wait, and a
    save that fails only at the push is fine until the key is renewed. If "Broker reminded about
    the key" isn't today, tell the broker in one line, offer to renew it ("Renewing the brain
    key"), and set that line to today; otherwise say nothing.
  - **Otherwise,** check the key file (step 1 of "Connect this computer"). Missing: the computer
    was never given the key, so do step 1. Set: check the helper with
    `git -C /workspace/ai-brain config --get-all credential.helper`. The last two lines should be
    an empty one, then the brain-key helper (anything listed above the empty line is switched off
    by it). If not, set them again:
    `b=/workspace/ai-brain; git -C $b config --replace-all credential.helper '' && git -C $b config --add credential.helper '!f() { test "$1" = get || exit 0; echo username=x-access-token; echo "password=$(cat /workspace/.ai-brain-key)"; }; f'`
    and pull again. Still failing: the key is wrong, expired or switched off. Tell the broker in
    plain words, help them renew it ("Renewing the brain key"), and carry on with the task
    meanwhile: the brain on this computer is still there, and saves wait here until the key works.
- **"index.lock" or "another git process":** another bot is saving right now. Wait 10 to 40
  seconds, a different number each time, and try again, up to three times. Still there, and more
  than 10 minutes old (`find /workspace/ai-brain/.git/index.lock -mmin +10` prints it): a bot
  stopped halfway through a save. Remove it with `rm /workspace/ai-brain/.git/index.lock`, log that
  you did, and try again. Never remove a newer one: carry on with the task, and try the save once
  more at the end. Still failing then: tell the broker (in a routine run, at the top of the final
  message).
- **"You have unstaged changes":** run `git -C /workspace/ai-brain config rebase.autoStash true` and
  pull again.
- **"Need to specify how to reconcile divergent branches":** run
  `git -C /workspace/ai-brain config pull.rebase true` and pull again.
- **The pull stops on a conflict:** see "Saving it" in [[brain/adding-to-the-brain]].
- **"A rebase is in progress"** (`git -C /workspace/ai-brain status` says so): another bot may be in
  the middle of one, so wait a minute and check again. Still there:
  `git -C /workspace/ai-brain diff --name-only --diff-filter=U` lists the files left to fix. Fix
  them as "Saving it" in [[brain/adding-to-the-brain]] says, `git -C /workspace/ai-brain add` them,
  then run `GIT_EDITOR=true git -C /workspace/ai-brain rebase --continue`.
- **"Applying autostash resulted in conflicts":** the pull went through, but changes nobody had
  saved yet are in a stash (`git -C /workspace/ai-brain stash list` shows it). Never drop a stash
  whose changes aren't back in the files.
  - **A file now has `<<<<<<<` lines:** merge them as "Saving it" says, save the file, then run
    `git -C /workspace/ai-brain stash drop`.
  - **No file has them:** nothing was put back. Save the files `git -C /workspace/ai-brain status`
    lists as changed, then run `git -C /workspace/ai-brain stash pop`. Merge and save any
    `<<<<<<<` lines it leaves, and only if the pop reported a conflict, run
    `git -C /workspace/ai-brain stash drop` after that.
- **Anything else:** never reset, stash by hand or delete. Tell the broker in plain words that their
  brain couldn't be updated (never the git message itself), and carry on with the files that are
  there, if the task allows it.

## Changes a bot never saved

Look when `git -C /workspace/ai-brain status --short --ignored` lists files (step 3 of "Every task"
in `AGENTS.md`), or when git names files you didn't change. `!!` marks a file git never saves, such
as a PDF or a spreadsheet. Leave alone anything changed in the last 10 minutes
(`find /workspace/ai-brain/<file> -mmin -10` prints it): another bot is probably still working on
it. Then, for each one:

- **A brain note you recognise:** save it, naming it in the command in "Saving it"
  ([[brain/adding-to-the-brain]]).
- **A file with client details, or any `!!` file** (a document, an export, a note copied from a
  client file): move it out of the brain folder at once, to `/workspace/work/<you>/` (make it with
  `mkdir -p` if it's missing). Log it as "a client document", without its name or contents, and
  tell the broker in one line.

`git -C /workspace/ai-brain stash list` shows a stash: "Applying autostash resulted in conflicts"
in "When a pull fails". Never `git add -A` or `git add .`.

## The broker's first bot

If "Brain introduced" in `context/about-me.md` says `not yet`, you are the first bot to work with
this brain. Before your own onboarding:

1. **Tell the broker in a few lines what the brain is,** in the plain words of
   [[brain/how-this-brain-works]], and that only they, and anyone they give access to, can read it.
2. **Tell them about new bots,** in one or two lines: every bot they make later needs to be
   connected to the brain too. The easiest way is to ask one of their bots to make it ("make me a
   bot for..."): it comes out connected. If they make one themselves, its first message should be
   "Connect to my AI brain at /workspace/ai-brain and follow AGENTS.md there."
3. **Set "Brain introduced"** in `context/about-me.md` to today's date, and save it, so no bot
   explains the brain again.
4. **Fill in the basics** in `context/about-me.md` that still say "not filled in yet": name, city,
   time zone, working days and hours, languages. One card, or a few short questions. If the broker
   would rather not now, leave them, except the time zone: every date the bots write needs it. Take
   it from their connected calendar if you can, or ask for that one alone.

The rest of `context/` fills up over time, as it comes up in the work ([[brain/growing-the-brain]]).

## A new bot

The three bots in `bots/` come ready. A bot the broker made, or another bot made for them, joins
like this:

1. **Know your job.** If neither the broker nor the bot that made you said what you are for, ask
   the broker in one line.
2. **Check you are really new.** Find your job in the table in `bots/README.md`. If an existing bot
   already does it, and your first instruction doesn't already say, tell the broker, and ask
   whether you replace that bot or take a different job. Replacing it: ask the broker to delete the
   old bot in Grok first, so nothing runs twice and no two bots answer as one. Then use its brain
   name and folder, and keep its three files as they are: they hold what the broker taught it. Ask
   with the secure secret card for any key a tool's file says the old bot held, put your name in
   Grok in its row in `bots/README.md`, do step 4, offer to set up its routines again from "Set up"
   in its `routines.md` ([[skills/set-up-a-routine]]), and skip the other steps.
3. **Pick your brain name,** if you aren't replacing a bot: your job in lowercase words joined by
   hyphens.
4. **Save the rule and your brain name in your memory** (see "Keep coming back here" and "Your
   name in the brain" in `AGENTS.md`).
5. **Write your three files** in the same shape as the other bots' files: `bots/<you>/job.md`
   (with `**Onboarding:** not started`), `bots/<you>/onboarding.md` (the goal, your job, what you
   need, what to look at before you suggest anything, what to suggest, and how to finish) and
   `bots/<you>/routines.md`. Write them from what the broker, or the bot that made you, told you
   about your job.
6. **If you worked for the broker before joining,** write your existing routines under "Set up" in
   your `routines.md`, and save what you learned where it belongs ([[brain/adding-to-the-brain]]).
7. **Add your row to the table in `bots/README.md`,** with your name in Grok. If your job touches
   another bot's (the leads you follow up write back to the inbox the Inbox Manager answers, say),
   add a line under "Where two jobs meet" saying which bot does what, and tell the broker in one
   line.
8. **Follow your `onboarding.md`.**

A bot that runs the others (a Chief of Staff, say) reads their logs and asks them for work by
their name in Grok. It never does their job itself and never changes their files.

## Making a bot for the broker

Grok Bots can create other bots. When the broker asks you for a new bot:

1. **Check the table in `bots/README.md` first.** If a bot already does that job, say so, and ask
   whether the new one replaces it or does a different job.
2. **Create it,** with a name the broker likes, and give it this as its first instruction: "Your
   job: <the job, in the broker's words, and which bot it replaces, if any>. Your AI brain is at
   /workspace/ai-brain. Save this rule in your memory: before every task, pull it and follow
   AGENTS.md there. When the broker first writes to you, follow 'A new bot' in brain/joining.md."
3. **Tell the broker** the new bot is connected to their brain, and that it needs one short chat to
   finish setting up: they open it and say hello.
