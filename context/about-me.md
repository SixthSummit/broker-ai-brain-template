# About me

The broker's basics. The first bot fills them in with the broker ([[brain/joining]]); any bot
completes what is still missing when it needs it.

- **Name:** not filled in yet
- **City and province:** not filled in yet
- **Time zone:** not filled in yet
- **Working days and hours:** not filled in yet
- **Languages I work in:** not filled in yet
- **Years as a mortgage broker:** not filled in yet
- **Brain introduced:** not yet
- **Brain key expires:** not filled in yet
- **Broker reminded about the key:** never

The last three lines are kept by the bots. "Brain introduced" gets the date the first bot explained
the brain to the broker ("The broker's first bot" in [[brain/joining]]). "Brain key expires" gets
the date GitHub gives for the brain key, written by the bot that connects or renews it ("Connect
this computer" in [[brain/joining]]). "Broker reminded about the key" gets the date a bot last
reminded the broker to renew it, so they hear it at most once a day (step 3 in `AGENTS.md`).

**Setting the time zone:** write the zone name that date commands understand. BC on Pacific time
stays on UTC-7 all year: `Etc/GMT+7`. The East Kootenays (Cranbrook, Fernie, Golden, Invermere)
follow Alberta: `America/Edmonton`. Elsewhere, use the zone of the broker's city, which follows the
clock changes: `America/Edmonton` (Alberta), `America/Regina` (Saskatchewan), `America/Winnipeg`
(Manitoba), `America/Toronto` (Ontario and Quebec), `America/Halifax` (the Maritimes),
`America/St_Johns` (Newfoundland). Then check it: `TZ=<zone> date` should show the time the broker
has right now.

## Background

Anything else about the broker as a person that helps their bots work for them: how they got into
mortgages, what they are known for. Dated lines.

(none yet)
