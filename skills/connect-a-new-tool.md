# Connect a new tool

**Use when:** a task needs a tool that the tool map in `integrations/README.md` doesn't show as
connected, a tool reached with a key that its file doesn't list you as holding, or a tool the
broker mentions that has no file.

## Steps

1. **Find out which tool does the job.** If the tool map already names it, the broker uses it: say
   it by name ("Let's set up your Velocity") and skip to step 3. Otherwise ask by the job, not the
   product, and offer the usual answers to make it easy, for example: "Which email do you use with
   your clients: Outlook, Gmail, something else?"
2. **Write the answer in the tool map** in `integrations/README.md`.
3. **Connect it the right way.** When the tool already has a file in `integrations/`, follow its
   "How to connect". Otherwise:
   - **An app** (most email, calendar, file and CRM tools): the broker connects it under Connect
     apps in Grok Bot, with their own account. Tell them exactly where to click and what to pick.
   - **A website without an app:** the broker saves their own login in their own Grok Vault, and
     you sign in with it in the browser. Never ask for the password.
   - **A key** (an API key or a token): only through the secure secret card, saved in Grok's
     Secrets under a clear name. It stays with you, the bot that received it: write in the tool's
     file that you hold it.
   - **A sign-in that needs something only the broker has** (a one-time code, a passkey, an
     approval on their phone): ask them to read out the code as it arrives (it stops working within
     minutes; never save it), or to approve the sign-in. If a sign-in can't work for a bot at all,
     say so, and write it in the tool's file.

   Never another person's account, and never a connection that opens more than this broker's own
   data.
4. **Test it** with one harmless read, such as listing today's emails or opening the client list.
   Then set "Connected" in the tool map to `yes, YYYY-MM-DD`.
5. **Look before you ask.** See how the broker uses the tool: how it is organised (folders, labels,
   lists, stages) and what they keep there.
6. **Ask only what you couldn't see:** what they want their bots to look up, write or change there,
   and anything about the setup that looking didn't settle.
7. **Write the tool's file.** If the tool already has a file in `integrations/`, fill that one in.
   Otherwise make `integrations/<tool>.md` from the block in `integrations/_template.md` (that
   file says how), and add the file's name to the tool map.
8. **Tell the broker in one line** what is connected and what their bots can now do with it.

## If it won't connect

Say in plain words which tool didn't connect and what still works without it. Set "Connected" to
`no`, and write in the tool's file why. Never try a way around it. If you were in your first run,
do what you can without the tool, then pause your onboarding as "Finish" in your `onboarding.md`
says.

## No tool for the job?

Some brokers keep their client list or their conditions in their head or on paper. Offer a simple
spreadsheet in their own files, with only the columns the job needs, and make it if they want one.
It lives in their files, never in the brain, because it holds client details. Then treat it as the
tool for that job.

## Notes

(none yet)
