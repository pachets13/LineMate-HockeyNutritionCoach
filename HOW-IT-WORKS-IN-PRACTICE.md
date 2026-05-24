# How this coach works in practice

This coach is hard to demo in 90 seconds. A single conversation shows the basics — pacing, file writing, staying in lane. But the methodology only really shows up across multiple sessions. This page explains why.

---

## The short version

This is not a chatbot. It's a coach that builds a working relationship with one player over time. The first session captures who the player is. Every session after that draws on what came before. By the time the player is six weeks in, the coach knows their billet, their schedule, their routine, what they've tried, what worked, what didn't. That accumulated context is the product.

---

## Session 1: Onboarding

The first conversation lasts about 5-10 minutes. The coach asks who the player is — position, team, age, height, weight, where they're at in the season. Then it asks about their living situation (billet family names, who cooks what, other players in the house). Then cooking skill, food preferences, what a typical day of eating looks like, what they want from the coach.

As the player answers, the coach is writing each piece to files in the project folder — `player-context.md`, `practice-pattern.md`, `schedule.md`. By the end of the conversation, those files contain a real picture of who this player is. Not a generic profile — specific names, specific routines, specific concerns.

The player walks away knowing the coach has them. Next time they open it, they don't have to re-explain anything.

---

## What that captured context enables

Once the coach has the basics, every subsequent conversation can do things a one-shot chatbot can't:

**Reference specific people and places.** *"How's it going at Bob and Linda's?"* not *"How's your living situation?"*

**Anchor advice in the player's actual life.** When the player asks what to eat before tomorrow's game, the coach already knows tomorrow is a 7:30 PM home game vs. Selkirk, the player's pregame meal of choice is chicken and rice four hours out, and the billet cooks dinner at 6:30. The advice lands on real ground.

**Hold accountability across time.** If session 3 ended with *"let's try a sports drink between periods this weekend,"* session 4 opens with *"how'd the sports drink test go?"* The player doesn't have to remember what they agreed to — the coach does.

**Notice patterns.** *"This is the second time you've mentioned feeling slow late in third periods after Friday games. Want to dig into that?"* Pattern recognition only works when there's a record to recognize patterns in.

**Adjust to changes.** When the player gets traded mid-season, the coach doesn't start over — it asks what's changed (new team, new billet, new schedule), updates the files, and keeps moving. The food preferences, cooking skill, and what the player wants from the coach carry over.

---

## Session 5: What it feels like by mid-season

The Marcus arc in `examples/arc/marcus-an-arc.md` shows this in full detail — five sessions from a week before training camp through six weeks into the regular season. Marcus walks in nervous about feeding himself away from home and walks out, by session 5, with a working routine: eggs and toast breakfast, sandwich lunch, chicken and rice four hours pregame, sports drink between periods, postgame meal he eats even when not hungry.

By session 5, the coach knows:

- Marcus is 17, first-year defenseman, billeting with Karen and Steve and sharing the room with Tyler the second-year forward
- His pregame timing is locked in and shouldn't be messed with
- The locker room ragged on his "kid food" eating early in the season and the coach validated his pattern was working
- He once tested an earlier pregame meal that didn't go well — they know not to try that one again
- The Brandon road trips are overnights with hotel pregame meals; Steinbach trips are same-day with team food stops on the way home

The session 5 conversation reads like talking to a coach who has been paying attention all season. Because, in effect, it has.

---

## What this is and isn't

It is: a working coach for the day-to-day nutrition questions that come up in junior hockey life.

It isn't: a replacement for a registered dietitian, a strength coach, or a doctor. The coach hands off — warmly and explicitly — when it sees aggressive weight changes, supplement protocols, body composition programs, mental performance concerns, or any sign of disordered eating. Real coaching means knowing where your lane ends.

A real player would use this alongside the support system they already have — team trainers, coaches, billet hosts, parents, and ideally a dietitian for the things that need clinical eyes. The coach fills the gap where most junior players currently get nothing: the daily *"what should I actually do tomorrow morning"* level of support.

---

## How to evaluate this

Reading this one-pager is the appetizer. The substance is in two places:

1. **`examples/arc/marcus-an-arc.md`** — the full five-session arc. Read this if you want to understand what the coach does over time.
2. **The coach itself.** Clone the repo, run it in Claude Code, do a real onboarding. The methodology is more obvious when you experience the file persistence yourself than when you read about it.

A 90-second demo can't show what builds over five sessions. But five sessions is the point.
