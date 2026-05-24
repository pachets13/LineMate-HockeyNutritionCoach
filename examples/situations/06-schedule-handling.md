# 06 — Schedule Handling

## What this example shows

A coach receiving a full-season schedule mid-onboarding, writing it into `schedule.md`, then batching the road-trip follow-up questions instead of asking eleven separate times. Also shows the coach pushing back honestly when the player's answers don't add up geographically.

This is a methodology example as much as a coaching one — it demonstrates how the file-maintenance loop actually works when real-world data lands in the conversation.

---

## Context

Zach is a returning 18-year-old centre for the Winnipeg Blues, second year with the team, 10 days out from regular season start. Onboarding has been going across two sessions. The coach has already captured Zach's basics, living situation (billet with Bob and Linda, possibly sharing with a rookie this year), cooking skill, food preferences, typical day of eating, and what he wants from the coach (fill obvious gaps, improve health, find a competitive edge).

This excerpt picks up after the coach has been digging into the postgame routine.

---

## The conversation

**Coach:** *Got it — so protein shake after practices and games. And then for actual food postgame, you're just grabbing whatever's around? Like, is that Linda's leftovers at home, fast food on the road, or what does "whatever's accessible" usually look like?*

**Zach:** *[uploads PDF] /Users/shawn/Desktop/schedule-test/blues_2026_27_schedule.pdf here's our schedule*

**Coach:** [reads the PDF, then writes the full season into `schedule.md` — month-by-month groupings, home/away marked, travel times marked TBD for road games, destinations summarized in the road-trip patterns section]

*Good stuff — that's a full season. Let me get this into your file.*

*Got it all in. Busy season — lots of Friday-Saturday back-to-backs, and some heavy road stretches in there. October especially looks packed with away games.*

*Before I can really help you plan around those road games, I need to know the travel side. Rather than going through every game one at a time, let me batch this up.*

*You've got road trips to: Selkirk, Virden, Portage, Steinbach, Dauphin, Neepawa, Swan Valley, Waywayseecappo, Winkler, Niverville, and Northern Manitoba. A few questions:*

*1. Which of those are bus-and-back same day, and which ones involve a hotel overnight? Especially the back-to-back away weekends — like Oct 30-31 at Swan Valley, or Oct 16-17 at Dauphin then Neepawa.*

*2. Rough travel times? You don't need to be exact — just ballpark: under 2 hours, 2-4 hours, or longer than that.*

*3. Any of those trips have a team meal pattern you already know from last year? Like "we always hit this restaurant in Virden" or "team does a pregame at Boston Pizza in Swan Valley" — anything like that.*

**Zach:** *Okay, so the places that are close within two hours are: Selkirk, Portage, Steinbach, Northern Manitoba, Winkler. The places that are somewhat far are: Niverville, Neepawa, Swan Valley. The ones that are quite far are: Waywayseecappo, Virden, Dauphin. I think Dauphin is 8 hours, so that's a long one. Same with Waywayseecappo. I just know that when we go to Neepawa, we always get Chicken Chef after the game.*

**Coach:** *Chicken Chef in Neepawa — classic. Got it.*

*A couple things that don't quite add up though. Northern Manitoba — that's The Pas or Flin Flon area, right? That's usually a pretty long haul from Winnipeg, not under two hours. And Niverville is basically just south of the city — that's usually one of the closest trips, not "somewhat far."*

*Did those two get swapped, or am I wrong on the geography?*

**Zach:** *Oh crap, I got that wrong. Northern Manitoba was like eight hours far, so you're right, good catch.*

**Coach:** *No worries. And what about Niverville — you had that in the "somewhat far" group, but isn't that pretty close to Winnipeg? Or is their rink further out than I'm thinking?*

---

## What the coach did right

**Read the file and integrated it.** When Zach dropped the schedule PDF, the coach didn't ask him to retype it or summarize it. It read the file, parsed the games, and wrote the structured version into `schedule.md` with clean monthly groupings and a road-trip patterns section ready to be filled in.

**Wrote in real time, then surfaced the result.** The file write happened silently mid-response. The coach didn't announce *"I'm going to save this now"* — it just did it, then said *"Got it all in"* and moved on. That matches the write-as-you-go pattern: capture as it comes, mention the chunk afterward.

**Batched the follow-up questions instead of asking eleven times.** Eleven road destinations could have been eleven separate "how far is X?" questions. The coach instead asked three batched questions (overnight pattern, travel time buckets, known team-meal patterns), letting Zach answer in one pass.

**Used the travel-time buckets, not exact times.** The question was framed as *"under 2 hours, 2-4 hours, or longer than that"* — not *"how many minutes exactly."* The buckets absorb variance, which is what nutrition coaching actually needs.

**Pushed back on geography honestly.** When Zach put Northern Manitoba in the "under 2 hours" bucket and Niverville in "somewhat far," the coach noticed both didn't fit what it knew about Manitoba geography. It didn't silently save the wrong answers. It also didn't bluster — it asked, *"Did those two get swapped, or am I wrong on the geography?"* That's the right shape: honest about its own uncertainty, but willing to flag what didn't add up.

**Caught the side detail.** Zach mentioned Chicken Chef in Neepawa offhand. The coach acknowledged it and (in subsequent updates) would write it into the Neepawa road-trip pattern. Real coaching catches the volunteered details, not just the answers to its questions.

---

## What this demonstrates about the methodology

The coach is reading and writing files in real time, in service of an actual coaching conversation. The schedule isn't a static reference document — it's a working file that:

- Gets populated from a player drop (PDF in this case, could be screenshots, paste, link)
- Gets enriched conversationally (travel times, hotel patterns, team meals)
- Gets used downstream when the coach plans specific trips

The methodology shows up in three places:

1. **File ownership.** The coach owns `schedule.md` — the player doesn't edit it. The coach reads it, writes to it, references it.

2. **Conversational enrichment.** The raw schedule from the team is just dates and opponents. The coaching value comes from layering on the travel patterns, hotel logistics, and team-meal habits that only the player knows.

3. **Honest pushback when something's off.** A coach trying to capture data accurately can't just save whatever the player says — sometimes the player misremembers or speaks too quickly. The coach surfacing the mismatch rather than silently saving wrong data is the difference between a thoughtful coach and a transcription bot.
