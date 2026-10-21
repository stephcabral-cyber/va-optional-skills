---
name: claude-mods
description: "What a mod for the Claude desktop app (Claude Code) can and cannot change, what one really costs to build, and how to ask Claude for one. Load it when the owner wants the app to show or do something it doesn't, says 'mod', 'plugin', 'can Claude show me X all the time', 'add a button', 'change the app', or asks why the app lost a feature. Read it BEFORE promising a mod, so the owner hears the cost and the limits first."
---

# Mods for the Claude app

**Version: 1.0 - 2026-10-20**

A mod is a small add-on to the Claude desktop app (the Code tab). Claude writes it for you, it lives on
your computer, and it changes a few things about what the app shows or does. We built and tested several
in October 2026, so everything below is measured, not guessed.

## The honest verdict

**Really good for small things, slow for anything bigger.** A mod that shows one fact on screen all the
time took about ten build-and-reload rounds before it was right. A bigger one (making scheduled runs
easier to see) took an evening and mostly could not be done, because the app does not allow it.

So before building one, say three things out loud to the owner:
1. What it will show or do, in one sentence
2. That it takes a while: several rounds of "change it, reload, check it"
3. Which limit below might stop it

## What a mod CAN do
| You want | Works? |
|---|---|
| One line of info always visible (e.g. how full the conversation is) | Yes. It sits in the status line under the message box, next to the model name. **The best spot for always-on info** |
| A box above the message box | Yes, but it covers the chat. Most people prefer the status line |
| A new slash command (e.g. `/today`) | Yes |
| Something that runs when you send a message or when Claude uses a tool (e.g. a safety check before a send) | Yes |
| A side panel | Yes, more work |
| A pop-up notification | Depends on the computer. Test before relying on it |

## What a mod CANNOT do
- Move, open or arrange windows, or change the sidebar
- Put scheduled routine runs somewhere new on screen
- Change how the app itself looks beyond the pieces above

When the wish is about windows, sessions or routines, ask Claude what the app's own tools can do first.
A mod is not the answer there.

## How to ask for one
Say it in one sentence, then let Claude plan before it builds:

"Make me a mod that shows <the one thing> in the status line. Tell me the plan and what could stop it
before you build anything"

Then:
1. The first time, the app asks to enable hot reloading for the session. Click Enable
2. The mod reloads after each of Claude's turns, so expect "check it now" a few times
3. If a dim line names the mod with an error, copy it and paste it back to Claude
4. When it works, ask Claude to keep a copy in your Memory Vault so a new computer can get it back

## Rules that save time
- **One fact, one place.** Never show the same thing in two spots
- **Stop after two failed rounds** and ask Claude for a different route. Grinding on a mod rarely ends well
- Start a new session to check that the mod loads for every session, not just the one that built it
