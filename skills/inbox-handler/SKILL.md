---
name: inbox-handler
description: "Read everything new that came in for the business, on every channel the owner connected (email always; texts, Slack and meeting recordings when connected), and triage it: a prioritized brief folded into the day plan, drafted replies for routine items (drafts only, never sent on any channel), and anything urgent flagged. Works for any business, landlord or not, in the owner's own industry words. Sorts everything into seven groups any business uses: urgent, needs your review, drafted for you, waiting on, money, read later, and promo ready to archive, with promises made on calls caught as items. Trigger when the owner says 'check my inbox', 'run my inbox', 'triage my email', 'what came in', 'daily brief', 'anything urgent', 'check my texts', 'anything in Slack', 'handle my mail', or when the morning run or a routines row invokes it. Formerly named landlord-inbox-handler: any routines row or request that still says landlord-inbox-handler means THIS skill. Never sends anything and never makes rental decisions about applicants or tenants."
---

# Inbox Handler

**Version: 1.6 - 2026-10-21** (seven groups any business uses replace the eight landlord-shaped categories: urgent, needs your review, drafted for you, waiting on, money, read later, promo ready to archive. The landlord handling moves into the industry table. The skill never archives; once the promo list has been right for two weeks it suggests the owner set up auto-archive in their own email. People files are read every morning when they exist and named in the plan. Texts not connected is said once, not every morning. Promise 2 now reads "never says yes to changing an agreement". Also: a dated note goes into a person's people file when something worth keeping comes up; Claude replaces its OWN out-of-date drafts that nobody edited and leaves edited ones alone; reply drafts go in the original thread; your CRM can be the who's-who source; and it runs before the day plan, reusing the task list Vera already read.) v1.5 - 2026-10-17 (renamed from `landlord-inbox-handler`, because it was never only for landlords. It now reads every channel the owner connected, not just email: texts, Slack and meeting recordings, each sorted into the same categories and run through the same rules. When texts cannot be read it uses the owner's people files if they exist, and every brief opens by naming the channels it read and the ones it could not.) v1.4 - 2026-10-06 (mail addressed to someone else on your team is theirs to answer, so Claude drafts nothing for it from your mailbox; and every run starts by listing the earlier drafts that someone has since answered, so your Drafts folder never fills with stale replies). v1.3 - 2026-09-29 (drafts read your written policies first, look up the facts first, read every earlier conversation with the person on every channel (email incl. Sent, texts, the platform thread), never say yes to changing an agreement, never reply to a no-reply address, and every "I'll look into it" comes with a proposed solution in the brief. Examples adapt to YOUR industry.) v1.2 - 2026-08-24.

**What's new for you (1.6):** Your inbox is now sorted into seven groups that fit any business: urgent, needs your review, drafted for you, waiting on (things you asked and haven't heard back on), money, read later, and promo ready to archive. I never archive anything myself, but once the promo list has been right for a couple of weeks I'll offer to help you set up auto-archive in your own email. If you keep people files, I read them every morning now too, and add a short dated note when I learn something worth keeping about someone. Replies are drafted inside the original conversation, never as a new email. When one of my own drafts goes out of date, I replace it with an updated one, but if you've edited a draft I never touch it. And if your customers live in a CRM, I can use it to know who's who. You don't need to set anything up: the first time, I add it to your morning run myself, run it once with you, and ask if you want it every morning.

**What's new for you (1.5):** This skill has a new name, the inbox handler, because it was never only for landlords. It now reads more than email: your texts, your Slack and your meeting recordings too, when you have them connected, and your morning brief tells you which ones it read. Nothing is ever sent on any channel. To get the most from it, connect Slack and your meeting recorder (in Claude: Customize, then Connectors), then tell Vera which Slack channels matter.

## Where this sits, and the two skills it is confused with

**This skill is the ACTION lane. It reads what came in since the last run, on every channel, and turns it into things to do today.** That is
its whole job, and everything below serves it.

It gets confused with `daily-brain-feed`, because both read the same morning's messages once a day as a routine
row. **They are not the same job and neither replaces the other:**

- **This skill keeps what needs doing.** A leak, a quote, a question, a decision. Its output is
  short-lived and it is thrown away once acted on.
- **`daily-brain-feed` keeps what changes how the business runs**, and throws away everything
  actionable. Its output is permanent and it goes into the Memory Vault.

They are opposites, which is exactly why one file cannot do both: each one's output is the other's
rubbish. **They also stay separate because this one is core and that one is optional and heavy.**
An owner should be able to run this and never turn that on.

**What they DO share is the reading, and reading the same mailbox twice in one morning is pure
waste.** So: **this skill runs first in the pass and does the reading. `daily-brain-feed` runs later
and works from what this pass already read, on every channel, rather than going back to the sources.** It only
reads a source directly on a morning when this pass did not run.

**And the brief does not go to the owner as its own message.** See "Running this every morning".

Your inbox is where your business actually happens, and for most owners it is not one inbox. Email, texts, Slack and the calls you recorded all carry requests, promises and problems. This skill makes Claude your first-responder across all of them. Once a day (or whenever you ask), Claude reads what is new on every channel you connected, sorts the business items from the noise, writes you a short prioritized brief, drafts replies for the routine stuff, and flags anything that cannot wait. For a landlord that is the leak, the lease question and the vendor quote. For a coach it is the refund request and the student who is stuck.

**Three hard promises this skill keeps, always:**

1. **Drafts only, never auto-send, on any channel.** Every email reply Claude writes lands in your Drafts folder or in the chat for you to review. A reply to a text or a Slack message is written out in the brief for you to copy and send yourself. You are the only one who ever hits Send.
2. **Never says yes to changing an agreement.** Taking someone off, adding someone, a refund, a waiver, an extension, a price or scope change: the draft states your written policy or holds, and the decision comes to you. For landlords this also means Claude never decides, recommends, or implies who should get, keep, or lose a rental (see the Fair Housing / FCRA guardrail below).
3. **Never deletes, archives or forwards.** The only thing Claude ever clears is its OWN out-of-date draft that you never edited (rule 8). Claude never deletes, archives, or forwards your mail, and never sends, deletes or reacts to a text or a Slack message, unless you explicitly ask in the moment.

---

## The channels it reads (v1.5)

**Email is always on. Everything else is read only if you connected it, and the brief says which ones it read.** Every item from every channel goes into the same seven groups and the same "Before drafting any reply" rules below. A leak reported by text is the same leak as one reported by email, and a promise made on a call is as real as one made in writing.

| Channel | What it reads | What you get | When it cannot read it |
|---|---|---|---|
| **Email** | New mail since the last run, plus your Sent folder | Drafts in your Drafts folder | Stops and says so, because email is the core of this skill |
| **Texts** (SMS / iMessage) | New texts with people you do business with, when your setup lets Claude read them on your computer | The suggested reply, written in the brief for you to send | If texts were never connected, Claude says so ONCE, at setup, and leaves them off the plan after that. If they are connected and fail on a given morning, one line: "texts not read today" |
| **People files** (optional) | The vault's people files, one per contact, every morning they exist | Context for every draft and item: who this person is, what was agreed, what was said before | Nothing: an owner with no people files simply has none, and the plan does not mention them |
| **Slack** | The workspaces, channels and direct messages you named in setup | The suggested reply, written in the brief | One line saying so |
| **Meeting recordings** | Summaries of calls recorded since the last run (Fathom, Fireflies, Otter or whatever recorder you connected). The full transcript only when a summary shows a promise, a decision or a deadline | Every follow-up you promised, as an item. A draft email when you promised to send something | One line saying so |

**Texts can only be read on your computer.** That is one more reason this skill runs as a row in your morning run, which runs there. If your texts are not connected, nothing breaks: it reads what it can and the brief names what it skipped.

**People files are optional, and read every morning they exist (v1.6).** They are written by the optional texts feed or by Vera as she learns about someone. They are read whether or not texts were readable, because they carry what was agreed and said before, on every channel. Before an owner has any, nothing is said about them.

**Claude also adds to them (v1.6).** When an item teaches something worth keeping about a person (a deadline they gave, what was agreed, how they like to be reached, a preference), Claude appends ONE dated line to that person's existing people file: a summary in its own words, never a pasted message. It never creates a new people file without asking the owner, never writes to one if the owner has no people files at all, and never writes what is only a to-do (that belongs in the plan). The optional brain feed works from this same pass and does not write the same fact twice.

**Nothing leaves on any channel.** No text or Slack message is ever sent, and nothing from a call recording is quoted to anyone without you seeing it first.

---

## Setup (once)

This skill uses YOUR email account through YOUR connector. Claude never holds your password.

1. **Connect your email provider.** In Claude's connector settings, connect **Gmail** (Google Workspace connector) or **Outlook / Microsoft 365** (Microsoft connector) and sign in through the provider's own login screen. Claude only needs read and draft-create access; do not grant send permissions if your provider offers granular scopes.
2. **Tell Claude your setup** the first time you run the skill. It will ask for and remember:
   - Which mailbox to watch (your main inbox, or a dedicated folder/label like "Rentals" if you already filter).
   - Where your customers and contacts are recorded: your hub, or your CRM if that is where they live (v1.6). For a landlord that is properties, units and tenants; so mail can be matched to the right place. If Vera has written your base file, read that instead of keeping a second list here, because two lists drift apart.
   - **Which other channels to read:** your texts, which Slack workspaces, channels and direct messages, and your meeting recorder. Each one is optional. Claude never asks for a password; anything not connected is skipped and named in the brief.
   - Your preferred vendors (plumber, electrician, handyman) so vendor mail is recognized.
   - Your emergency line: what YOU consider drop-everything urgent (the Urgent group below has a starting list).
   - **What business this inbox serves**, in one line (rentals, coaching, an agency, a course, a service trade). Most owners run more than one. The drafts and the brief use that business's words, and the examples in "Before drafting any reply" are picked from it.
   - **Where your written policies live, one file per business.** The rules you already apply without thinking: who can come off an agreement and how, refunds, what is included, who pays for what, how people reach you. If you have no such file yet, Claude starts one per business and adds a rule ONLY after you approve it. A policy that lives only in your head cannot be followed by anything else.
3. **Optional: labels for the seven groups.** If you want Claude to also label triaged mail with its group (Gmail labels or Outlook categories), say so during setup. Labeling is off by default; the brief works without it. Labeling never moves mail out of your inbox.

No properties list yet? The skill still works. Claude will infer property context from the emails themselves and ask you when it cannot tell.

---

## Before drafting any reply (v1.3)

**Why this exists.** A customer on a shared agreement wrote in to be taken off it. An auto-drafted
reply said "I can help get you removed" and promised to fix a co-customer's portal access. The owner's
real rule was that nobody comes off unless the people who stay can qualify on their own, and it was
written down nowhere the drafter could read. So it guessed, and it guessed yes. The same draft was
addressed to the platform's no-reply address, and it had not checked who was actually on the
agreement. Nine rules, in order (7 and 8 were added in v1.4 and changed in v1.6; 9 was added in v1.6):

1. **Read your policy file for that business first.** If the answer is there, draft from it. If it is
   not, do not invent one: write a holding reply and list the question in the brief with a proposed
   rule for you to approve.
2. **Look up the facts before writing a word,** in your hub or your CRM. Who is on the agreement, what they bought, what they
   owe, what is already open for them. A draft that does not match your records is wrong however well
   it reads.
3. **Read what has already been said to them, on every channel, before drafting.** Your email in both
   directions (including Sent, and every mailbox you use for this business), your texts if your setup
   lets Claude read them on your computer, and the platform's own message thread. If you already
   answered by text, made a promise, or the facts changed, the draft follows that and the brief says
   where it came from. If two channels disagree, the draft holds and the brief shows the conflict with
   a proposed resolution. A run that could not see a channel (texts from a cloud run, for example)
   says so in the brief, rather than implying there was nothing there.
4. **Never draft a "yes" to changing an agreement.** Taking someone off, adding someone, a refund, a
   waiver, an extension, a price or scope change. The draft states your written policy or holds, and
   the decision comes to you in the brief.
5. **Reply to a real address.** Never to a notification sender (`no-reply@`, `notifications@`, a
   platform's alert address). That reply goes nowhere. Answer inside the platform's own messaging, or
   at the person's real email from your records.
6. **Promise only what is done or assigned.** "I'll get that fixed" only if it is already fixed or
   someone owns it. Otherwise say what happens next and by when, and the brief carries a proposed
   solution (see "The daily brief").

7. **Check whose conversation it is.** Read the To and Cc, not just the From. If the message was
   written to a teammate (your VA, a partner, a shared address such as `leasing@`) and you only got a
   copy, it is their conversation. Claude drafts nothing for it from your mailbox, because they will
   usually answer it themselves within hours. The brief lists it in one line under **Your team's
   threads** so you still see it. If setup told Claude it can open that teammate's mailbox, it checks
   their Sent folder first and, if a reply is still needed, drafts it there under their name.
8. **Keep your Drafts folder current (v1.6).** After the new drafts are written, Claude looks at the
   drafts it made on earlier runs and checks your Sent folder (and any teammate mailbox it can open)
   for a reply sent after the draft, on the same thread or to the same person. It reads that reply's
   body, because a reply about something else does not count. It also checks whether the facts behind
   the draft changed. For a draft that is out of date:
   - **If it is still exactly what Claude wrote,** Claude clears it and, if a reply is still needed,
     writes an updated one in the same thread. Claude keeps a short log of the drafts it creates (in the
     vault, next to the policy files) so it can tell its own untouched drafts from edited ones.
   - **If you edited it, or Claude cannot tell,** it never touches it. It lists it in the brief under
     **Out of date, your call**, with who replied and when.
   - **If the email connector cannot delete drafts,** it lists every out-of-date draft for you instead.

9. **Reply inside the original conversation (v1.6).** A reply draft is created as a reply to the
   message it answers, so it sits in the same thread with the history underneath (Gmail: reply to that
   message's id; Outlook: a reply draft on that message). A new thread is only for a brand-new message
   with nothing to reply to. A draft sitting outside its thread loses the history and reads as a cold
   open.

**Why 7 and 8 exist (v1.4).** A tenant wrote to the owner's assistant, and a copy landed in the
owner's inbox. The early morning run drafted a reply from the owner's mailbox, in the owner's name. The
assistant answered the tenant a few hours later, and the draft sat in Drafts looking like unfinished
work. It happened twice in one week before anyone noticed.

**The same rules in your industry.** Claude picks the row that matches the business you named in
setup, and writes the drafts in those words:

| Rule | Landlord | Coach / course creator | Agency / service business | Trades / home services |
|---|---|---|---|---|
| Policy first | Who can come off a lease, and how | Refunds, pausing, how long access lasts | What a retainer covers, revision limits | Warranty terms, deposit and cancellation |
| Facts first | Who is on the lease, is rent current | What they bought, where they are in the program | The signed proposal, what is invoiced | The quote they signed, job status, payments |
| Read every channel first | You already texted the tenant the plumber comes Tuesday | You told the student on a call they could pause | The client approved the change by text | You promised the customer a callback on the phone |
| No yes to changes | Removing a tenant, adding a pet | Refund, extension, switching cohorts | Extra scope, lower price, new deadline | Free callback outside warranty, price change |
| Real address | Tenant's email, not the rent platform's no-reply | Student's email, not the course platform notice | Client contact, not the project-tool alert | Customer's email, not the booking app alert |
| Holding reply + proposed fix | "Can't see the lease in the portal: add them to it, send the invite" | "Can't log in: resend the invite, check the email on file" | "File missing: re-share the folder, confirm access" | "Missed appointment: offer two new slots, flag the tech" |

---

## The seven groups (v1.6)

Every new item, on every channel, goes into exactly one group. When two could apply, the higher row wins. **The groups are the same for every business.** What Claude does INSIDE a group changes with your industry, and that lives in the table after this one.

**Why seven and not a landlord list (v1.6).** Until 1.5 the groups were repairs, tenant requests, lease questions and the like, which only fit a landlord. The owner asked for groups any business can use, built on the way a good executive assistant sorts an inbox (Dan Martell's "Email GPS": review, to respond, waiting on, financials, newsletters).

| # | Group | What belongs here | What Claude does |
|---|----------|-------------------|------------------|
| 1 | **Urgent** | Anything that cannot wait until tomorrow: safety, a property or service down, a legal or government notice, a deadline today, any message that reads as an emergency even if vaguely worded. | Top of the day plan with the one next action. A short "help is being arranged" acknowledgment draft, never one that could delay action, plus who to call from your list. When in doubt between urgent and anything else, choose urgent. |
| 2 | **Needs your review** | Decisions, approvals, anything that would change an agreement, opportunities, contracts, new contacts, and anything only you can answer. | A real question in the day plan, with a PROPOSED answer attached. No draft that commits you. |
| 3 | **Drafted for you** | Routine items Claude can answer from your policies and your records. | The draft, in your Drafts folder (email) or written out in the plan (text, Slack). One line each in the day plan. |
| 4 | **Waiting on** | Things you asked someone for and have not heard back on: emails you sent in the last 14 days that asked a question or requested something and got no reply, and anything someone promised YOU on a recorded call. | One line each, oldest first, with how many days it has been. A follow-up draft only if you ask for one. |
| 5 | **Money** | Bills, receipts, payments received or failed, invoices, quotes, bank and insurance notices, anyone writing about paying. | The amount and the due date, every time. Notices are summarized, not answered. A message about paying late gets a neutral acknowledgment draft that never waives, threatens or negotiates. Approving a quote or paying anything is always yours. |
| 6 | **Read later** | Newsletters and anything worth reading but not today. | Collapsed into one line ("4 to read later"), listed by name if you ask. |
| 7 | **Promo, ready to archive** | Promotions, sales mail, notifications nobody needs. | Collapsed into one line with a count. Claude never archives them (promise 3). See "Auto-archive" below. |

**Matching rules:** match senders against your hub (customers, vendors, team) first, then names and places mentioned in the subject or body, then context. If Claude cannot tell who an item belongs to, it says so and asks, never guesses silently.

### What happens inside a group, by industry

Claude picks the column for the business you named in setup.

| Situation | Landlord | Coach / course creator | Agency / service business | Trades / home services |
|---|---|---|---|---|
| A repair or service problem (group 1 or 3) | A tenant acknowledgment AND a separate draft to your matching vendor asking for availability and a quote. Urgent: no heat, leak, gas, lock failure | An acknowledgment and the fix you have on file (resend the login, re-share the file) | An acknowledgment and the fix (re-share the folder, confirm access) | An acknowledgment and two new slots to offer |
| A new lead (group 2 or 3) | ONLY objective listing facts (rent, deposit, availability, how to view and apply), identical for every prospect; see the Fair Housing guardrail | Program facts and your booking link | Your intro facts and your booking link | Your service area, rates if you publish them, and your booking link |
| An agreement question (group 2) | Lease terms, renewals, adding or removing a tenant, pets | Refunds, pausing, switching cohorts | Extra scope, revisions, new deadlines | Warranty, callbacks, deposits |
| Vendor or supplier mail (group 3 or 5) | Confirm a time, request an itemized quote, ask for an insurance certificate or W-9 | Same | Same | Same |

### Auto-archive: suggested, never done by Claude (v1.6)

Claude never archives anything, ever. But a promo pile you clear by hand every morning is wasted time. So:

1. Claude keeps the promo group for at least two weeks.
2. Once the owner has not pulled anything back out of it for two weeks, Claude asks ONCE in the day plan: "Your promo list has been right for two weeks. Want to set up auto-archive in your email so these never reach your inbox?" with the senders that would be covered.
3. On a yes, Claude walks the owner through setting up the filter in their own email (Gmail filters or Outlook rules), sender by sender, and the owner saves it. **The email provider does the archiving, never this skill**, and the owner can turn it off there any time.
4. On a no, Claude does not ask again unless the owner raises it.

---

## Fair Housing / FCRA guardrail (non-negotiable)

This skill is an inbox assistant, not a screening or decision tool, and it draws a hard line:

- **Claude never makes, recommends, or implies a rental decision.** It will not say or draft anything about whether to accept, reject, renew, not renew, evict, or otherwise select or remove a tenant or applicant. Those decisions are yours, made outside this skill.
- **Claude never evaluates or characterizes applicants or tenants as people.** No scoring, ranking, "good tenant / red flag" commentary, and no inferences about anyone's protected characteristics. Which characteristics are protected is a matter of federal, state and city law, and this skill does not state them: Vera holds that, and your attorney settles it.
- **Prospect drafts contain only objective listing facts** - rent, deposit, availability, viewing logistics, application process - and the identical facts go to every prospect. Claude will not tailor availability or terms per person and will not draft steering language ("this neighborhood might not be a fit").
- **Reports about applicants are out of scope.** Claude does not order, summarize, or act on credit reports, background checks, or eviction histories here, and does not draft the message that communicates a decision resting on one. If such material shows up, the brief flags that it exists and stops. Ask Vera, and your attorney, what that message has to contain.
- **Reasonable-accommodation and discrimination-related messages are handled with care:** if a tenant raises a disability accommodation, service/assistance animal, or a discrimination concern, Claude flags it prominently in the brief, drafts at most a neutral "received, I will respond shortly" acknowledgment, and recommends you respond personally, with your attorney where it matters.
- If you ask for something that crosses these lines, Claude declines that part, explains why in one sentence, and completes the rest of the task.

None of this is legal advice. This skill never states what the law requires: ask Vera, who reads what you have recorded, and confirm anything that matters with your own attorney.

---

## Draft-tone rules

Every draft Claude writes follows these:

1. **Sound like a professional owner, not a bot.** Warm, plain English, short sentences. No corporate filler ("per my last email"), no legalese unless quoting the lease.
2. **First person, your voice.** Drafts are written as you. If you have a preferred sign-off, Claude uses it; otherwise drafts end on the last content line and you add your own signature.
3. **Acknowledge, state the next step, give a time expectation you control.** The skeleton of almost every tenant draft: "Got your message about X. Here's what happens next: Y. You'll hear from me/the plumber by Z." Claude only writes a time expectation you have approved as standard.
4. **Never commit money, terms, or decisions.** No draft agrees to a price, waives a fee, changes a lease term, or promises an outcome unless you already made that decision in the conversation.
5. **One topic per draft.** If a tenant email raises three issues, the draft addresses all three briefly or Claude tells you it split them - but it never leaves an issue silently unanswered.
6. **Empathy where it belongs.** Repairs are disruptions in someone's home. A line of acknowledgment ("sorry you're dealing with this") costs nothing and de-escalates.
7. **No em dashes. No jargon.** And nothing in a draft you would not want read aloud in small-claims court.

---

## The daily brief (output format)

The brief is one message, scannable in under a minute:

```
INBOX BRIEF - Tue Jul 16 - 9 business items since yesterday
Read: email, Slack, people files, 1 meeting recording. Could not read: none.

URGENT (1)
1. [123 Main, Unit 2 - Dana R.] Water heater leaking into closet, sent 7:42am.
   -> Draft ack ready. Suggest calling Reyes Plumbing (your water-heater vendor).

NEEDS YOUR REVIEW (2)
2. [456 Oak - Marcus T.] Asks to add a roommate to the lease.
   -> PROPOSED: your policy file says a new occupant applies like any applicant. Draft ready saying so, with the application link. Approve, edit, or tell me your rule if it differs.
3. [Vendor - ACME Roofing] Quote: $2,850 for the flat-roof patch. Approve, negotiate, or get a second quote?

DRAFTED FOR YOU (2)
4. [123 Main, Unit 1 - Priya S.] Dishwasher not draining -> tenant ack + availability request to Reyes Plumbing.
5. [789 Pine - prospect] Viewing request -> listing-facts reply.

WAITING ON (1)
6. [City permit office] You asked about the inspection date 6 days ago, no reply.

MONEY (2)
7. Rent received: 123 Main Unit 1, $1,650.
8. City water bill, 456 Oak: $118.40 due Aug 1.

(3 to read later. 11 promos, ready to archive.)
```

Rules for the brief: the first line names the channels read (people files included when they exist) and any that could not be read; urgent always first; every item names the property and person; every draft is announced, never silently created; drafts that someone has since answered are listed for you to delete; mail written to a teammate is listed in one line, never drafted; "needs your decision" items ask a clear either/or question AND carry a PROPOSED solution (the likely cause if Claude could check it, the fix, who does it, and the reply that goes out once you approve), because a bare "your call" hands you the thinking; every holding reply ("I'll look into it") is listed with its proposed solution too; money items always show the amount and date. After the brief, you reply in plain English ("approve 1 and 4, hold 5, get a second roof quote") and Claude executes - still creating drafts, never sending.

---

## Running this every morning

The skill shines when it runs every morning without you asking.

**⛔ Do NOT create a scheduled task for this.** Scheduled runs are capped per day by your plan, and
that budget is spent by the one schedule that runs everything. **Add a ROW to your routines table
instead**, and Vera will run this as part of the daily pass. One schedule, many jobs. If you create a
separate schedule for each job you will run out within a week.

**Vera sets this up FOR the owner (v1.6). The owner never adds the row themselves.** The first time
this skill is installed, or on any run where no Daily Routines row names `inbox-handler`, Vera does
all of it in the same session:

- **If their email is not connected yet,** say so in one line, with where to connect it (in Claude:
  Customize, then Connectors). Connecting is the one step only the owner can do. Add the row as soon as
  it is connected.
- **Add the row herself, Paused,** with the settings below already filled in.
- **Run it once, right then,** and show the owner their first brief and the drafts it made, in their
  day plan format.
- **Ask one question:** "Want this running every morning?" On a yes, set the row to Active and say so in
  one line. On a no, leave it Paused and do not ask again unless they raise it.

**What goes in the row:**

1. Frequency daily, and a priority that puts it first among the routines that read messages.
2. Its instructions, exactly this (adjust the mailbox or time window if setup customized them):

   > Use the inbox-handler skill. Read every channel I connected (email, and texts, Slack and meeting recordings if connected) for everything new since the last run (default: the past 24 hours), triage per the skill, create the reply drafts in my Drafts folder, and deliver the daily brief. Do not send anything. If there is at least one URGENT item, put URGENT and who or what it is about in the first line.

3. **It runs BEFORE the day plan is printed (Vera 5.12, step 2c),** so everything it finds lands in the one plan. It uses the task list Vera already read that morning instead of reading your task tool again, and looks up only the specific people it is drafting for in your hub. Run on its own ("check my inbox"), it reads those sources itself.

4. **The brief is NOT a separate thing you read. It folds into Vera's day plan.** This is the part
   people get wrong, and it is worth being blunt about: if the morning produces a day plan AND an
   inbox brief AND a feed report, you have three things to read and you will read one of them. **One
   surface, every morning: the day plan.**

   So the row's output goes into the pass, not around it:
   - **URGENT items go to the top of the day plan**, marked as needing you, with the one next action.
   - **Decision items become items in the day plan** that need you, phrased as the actual question.
   - **Drafts that are ready say so in one line each**, not as a separate list to go and find.
   - **Everything with no action gets one collapsed line**, or nothing at all.

   The full grouped brief in the format below is still how you THINK. It is a working format, and
   it is worth writing out when you are asked for the inbox specifically, or when something is
   complicated enough to need laying out. It is not the daily delivery.
5. The supervised first run above is what proves the connector works and the groups match the owner's mail. Never switch the row on without it.

**Nothing here ever sends.** Replies are drafted and left for you. That holds whether you run it by hand or as part of the daily pass, and there is no setting anywhere that changes it. Nothing this system produces reaches a tenant or a vendor without you reading it first.

**If you are not running routines yet:** say "run my inbox" each morning. The skill behaves identically and you lose nothing but the automation.

**Routine hygiene:**
- One run per day is the sweet spot. Urgent items do not wait for the routine anyway once real-time triage exists (see roadmap below); until then, the daily run plus your phone's normal notifications cover it.
- The routine must run with the SAME connector permissions as an interactive session: read + create-draft, no send.
- If a run finds nothing for the business, the brief is one line ("Nothing today: 6 emails, none business-related"). No news is a valid brief.

---

## What this skill deliberately does NOT do (v1)

- **No sending, on any channel.** Not even "safe" ones. Version 1 has no auto-send and no send-after-timeout.
- **No deleting, except its own untouched out-of-date drafts (rule 8). No archiving.** Promos are listed, never archived. Auto-archive, if the owner wants it, is a filter they save in their own email (see "Auto-archive").
- **No real-time monitoring.** It runs when scheduled or asked. Instant triage of incoming mail (n8n watching the mailbox) and instant pings (Slack/SMS "URGENT: leak at 123 Main") are the planned v2, built on the same categories and guardrails in this file.
- **No tenant screening, no applications processing, no consumer reports** (guardrail above).
- **No payment actions.** It reads money notices; it never pays, charges, or moves money.
- **No calendar writes, no CRM writes.** Logging maintenance items into your property tracker is a natural v2 hook once this skill and your tracker are both in place.
