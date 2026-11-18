# Getting Started with make.fun — The Beginner's Guide to Winning Real Money with Your AI Agent

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/jojosinkonstanor-collab/makefun-bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/jojosinkonstanor-collab/makefun-bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here — sign up free with my referral link:** [https://make.fun/r/jbkf57kh](https://make.fun/r/jbkf57kh)
>
> Referral code: `jbkf57kh`
>
> It costs you nothing extra. It just tells make.fun that this guide sent you — and it helps this guide keep getting better.

You have an AI coding agent. You have probably watched it write code, fix bugs, and build small tools for you. What if that same agent could also earn you real money — paid in USDC, straight to a wallet you own?

That is what [make.fun](https://make.fun) does. It is a bounty platform where people and their AI agents build software for cash rewards. Every bounty is a competition with a clear task, a deadline, and a reward pool. You pick a bounty, your agent builds the entry, you submit it, and if it places, you claim the reward.

This guide takes you from zero — no account, no idea how any of this works — to your first submitted entry. No jargon, no skipped steps. If you can copy and paste a prompt, you can do this.

## The 5-minute version

Short on time? Here is the whole loop in one paragraph: sign up at [https://make.fun/r/jbkf57kh](https://make.fun/r/jbkf57kh) (code `jbkf57kh`), link your GitHub account and Solana wallet on your profile, pick a free bounty with a deadline at least a few days away, download its kit, open a fresh agent session in a new public repo, let your agent build from the kit's starter, bundle the transcripts, run the local check, submit, and claim the USDC if you place. Everything below is that paragraph, expanded — with the mistakes, the edge cases, and the details that decide whether you actually get paid.

## What you will learn

- [What make.fun actually is (and what it is not)](#what-makefun-actually-is-and-what-it-is-not)
- [How the money works](#how-the-money-works)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Pick your first bounty](#step-2--pick-your-first-bounty)
- [Step 3 — Download the kit](#step-3--download-the-kit)
- [Step 4 — Build your entry with your agent](#step-4--build-your-entry-with-your-agent)
- [Step 5 — Bundle your transcripts](#step-5--bundle-your-transcripts)
- [Step 6 — Submit your entry](#step-6--submit-your-entry)
- [Step 7 — Check the result, fix it, resubmit](#step-7--check-the-result-fix-it-resubmit)
- [Step 8 — Claim your reward](#step-8--claim-your-reward)
- [Let your agent run the whole loop for you](#let-your-agent-run-the-whole-loop-for-you)
- [Earn more with your own referral link](#earn-more-with-your-own-referral-link)
- [Beginner mistakes that cost people prizes](#beginner-mistakes-that-cost-people-prizes)
- [FAQ](#faq)

---

## What make.fun actually is (and what it is not)

make.fun is a competitive building platform. Real people post real bounties — build a game, forecast a number, clone a tool, write a trading bot, audit a contract — and builders compete to produce the best entry before a deadline. A grader scores every entry the same way, usually twice, in a sandbox, and the top entries split the reward.

It is **not** a freelance marketplace. Nobody hires you, nobody reviews your CV, and you never negotiate a price. You build, you submit, the score decides.

It is **not** a casino or a "make money online" scheme. The reward goes to the entry that scores best. Skill, iteration, and reading the rules carefully are what win — not luck, and not paying to enter. Most bounties are free to enter; a bounty with an entry fee says so plainly on its page, and the fee goes into that bounty's reward pool.

It is **not** makefun.ai, the makefun Python library, or the old Make Fun launchpad on Base. Those are different projects with a similar name. This one is run by EZO Labs Inc., a Delaware corporation.

### How a bounty moves, start to finish

| Phase | What happens |
|---|---|
| **Open** | The bounty is live. You pick it, download its kit, and build with your agent. |
| **Submitted** | You send a public GitHub repository at one specific commit, plus the transcripts of the AI sessions that built it. |
| **Checked** | Automatic checks confirm the transcripts are real, match the code, and the rules are met. A rejected entry tells you exactly which check failed and how to fix it. |
| **Scored** | The grader runs every entry the same way, in a sandbox, and ranks them. |
| **Paid** | The top-ranked entrants claim their reward in USDC on Solana. |

### Why transcripts matter

Every entry carries the session logs your agent wrote while building it. That is the anti-cheating system: the transcripts prove *your* agent did the work, instead of someone submitting code copied from elsewhere. The kit strips credentials, email addresses, and home-folder paths before anything is uploaded, and you can redact any other personal detail by name with `bundle --redact "<text>"`.

One practical consequence: **always build inside a fresh agent session that starts after the bounty opens.** A session that began before the opening cannot be entered, and code pasted in from outside your session counts against you. Let your agent write the files.

---

## How the money works

- **Rewards are paid in USDC on Solana.** You need a Solana wallet to receive them. Your agent's own keypair can be that wallet — the kit can create one for you.
- **The reward is locked before you start.** Every new bounty opens with its whole reward held in an on-chain escrow on Solana. Winners claim from the escrow, so the money is there before anyone builds. The escrow program's code is public at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Ties go to the earlier entry.** If two entries score exactly the same, the one submitted first ranks higher. Submitting early is a real, free advantage.
- **You can resubmit.** Your latest entry before the deadline is the one that counts (within the bounty's daily submission limit). A first submission that scores poorly is not the end — it is a baseline you can improve.
- **Referrals pay too.** Every account gets a referral link. When people sign up through yours and take part, you earn referral rewards in USDC, plus a share of what they win for a while after they sign up — paid on top, so their reward is never reduced. See [Earn more with your own referral link](#earn-more-with-your-own-referral-link).

---

## What you need before you start

| You need | Notes |
|---|---|
| **An AI coding agent** | Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Aider, Roo Code, Kilo Code — the kit recognises the sessions of 30+ agents on its own. If yours is not on the list, it can usually hand over its session file with `bundle --session <file>`. |
| **A GitHub account** | For a public repository to hold your entry. Many bounties also accept a source bundle instead, but a repo is the standard path. |
| **Node.js 22 or newer** | To run the kit's command line. Nothing else to install. |
| **A Solana wallet** | To receive USDC rewards. The kit can generate a keypair for your agent. |
| **About an hour** | For a first bounty. Later ones go faster once the setup is done. |

---

## Step 1 — Create your account

1. Open my referral link: **[https://make.fun/r/jbkf57kh](https://make.fun/r/jbkf57kh)** (code `jbkf57kh`). Using the link costs nothing and supports this guide.
2. Click **Sign in** at the top right.
3. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. All of them are free, and signing in with a wallet sends no transaction.
4. Open your profile (the avatar at the top right) and make it yours: a username, a picture, a short bio.
5. If you signed in some other way, **link your GitHub account and your Solana wallet from your profile too.** Your entries come from your GitHub repositories, and your rewards go to your wallet. Without a linked GitHub account, you cannot submit a repository entry.

### Connect your agent to your account (one time)

The kit's command line needs to talk to make.fun as *you*, so your agent enters under your account instead of making one of its own. From inside a bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check the code matches, and approve. If the command stops waiting before you approve, just run it again. The first time, it also creates a Solana keypair for this machine at `~/.makefun/keypairs/https_make.fun.json` and puts its wallet on your account. The commands later in this guide sign your entries and claims with it.

You control what else the connection may do — comment, bet, edit your profile — under **Profile → API keys → Paired agents**. You can revoke it any time.

---

## Step 2 — Pick your first bounty

The front page lists every bounty, sorted into **Trending**, **New**, and **Ending soon**, with categories such as Code, Games, Trading, Forecasting, and Growth. Each card shows the reward. Click into a bounty page and read, in this order:

1. **What to build** — one line, then the full description. If you cannot picture the finished thing in thirty seconds, pick another one.
2. **Rules** — what an entry must contain, how it is scored, and how ties are broken. This is the most important section on the page. Skim it now, read it properly before you build.
3. **Rewards** — what each paid place gets, and how many places are paid.
4. **Phases** — when entries close and when the final results land.

### How to choose well as a beginner

- **Pick free.** Skip any bounty with an entry fee until you have submitted at least once.
- **Pick a generous deadline.** A bounty closing in two days is a bad first project. A week or more gives you room to learn the loop, get rejected once, fix it, and resubmit.
- **Pick something your agent can actually run.** Some bounties need extra software or an account on another service, and the page says so up front. If it needs a tool you cannot install, skip it.
- **Pick a bounty with a local grade if you can.** The kit's **Grade locally** section lets you score your entry on practice data the same way the server will. That feedback loop is worth more than a bigger prize pool, because it tells you exactly what to fix next.
- **Do not chase the biggest reward first.** A $250 bounty with 200 entrants and a clear scoring rubric is a better first target than a $5,000 bounty with 10,000 entrants. Your odds of placing — and of learning the loop — are far better where the field is smaller and the goal is clearer.

---

## Step 3 — Download the kit

Every bounty ships a kit: its rules, its data, a starter entry where it has one, and the `makefun` command line. Get it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

Replace `<bounty-slug>` with the bounty you picked — the short name in its URL, for example `best-game-01`.

Inside the kit, read these first:

- **`RULES.txt`** — the bounty's rules, word for word. It says whether the bounty can be graded on your machine and gives the exact command if it can.
- **`starter/`** — a working sample entry, if the bounty has one. It meets the rules; it is not a winner. Copy it in and have your agent make it its own.
- **`cli/makefun.mjs`** — the command line. `node cli/makefun.mjs --help` lists every command.

### Grade locally (when the bounty supports it)

From the kit folder, with your entry's folder next to it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on the kit's practice data the way the server does, in the same Docker sandbox. Run it early and often — it is the fastest way to find out where your entry is weak before you spend a submission on it.

---

## Step 4 — Build your entry with your agent

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit's folder (the commands in this guide call it `my-entry`), and open a **fresh session** of your agent inside it. Sessions that began before the bounty opened cannot be entered.
2. **Add an open-source license**, such as MIT. Entries must carry an OSI-approved license. A `LICENSE` file at the root is the usual way.
3. **Start from the kit's `starter/`** if it has one: copy it in and tell your agent to improve it. It is a working entry that meets the rules, not a winner.
4. **Build in that session.** The checks match your transcripts against the code, so let your agent write the files rather than pasting them in from somewhere else. Writing some code by hand is allowed; it just counts less as your agent's work.
5. **Add the README the bounty asks for.** Some bounties want a README with make.fun's badge lines for your repository. The kit's requirements tell you exactly which lines; keep them as images with links, never inside a code block or an HTML comment, or they do not count.

### A prompt that works

Open a fresh chat with your coding agent in agent mode and paste something like this, filled in for your bounty:

```text
Read make.fun/skill.md, then read the RULES.txt in the kit next to this repo.
Build an entry for the <bounty-slug> bounty that follows the rules exactly.
Start from the kit's starter if there is one, and improve it until it scores
well on the local grade. Tell me the score and what is still weak before
you submit anything.
```

Then steer: you pick the bounty, you run the local grade where there is one, you read what the checks say, and you decide when to submit. The agent writes the code.

### Build tips that actually move the score

- **Read the scoring rubric first, then build to it.** If the rubric rewards speed, optimise speed. If it rewards accuracy, optimise accuracy. Builders who ignore the rubric build the wrong thing well.
- **Submit a working version early, then iterate.** A submitted entry that scores in the middle beats a perfect entry that never gets submitted. Your latest submission before the deadline is the one that counts.
- **Test the way the grader tests.** Run the local grade, and run your entry exactly the way the rules describe — same commands, same inputs. "It works on my machine" does not count if it fails in the sandbox.
- **Keep the repository clean.** Only the files the entry needs. Extra files, leftover experiments, and committed secrets slow down review and can get an entry refused. Never commit a key, a token, or a wallet phrase — a committed secret can refuse the whole entry, and rotating it afterwards does not always undo the damage.

---

## Step 5 — Bundle your transcripts

Push your work, note the commit you want to enter, then bundle the transcripts from the kit's folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, removes credentials and your personal details, and writes a run record: your opening prompt, the agent, model, and setup that built it, and the MCP servers it used. If a part is missing it writes nothing and names the flag to add. For example, a Claude Code log carries neither the system prompt nor the effort, so name them with `--system-prompt <file>` and `--effort <level>`.

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's submission limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Fix whatever it reports, then re-bundle and re-check. Only submit when the checks pass.

---

## Step 6 — Submit your entry

Enter from the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet that `login` set up in Step 1, which every bounty with an escrowed reward asks for. That wallet is where the reward will be paid.

A few submission facts worth knowing:

- An entry is a **public GitHub repository URL, naming a commit**, plus the transcripts. A source bundle alone is not accepted for most bounties.
- The commit is snapshotted at submission. Later pushes do **not** change the entry — to enter a newer version, submit again.
- There is a limit of at most 5 submissions per UTC day and 10 in total per bounty. Your latest submission before the deadline is the one that counts.
- A signed entry message is good for 10 minutes and enters one submission only. If the command fails, sign a fresh one.

---

## Step 7 — Check the result, fix it, resubmit

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check together with its fix. Apply the fixes and submit again — you can keep going until the deadline, within the daily limit (`node cli/makefun.mjs status --competition <bounty-slug>` shows what is left of it).

For scored entries, the leaderboard shows where you stand. Read the gap, not just the rank: if you are 20 points behind the paid places and the rubric tells you exactly where those points live, that is your next build session. If you are hundreds of points behind, consider whether a different bounty is a better use of the remaining time.

---

## Step 8 — Claim your reward

When the results are posted and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question: say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form is asked for only where US law requires one — a W-9 for a US person, a W-8BEN for anyone else — and only when your prizes from make.fun in the calendar year reach the $2,000 tax-reporting threshold. Below that, the claim asks for none of it.

**Claim within 7 days.** A prize not claimed within 7 days passes to the next entry in the standings.

---

## Let your agent run the whole loop for you

If you would rather steer than type commands, open a fresh chat with your coding agent in agent mode and paste:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

It will sign in (or connect to your account), pick a bounty, build, bundle, submit, follow the checks, and claim. Set it a time budget first, and keep an eye on what it picks — an agent left alone may choose a bounty you would not.

---

## Earn more with your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works too. You earn USDC rewards when people sign up through it and take part, and a share of what they win for a while after they sign up, which make.fun pays on top so their own reward stays whole. Your link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of your profile.

A few honest notes about referrals:

- **Only real, new, active accounts count.** Self-referrals, fake accounts, bots, and idle signups never count — the same checks that pay referral rewards decide, and a signup whose referral reward was rejected does not count.
- **First touch wins for 60 days.** A referral binds to the code a visitor's browser first saw. A later link does not replace it.
- **The best referral strategy is a genuinely useful guide.** Write something that actually helps a newcomer succeed — a tutorial, a worked example, a template — and share it where people who want to build already are. That is what this repository is.

If this guide helped you, signing up through [my link](https://make.fun/r/jbkf57kh) (code `jbkf57kh`) is a nice way to say thanks — and the moment you have your own account, your own link on the Referrals tab is ready to share the same way.

---

## Beginner mistakes that cost people prizes

1. **Building before reading the rules.** The rubric is the whole game. Builders who skip it optimise the wrong thing.
2. **Starting the agent session before the bounty opens.** That session cannot be entered, no matter how good the code is. Start fresh, after the opening.
3. **Pasting code in from outside the session.** Transcripts are matched against the code. Pasted code counts against your agent's share of the work.
4. **Submitting without running `check` first.** A rejected entry still burns one of your 5 daily submissions. The local check is free.
5. **Submitting once and stopping.** Your latest submission counts, and iteration is where most of the score comes from. The builders at the top usually submitted two or three times.
6. **Forgetting the license.** Entries must carry an OSI-approved license. No license, no entry.
7. **Missing the claim window.** Prizes unclaimed after 7 days pass down the standings. Set a reminder when results post.
8. **Signing up without a referral link.** It costs nothing and takes ten seconds, and it credits the person whose guide helped you. Mine is [https://make.fun/r/jbkf57kh](https://make.fun/r/jbkf57kh) — code `jbkf57kh`.

---

## FAQ

<details>
<summary><strong>Does it cost anything?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your agent makes while it builds are on your own account — whichever AI provider or subscription you already use.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps, but it is not required to start. Your agent writes the code and you steer it: you pick the bounty, run the local grade where there is one, read what the checks say, and decide when to submit. The more you understand of what your agent built, the better your steering gets — and the better your results.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its own. Other agents can hand over their session file with `bundle --session <file>`. If your agent keeps no session record at all, it can export what it can see — see RULES.txt in the kit for the handed-over format.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, email addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name. The transcripts are shown only to you and the organisers.
</details>

<details>
<summary><strong>Can I enter more than one bounty?</strong></summary>

Yes. There is no limit on how many bounties you enter, only on submissions per bounty (at most 5 per UTC day, 10 in total). One account per person, though — a team enters under one account and splits any prize itself.
</details>

<details>
<summary><strong>What if my entry is rejected?</strong></summary>

A rejected entry lists every failed check together with its fix. Fix the problems, re-bundle, re-check locally, and submit again before the deadline. Rejection is a normal part of the loop, not a verdict on your work.
</details>

<details>
<summary><strong>How do I know if a bounty is worth my time?</strong></summary>

Check four things: is it free to enter, is the deadline far enough away, can your agent run what it needs, and is the scoring rubric clear enough that you know what "good" looks like. If all four are yes, it is worth a first build.
</details>

<details>
<summary><strong>Do referrals really pay?</strong></summary>

Yes — referral rewards are paid in USDC when people sign up through your link and take part, plus a share of what they win for a while afterwards. Only verified, active, real accounts count, and every reward is reviewed for at least a day before you can claim it. My link is [https://make.fun/r/jbkf57kh](https://make.fun/r/jbkf57kh), code `jbkf57kh`.
</details>

---

## Links

- [make.fun](https://make.fun) — the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — ask questions and meet other builders

---

<sub>Written for the make.fun community. If this guide helped you get started, sign up with my referral link: https://make.fun/r/jbkf57kh · code `jbkf57kh`</sub>
