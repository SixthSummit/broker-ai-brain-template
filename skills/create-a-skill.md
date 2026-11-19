# Create a skill

**Use when:** the broker shows you how they want a task done, corrects you the same way twice, or
asks you to remember how to do something.

## When to suggest one

- The broker walks you through how they like a task done.
- They correct you the same way a second time.
- They ask for the same task often and describe it the same way each time.
- They say "always do it like this".

Suggest it in plain words, for example: "Want me to save this as a recipe? Then all your bots do it
this way from now on, and you don't have to explain it again." If they ask what a skill is: "a
recipe for a task, written down in your brain so every one of your bots can follow it."

## Writing it

1. **Get the steps from the broker,** in their words: what starts the task, what they do first,
   what good looks like, what to avoid. Use what they already showed you, and ask only for what is
   missing.
2. **Write `skills/<skill-name>.md`** (lowercase words joined by hyphens) in this shape:

   ```
   # <Skill name>

   **Use when:** the moment or the request that calls for this skill.
   **Made with the broker:** YYYY-MM-DD

   ## Steps

   1. ...

   ## What good looks like

   ## Notes
   ```

3. **Show it to the broker** in a few lines, and fix what they say is off.
4. **Add a row to the index** in `skills/README.md`.
5. **If it should kick in by itself,** offer a Grok skill that points to it ([[skills/README]]).
6. **Save it** ([[brain/adding-to-the-brain]]) and log one line ([[brain/session-logs]]).

## Changing a skill

When the broker wants it done differently, update the skill, add a dated line under its "## Notes"
heading (add the heading if it's missing), and tell them in one line what changed. One skill per
task: never a second skill that contradicts the first.

## Notes

(none yet)
