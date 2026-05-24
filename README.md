# Hockey Nutrition Coach

A folder-based AI coach for junior hockey players (ages 16-20) navigating nutrition while living away from home — billets, bus trips, hotels, team meals, all of it.

---

## How to use this

This coach runs in **Claude Code**. The whole experience depends on Claude being able to read and write files, which only Claude Code supports.

1. **Install Claude Code** if you don't have it: [claude.com/product/claude-code](https://www.claude.com/product/claude-code)
2. **Clone or download this repo**, then open a terminal and `cd` into the folder.
3. **Run `claude`** to start a session.
4. **Say hi.** The coach will introduce itself and onboard you conversationally if you're new, or pick up where you left off if you've used it before.

That's it. No setup steps, no file editing, no configuration. The coach figures out what it needs and asks you for the rest.

---

## What to expect

The coach asks questions before answering. It listens. It pushes back when something doesn't add up. It holds you accountable to what you said you'd try. It remembers your billet, your routine, your schedule between sessions — because it actually writes those things to files in this folder.

As you talk, the coach writes what it learns about you into reference files in real time, so it remembers between sessions and nothing's lost if you have to stop partway through. If it captures something wrong, just tell it and it'll update the file.

It's a coach, not a knowledge base. If you ask "what should I eat before a game," you won't get a Wikipedia article on sports nutrition. You'll get a conversation about *your* game, *your* schedule, *your* living situation.

---

## What's in this folder

- `CLAUDE.md` — the map Claude reads when you start a session
- `identity.md` — who the coach is
- `rules.md` — how the coach coaches
- `reference/` — background knowledge (hockey physiology, junior hockey realities) and per-player files the coach maintains as you talk
- `examples/` — example coaching conversations you can ask the coach to walk you through if you want to see how it works

You don't need to read any of these to use the coach. They're how the coach works. Just start a Claude Code session and say hi.

---

## About

Built for an interpretable context methodology competition. The build uses the folder-as-architecture approach — each file does one job, routing is explicit, and the coach maintains state across sessions through reference files it reads and writes.

The domain (junior hockey nutrition, ages 16-20) was chosen from the builder's own experience playing in the MJHL.

Feedback welcome. If you're a junior hockey player, a coach, a billet, or a dietitian working with junior players and you see something off, that's exactly the input that would make this better.
