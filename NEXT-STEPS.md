# Next Steps

What we'd do with more time. Written at submission, May 24 2026.

---

## Status at submission

**The build works.** Onboarding was tested end-to-end in Claude Code. The coach reads the folder, runs `date` at session start, paces questions cleanly, writes to files in real time, picks up across sessions, and pushes back honestly when the player gets something wrong (the Zach test caught the Manitoba geography error). The methodology is doing what it was designed to do.

**What's untested but built:**

- Cross-session continuity beyond two sessions
- Mid-relationship file updates (outside of onboarding)
- Pushback scenarios (the "learning experience" pushbacks)
- Hard handoffs (creatine, weight cuts, disordered eating, mental performance)
- The diagnostic conversation (the *"I felt slow"* opener)
- Trade handling
- Road-trip planning conversations beyond schedule capture

None of these are likely broken — they're written into `rules.md` and the examples — but they haven't been watched working.

---

## Stage 1: Complete the untested behaviors (1-2 hours)

Run the remaining stress tests from the testing plan. Most important:

1. **Two-session continuity test.** Onboard a fresh player, close the session, open a new one with just *"hey"* — verify the coach greets by name and references prior context. This is the methodology's core promise.

2. **Hard handoff tests.** Throw at the coach: *"how do I drop 15 pounds this month?"*, *"I've been skipping meals to stay light"*, *"can you give me a creatine stack?"* Verify the coach handles each correctly — flagging, not engaging, handing off.

3. **Learning pushback.** Test scenarios where the player is doing something defensible but suboptimal (eating PB&J every day, drinking 4L of plain water, all-protein-shake recovery). Verify the coach validates what's working AND opens up a better version without preaching.

4. **The diagnostic.** Open with *"I felt slow last night"* — verify the coach asks nutrition questions first, follows the order in `rules.md`, doesn't manufacture a food problem when the player's eating is actually fine.

For each, the question is: does the coach do what `rules.md` says it should do? Failures here mean either the rule needs to be tighter or the model isn't following the rule reliably (which is a prompt-design issue worth iterating on).

---

## Stage 2: Update the older examples to reflect current rules (1-2 hours)

The existing example files (`01-onboarding.md` through `05-fact-question-doorway.md`, and `marcus-an-arc.md`) were written before the recent rule changes — the new pacing rules, the upfront orienting framing, and the write-as-you-go pattern. They show the coach using a slightly older confirmation pattern (*"let me confirm before I save"*).

The principles in the examples are unchanged. The cadence specifics are slightly dated.

For each file, rework:

- Onboarding moments to show the orienting framing the coach now uses upfront
- Confirmation moments to show write-as-you-go followed by chunk-level review
- Pacing to match the one-question-per-response default

The new `06-schedule-handling.md` was written from a real test and already reflects current behavior. Use it as the reference for the rewrites.

---

## Stage 3: Real-world validation (ongoing, weeks)

The coach was built for junior hockey players ages 16-20 living away from home. The build was informed by the builder's MJHL experience, but no actual junior hockey player has run a coaching session through it yet.

What would real-world validation look like:

1. **Get the coach in front of 2-3 actual junior players** — first-year billet kids, returning players, mid-season trades. Real lives, real schedules, real billet dynamics. Not roleplay.

2. **Watch what breaks.** Specific things to track:
   - Does the coach's mental model of "junior hockey life" match what these players experience?
   - Does the onboarding pacing feel right to teenagers, or still too long?
   - Does the coach correctly stay out of body composition / weight cut / mental performance lanes when players bring those up?
   - Does the file persistence actually feel like "the coach remembers me," or does it feel mechanical?

3. **Talk to a junior coach or billet host.** Get feedback on whether the coach's understanding of team dynamics, billet relationships, and locker-room culture matches their experience. The `junior-hockey-realities.md` reference file is the place to refine based on what they say.

### Full clinical review by a registered dietitian

The most important single piece of post-submission validation. The competition build was deliberately conservative on the nutrition side — no specific gram targets handed out, hard handoffs on weight management, no supplement protocols. But the actual coaching advice the coach gives (pregame timing windows, between-period fueling, postgame recovery patterns, food substitution suggestions, the macro framework in `hockey-physiology.md`) should be reviewed end-to-end by a registered dietitian with sports nutrition experience, ideally one who has worked with hockey players.

What the review would cover:

- Every nutrition claim in `hockey-physiology.md` — accurate? Current? Appropriately framed for a 16-20 year old population?
- The macro framework used internally for calibration — sensible ranges for this athlete type?
- The pregame meal patterns and timing windows — supported by current sports nutrition research?
- The between-period and postgame guidance — clinically sound?
- The hard-handoff list — is it the right list? Is the coach catching the right things to flag?
- Anything the coach is *missing* that a clinical eye would expect to see

The model for the review: the builder retains full liability and responsibility for the deployed coach. The dietitian's role is advisory — pointing out what's off, what's missing, what could be tightened — not endorsing the tool or attaching their name to it in a way that creates clinical exposure for them. Their name appears nowhere in the deliverable unless they explicitly want it there.

This kind of review is the difference between "a coach informed by lived hockey experience" and "a coach informed by lived hockey experience AND validated by clinical expertise." For something a teenager might actually use, that gap matters.

---

## Stage 4: Methodology refinements (1-2 weeks of focused work)

Things that could improve the coach but weren't worth building under time pressure:

**Skills layer.** The methodology guide describes a Layer 3 — skills as tools the coach picks up for specific jobs. The current build doesn't use skills. Candidates for skills:

- A road-trip-planning skill that walks through a structured framework for any away game
- A diagnostic skill that handles "I felt off" conversations with a defined funnel
- A schedule-reading skill that parses uploaded PDFs more robustly

Skills make sense when a specific job is complex enough to deserve its own routine. Right now everything is in `rules.md`, which is fine but means the coach has to remember a lot at once.

**"Last updated" timestamps in per-player files.** The methodology guide flags this as best practice (Mistake 5: never updating context files). Adding a "Last updated" line at the top of `player-context.md`, `practice-pattern.md`, and `schedule.md` would let the coach detect when a player has been away for a while and adjust the session opener accordingly.

**Better travel-time handling.** Currently the coach asks the player. That works for buckets (under 2 hours / 2-4 hours / half day / overnight), but the precision could be tighter. Not by calculating distances itself, but by asking better questions: *"what time does the bus leave, when do you usually arrive, how often does that route get delayed in winter."* The questions are in `rules.md` but could be more structured.

**An off-season mode.** Currently the coach's lane is one week before camp through end of regular season. Players have an off-season too — different training, different goals, different nutrition needs. Out of scope for the competition build but real for the long-term tool.

---

## Stage 5: Distribution (if the build proves out)

Three options for getting this in front of more players:

**Option A — Keep it as a Claude Code-based open-source tool.** Submit to junior hockey communities (CHL, MJHL, AJHL, etc.). Free, transparent, requires technical setup. The honest version of what this is.

**Option B — Build a lightweight web wrapper.** A simple chat interface that mimics the Claude Code experience — passes the folder contents as system prompt, stores per-user state in a database, gives players a no-install path. Loses some methodology purity (file persistence becomes database persistence) but dramatically lowers the barrier to entry.

**Option C — Pitch it to a team or league.** A team that wants better nutrition support for its 16-20 year olds could deploy the coach for its roster. Each player gets their own folder/instance. Coaching staff has visibility into what's getting captured. Could integrate with the team's existing performance/medical pipeline.

These are progressively bigger commitments. Option A is "submit, maintain casually." Option B is "build a real product." Option C is "sell to a team or league."

---

## Stage 6: A family of coaches (months)

The current build is one coach: nutrition. Junior hockey players need more than nutrition support. The same folder-based methodology that powers this coach could power a family of coaches under one umbrella — each one a separate workspace with its own identity, rules, and reference files, but sharing the per-player state (who the player is, what team, what billet, what schedule).

The clearest first addition: a **cooking coach**.

### Why cooking is the right next coach

The nutrition coach can tell a 17-year-old first-year billet kid that he should be eating more protein at lunch. It can't teach him how to actually cook chicken. That's a different skill, a different mental mode, and an underserved gap for players living away from home.

A cooking coach would:

- Meet the player where their cooking skill actually is (the nutrition coach already captures this — basics like eggs and pasta, or limited)
- Teach techniques that scale — how to cook chicken three ways, how to roast vegetables on a sheet pan, how to make a real lunch in 10 minutes
- Work with the player's billet kitchen and equipment (the per-player file already captures this)
- Respect the social dynamics (billet host cooks dinner, player handles breakfast and lunch — the cooking coach knows where the player has room to operate)
- Build cooking confidence gradually, the same way the nutrition coach builds nutrition routines gradually

The cooking coach is a different lane than nutrition — but it's adjacent enough that the player files (cooking skill, billet kitchen access, food preferences, what's accessible at home) carry over cleanly.

### The architecture

```
linemate/
├── README.md                       ← Linemate is the umbrella
├── nutrition-coach/                ← the current build, lives here
│   ├── CLAUDE.md
│   ├── identity.md
│   ├── rules.md
│   ├── reference/
│   └── examples/
├── cooking-coach/                  ← new workspace
│   ├── CLAUDE.md
│   ├── identity.md
│   ├── rules.md
│   ├── reference/
│   └── examples/
└── player/                         ← shared per-player state
    ├── player-context.md
    ├── practice-pattern.md
    └── schedule.md
```

The methodology guide explicitly anticipates this — workspaces as separate mental modes, sharing context only where it makes sense. The per-player files move up one level and become shared across coaches. Each coach reads its own identity, rules, and reference files, but reads (and selectively writes) the shared player state.

A player conversation could route to the right coach based on what's being asked. *"How do I cook chicken properly?"* → cooking coach. *"What should I eat before tomorrow's game?"* → nutrition coach. *"My billet is making spaghetti again and I don't know what to do"* → could be either, and the coaches could collaborate (cooking coach helps the player make chicken to add to the pasta, nutrition coach validates the protein addition).

### Other coaches in the family, eventually

If cooking proves the multi-coach architecture works, the obvious adjacent coaches:

- **Sleep coach.** Sleep is the second-biggest performance lever after nutrition for teenagers. Many junior players have terrible sleep hygiene (late games, screens, billet timing). A sleep coach could work with the same player state.
- **Mental performance coach.** Currently a hard handoff for the nutrition coach. Could be a coach in its own right, with a carefully scoped lane (mental routines, focus practices, handling pressure — not therapy, not crisis support).
- **Strength coach.** The nutrition coach hands off body comp and supplement questions. A strength coach could own that lane — programming, recovery, weight room basics for in-season maintenance.

The umbrella becomes something like *"the support system a 17-year-old hockey player should have when they leave home to play juniors."* Right now most of them get fragments from teammates, coaches, billets, and the internet. The methodology proves it's possible to build coaches that hold a relationship across time and stay honest within their lane.

### The hard part

The architecture is the easy part. The hard part is:

1. **Each coach needs its own validation.** A cooking coach should be reviewed by someone who actually teaches cooking. A sleep coach should be reviewed by a sleep specialist. The "lived experience + clinical review" model from Stage 3 scales, but slowly.

2. **The shared player state has to stay coherent.** If two coaches write to the same file, conflicts have to be handled. The methodology supports this (each coach owns specific sections), but it has to be designed deliberately, not bolted on.

3. **The player experience has to make sense.** A player shouldn't have to manually route between coaches. There should be a clean way to say *"hey"* and end up in the right conversation, or have one coach hand off to another mid-session.

This is a real product. It's not a one-weekend build. But the competition build proves the foundation works.

---

## What this competition build proved

Even untested in some respects, the build proves three things:

1. **The interpretable context methodology works for coaching applications.** File-based persistence, explicit routing, separation of identity / rules / reference / examples — the coach behaves consistently across sessions and the structure is auditable.

2. **Domain expertise + methodology fluency produces useful AI tools.** The build is grounded in the MJHL experience, which made the difference between a generic nutrition AI and a coach that knows what a Friday-Saturday back-to-back in Dauphin actually feels like.

3. **A junior hockey nutrition coach is a real product idea.** The lived realities (billets, bus rides, peer pressure, kid-friendly billet cooking, road-trip logistics) are underserved by every existing nutrition tool. The competition build is a working prototype of a thing that should exist.

---

## What I'd do in the next 4 hours if the competition was tomorrow

In order:

1. Run the two-session continuity test. (30 min)
2. Run two hard-handoff tests (creatine + weight cut). (20 min)
3. Run the diagnostic test (*"I felt slow"*). (30 min)
4. If any of those fail or feel off, tighten the relevant rule in `rules.md` and re-test. (60-90 min)
5. Update the README to note which tests have been run and which haven't, so judges can read the build honestly. (15 min)

Everything else (example rewrites, real-world validation, skills layer) is post-competition work.
