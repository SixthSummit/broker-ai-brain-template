# Velocity

**Job:** Mortgage applications. The broker builds their applications (deals) in Velocity, also
called Newton after the company that makes it.

## What lives here

The broker's deals: the borrowers, the property, the mortgage requested, the lender it went to, the
rate, the status, the conditions and the dates. It also holds every borrower's personal and
financial details, which never go in the brain (hard rule 1 in `AGENTS.md`).

## What it is used for

not known yet

## How to connect

With the broker's own Velocity API key, given through the secure secret card and saved in Grok's
Secrets as `VELOCITY_API_KEY`: "Let's set up your Velocity. Paste your Velocity API key in this
secure card." Never in the chat. The broker finds their key on their Velocity Settings page. If they
don't have one yet, they request it there ("Request API Key"), and Newton approves it by email:
meanwhile set Connected in the tool map to `no, key requested YYYY-MM-DD`, and ask once in a later
chat whether the email has come.

The key stays with you, the bot that received it: add your brain name under "Bots holding the key"
below. Velocity is connected for you only when your name is there and
`test -n "$VELOCITY_API_KEY" && echo set || echo missing` says `set`, whatever the tool map says.
Another bot that needs Velocity asks the broker for the key with its own card.

How a call works (VelocityAPI v1, reference: https://developer.newton.ca/velocity/v1/index.html):
the base address is `https://api-velocity.newton.ca/api/forms`, and the key goes in the address as
`apiKey=$VELOCITY_API_KEY`. Read the reference for a call's exact fields before you make it the
first time.

- **Read deals** by status, date range or loan code: `GET /v1/deals`, up to 100 deals a page. Ask
  for the next page until none are left.
- **Search deals:** `POST /v1/deals/search`.
- **Create a contact** (`POST /v1/contacts/contact`) **or a deal** (`POST /v1/deals/deal`): only
  when the broker asks for that one.
- **Nothing else:** no documents, no deleting, no reading contacts. Conditions and notes come only
  as fields inside a deal.

Test it with one harmless read, such as the deals with one status. For what the key can't do, the
broker can save their Velocity login in their own Grok Vault, and you use it on Velocity's own
website.

Bots holding the key: (none yet)

## What the broker uses bots for here

not known yet. Ask the broker what they want their bots to look up or create here, and write it
down.

## This broker's setup

Fill in as you learn it: how they name and find their deals, which statuses they use, what they
want bots to look up here.

(none yet)

## Traps

- **The key is in every call's address.** Never print, log or pass on a call's address, and never
  show a command with the key written out. Call Velocity only with `curl -s`, never `-v`, and never
  with Python, wget or another tool: they print the full address, key included, when a call fails.
  Use the key only as `$VELOCITY_API_KEY`, and check it only with the `test -n` line above.
- **Never print or pass on a Velocity link.** It can carry a live sign-in.
- **A deal or a contact created by mistake can't be deleted with the key.** Check every detail with
  the broker before you create one.
- **Velocity and the client list don't always agree.** When they differ, say which says what. Never
  pick one quietly.
- **Never give a total from one page of deals.** Read every page, or narrow the dates, first.
