---
name: daily-brain-feed
description: "OPTIONAL. Feeds the owner's Memory Vault every day from what happened: everything the inbox handler read that morning (email, and texts, Slack and meeting recordings when connected), reduced to lessons, decisions and updates and written into the right folders. Runs as ONE row in the routines table inside Vera's daily pass, never as its own schedule. Trigger when the owner says 'daily brain feed', 'feed my second brain', 'feed my memory vault from my emails', 'set up the daily feed', 'turn on the brain feed', 'turn off the brain feed', 'brain feed', 'what did you learn this week', or asks Vera to learn from their emails or meetings every day. It is installed with the library but switched OFF: Vera offers it in the day plan once the Memory Vault, Airtable and the daily pass are working, and never switches it on unasked."
---

# Daily brain feed (optional)

**Version: 1.3 - 2026-10-21** (no setup questions: on a yes Vera uses the defaults, says them in one line, adds the Daily brain feed row herself, and runs it once right away so the owner sees what it saved. The offer comes as a question in the day plan. "Turn off the brain feed" switches the row off, and "what did you learn this week?" answers from what it saved. Matches Week 2 Chapter 7.) v1.2 - 2026-10-17 (learns from everything the inbox handler read that morning, not only email and meeting recordings, so a rule agreed by text or a decision made in Slack reaches the vault too. Asks up to three times instead of once, and the owner can turn it on any time by asking. Runs only in the morning run, never on its own cloud schedule. Points at the renamed `inbox-handler`.) v1.1 - 2026-08-24.

**What's new for you (1.3):** Turning on the brain feed is now one word: say yes when I ask in your day plan, or say "turn on the brain feed" anytime. I set it up myself, no questions, add it to your Daily Routines tab, and run it once so you can see what it saved. "Turn off the brain feed" turns it off, and "what did you learn this week?" shows you what it kept.

**What's new for you (1.2):** If you have the brain feed on, it now learns from your texts, your Slack and your meeting recordings too, not just your email, because it works from everything the inbox handler read that morning. If you said no to it before, Vera may ask you again, up to three times in all, and you can turn it on yourself any time by saying "turn on the brain feed."

## Where this sits, and why it is not the inbox handler

**This skill is the MEMORY lane. It keeps what changes how the business runs, and throws away
everything that merely needs doing today.**

`inbox-handler` is the opposite: it keeps what needs doing and throws away everything else.
**Each one's output is the other's rubbish, which is exactly why they are two files.** They also stay
separate because that one is core and this one is optional and heavy: an owner should be able to run
their inbox every day and never turn this on.

**They do share the reading, and reading the same messages twice in one morning is pure waste.**

- **The inbox handler runs first in the pass and does the reading.**
- **This runs later and works from everything that pass already read**: email, and texts, Slack and
  meeting recordings when the owner connected them. It does not go back to any of those sources.
- **If the inbox handler is not installed or did not run**, this reads the sources the owner named
  itself, exactly as described below. It never depends on the other skill being there.

**Neither of them produces its own morning report.** Everything reaches the owner through the day
plan. Three morning messages means one gets read.

**What it is.** Once a day, Vera reads what happened yesterday (email, texts, Slack, meeting recordings), keeps
only what changes how the business runs, and writes it into the Memory Vault. The vault stops being a
thing the owner has to remember to update.

**What it costs.** This is the heaviest thing Vera does: it reads a lot of text every day. Say that
before setting it up. Two rules keep it sane: it reads only the sources the owner named, and it runs
inside the daily pass as a routine row, so it obeys the owner's per-day cap like everything else. It
runs in the morning run on the owner's computer, like the inbox handler, and never gets its own cloud
schedule: cloud runs come out of a limited allowance.

**Who wants it.** Owners with many conversations a day. Owners with few will find it noise: tell
them so and let them decide.

---

## Ask before turning it on, up to three times

It is optional, so it is off until the owner says yes. Ask only after all three are true: the Memory
Vault is saving, Airtable is connected with the routines table, and "Good morning, Vera" has run at
least once. Then ask it as ONE question item in the day plan (v1.3), never as a separate message:

> "I can also save what you decide and learn to your Memory Vault every day, from your email, your
> texts, your Slack and your meeting recordings, so I learn your business without you having to tell
> me. It's the heaviest reading I do. Want me to turn it on?"

- **Yes:** set it up as below, in the same run.
- **No:** log the date in `log.md`. Ask again about 30 days later, and if that is a no, about 90 days
  after that. Each later ask adds one line on what it would have caught since the last ask, taken
  from what the inbox handler read. **After the third no, stop asking for good.**
- **Any time, on request:** "turn on the brain feed" or "set up the daily feed" sets it up, whatever
  was said before. A no never locks the owner out.
- **Turning it off:** "turn off the brain feed" sets its Daily Routines row to Paused and says so in one
  line. Nothing it already saved is removed.

Log every ask and answer with its date, so the count survives across sessions.

## Setting it up (no questions, v1.3)

**Vera does the whole setup herself and asks nothing.** She uses these defaults and says them in ONE
line ("I'll learn from everything your inbox handler reads, look back to the last run, and file things
by your vault layout. Want anything different?"). She changes a default only if the owner asks.

1. **Sources:** everything the inbox handler reads. If the inbox handler is not installed, email (the
   connected mailbox) and the meeting recorder already connected, if any. Never ask for a password. If a
   source cannot be reached from where Vera runs, drop it and say so.
2. **Lookback:** since the last run, capped at 2 days. Never "everything".
3. **Where things go:** by `reference/repo-layout.md`. Defaults: a decision the owner made goes to
   `decisions/YYYY-MM-DD_topic.md`; a rule they stated goes to `policies/`; a fact about the business
   (new vendor, new attorney, new unit) goes to `business/`; a lesson or an open thread goes to
   `notes/YYYY-MM-DD_daily-feed.md`; anything about a tenant, lease or money that should be a record
   goes to the tasks table as a proposed row, never written into Airtable records directly.

Then create ONE row in the Daily Routines tab:

| Field | Value |
|---|---|
| Name | Daily brain feed |
| What it does | Reads yesterday's emails and meeting notes, keeps what changes how the business runs, writes it into the Memory Vault, and proposes tasks for anything that needs a person. |
| Instructions | Load the daily-brain-feed skill and run "The daily run" with the sources and folders recorded there. |
| How often | Daily |
| Active | Yes |
| Prepare and wait | No (it writes only to the vault and to the tasks table as proposals) |
| Order | Last in the pass |

Record the settings (sources, how reached, lookback, destinations) in
`.claude/skills/daily-brain-feed/config.md` in THEIR vault, so the run needs no questions. Push. Add
the skill's row to the skills table.

**Then run it once, right away, in the same session (v1.3),** and show the owner what it saved: the
two or three items that matter and the folders they went to. Tell them the row named **Daily brain
feed** in their Daily Routines tab is how they know it is on, and that "turn off the brain feed" turns
it off.

**"What did you learn this week?"** Answer from what this skill saved: read `log.md` and the files it
wrote in the last seven days, and give the few items that matter, each with the folder it is in.

## The daily run

1. Read `config.md`. Read `log.md` for the last feed timestamp.
2. **Collect** everything new from each source since then, capped at the lookback.
   - **If the inbox pass already ran this morning, take everything it read: email, texts, Slack and
     meeting recordings. Do not read any of those sources again.** That pass has already been through
     every message and knows which ones carry anything. Re-reading them is the single biggest avoidable
     cost in this skill.
   - **If the inbox pass did not run**, read the sources the owner named yourself: mail by subject and
     body, and for a recording the summary first, the full transcript only when the summary shows a
     decision, a rule, a number or a name that matters.
3. **Reduce, hard.** Keep only: decisions made, rules stated, facts that changed, lessons learned,
   commitments with a date, and open threads that need a person. Drop pleasantries, newsletters,
   notifications, anything already in the vault (check before writing, including a people file a text
   already updated, so nothing is written twice), and anything that is only a
   record update (that becomes a proposed task instead).
4. **Write** each kept item to its folder per `config.md`, one item per file or one dated feed note
   with headed sections, in the naming rules of `reference/repo-layout.md`. Quote the source in one
   line (who, when, subject) so it can be checked. Never invent a fact to fill a gap.
5. **Propose tasks** for anything that needs a person: one row each in the tasks table, status not
   started, with the source line. Never send anything, never edit a tenant, lease or money record.
6. **Commit, push, read back.** Append one line to `log.md`: date, sources read, count kept, count
   dropped, count of tasks proposed.
7. **Report** in the daily pass, three lines maximum: what was learned (the two or three items that
   matter), what was proposed as tasks, and anything a source refused to open.

## Guardrails

- **Reads are free, writes go to the vault and the tasks table only.** No email replies, no record
  edits, no sends. The rulebook stands.
- **When the same source fails twice, stop reading it and report it precisely.** Do not retry daily
  in silence.
- **If a day's material is enormous** (a long meeting plus a full inbox), read summaries and subjects,
  keep the top ten items, and say that the rest was skimmed. Better a short honest feed than a stalled
  pass.
- **Nothing sensitive gets copied verbatim.** Numbers, names and dates that matter, yes. Whole email
  bodies, bank details, documents, no. Link or cite instead.
- **The owner can turn it off by saying "turn off the brain feed"** (or by pausing the row). Say so when
  you set it up.
