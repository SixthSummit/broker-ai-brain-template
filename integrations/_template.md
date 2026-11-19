# Template for a tool's file

This is not a tool. When the broker starts using a tool that has no file yet, copy what is between
the two lines of three backticks below (not those lines themselves) into a new
`integrations/<tool>.md` ([[skills/connect-a-new-tool]]), and fill it in. Never edit this template
itself. Write only what you know: leave a part as "not known yet" rather than guess.

```
# <Tool name>

**Job:** which job in the tool map this tool does, such as "Client list (CRM)".

## What lives here
The information this tool holds for the broker, and what is the master copy of what.

## What it is used for
How the broker uses it day to day.

## How to connect
How bots reach it: an app connected under Connect apps, a website login the broker saved in their
own Grok Vault, or a key in Grok's Secrets (its name only, never the value, and which bots hold
it). Whose account it is, never the username.

## What the broker uses bots for here
What the broker wants their bots to look up, write or change in this tool.

## This broker's setup
Where things are: folders, lists, labels, fields, stages, saved reports. Dated lines as you learn
them.

## Traps
What goes wrong easily in this tool, as you find it.
```
