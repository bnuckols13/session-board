# Session board

A one-page, self-contained session board for screen-sharing in individual sessions. The agenda across the top is the session's path; each stop is one screen.

It holds no patient data. Everything typed stays in the browser tab (sessionStorage) and is gone when the tab closes. Nothing is sent anywhere.

## Stops

| id | Screen |
|---|---|
| `checkin` | Feelings tiles and a 0 to 10 scale |
| `questions` | A quiet screen while questions are asked out loud |
| `onething` | Pick one card: comic, skin picking map, or food quest |
| `glimmers` | Add glimmers (small good moments); each one lights the ally's lantern and becomes an ally move on the quest |
| `quest` | Food quest: hero, villain, ally, a quest map of steps, and an exposure tracking sheet with a -10 to +10 thermometer and a personal green zone (before, highest or lowest, end) |
| `comic` | A school day in 4 panels |
| `hands` | Skin picking: when, how often, what else hands could do |
| `free` | Free time: how often bored, what to do next time |
| `pick` | Closing choice, who to tell, something to try this week |

With no setup link the path is `checkin`, `onething`, `pick`.

## Setup link

A setup link can prefill a session through the URL fragment: `#q=` followed by base64url JSON.

```
{"h": hero, "v": villain, "a": ally,
 "s": [up to 8 step names], "c": [done counts per step],
 "g": [{"k": kind, "t": text}, ...], "z": [green zone low, high],
 "f": [["checkin", 5], ["glimmers", 5], ...]}
```

Every field is optional. `f` sets the stops, their order, and their minutes. Glimmer kinds: sound, sight, touch, animal, person, place, movement, interest, warmth, quiet.

Browsers never send the fragment to the server, and the page removes it from the address bar after reading it.
