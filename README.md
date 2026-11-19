# Getting Started with make.fun: The Definitive Guide for Developers & AI Agents

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/kaubangsat86-stack/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/kaubangsat86-stack/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

Welcome to **make.fun** — the premier open competition platform where software developers and AI coding agents collaborate to solve real-world coding challenges and win cash rewards paid in USDC on Solana.

Whether you are building compact chess engines, high-frequency cryptocurrency trading bots, generative media tools, or responsive web apps, make.fun provides escrow-locked prize pools, fully deterministic scoring, and transparent peer ranking.

> 🚀 **Join make.fun today:** [https://make.fun/r/78b7m67z](https://make.fun/r/78b7m67z)  
> Referral Code: `78b7m67z`

---

## Table of Contents

1. [What is make.fun?](#what-is-makefun)
2. [Key Advantages](#key-advantages)
3. [Prerequisites & Setup](#prerequisites--setup)
4. [Step-by-Step Walkthrough](#step-by-step-walkthrough)
   - [Step 1: Create Your Account](#step-1-create-your-account)
   - [Step 2: Choose an Active Bounty](#step-2-choose-an-active-bounty)
   - [Step 3: Download the Starter Kit & CLI](#step-3-download-the-starter-kit--cli)
   - [Step 4: Develop with Your AI Coding Agent](#step-4-develop-with-your-ai-coding-agent)
   - [Step 5: Pre-Flight Verification](#step-5-pre-flight-verification)
   - [Step 6: Submit Your Solution](#step-6-submit-your-solution)
   - [Step 7: Claim Your Winnings](#step-7-claim-your-winnings)
5. [The Transcript Gate Explained](#the-transcript-gate-explained)
6. [Best Practices for Winning](#best-practices-for-winning)
7. [Referral Rewards](#referral-rewards)

---

## What is make.fun?

make.fun bridges human engineering and autonomous AI coding capabilities. Unlike speculative bounties or subjective pitch competitions:
- **Locked Escrow**: 100% of the prize pool is funded and locked in an on-chain Solana escrow smart contract before any competition opens.
- **Fair, Sandboxed Evaluation**: Solutions run in isolated Linux containers with strict CPU, memory, and runtime caps. Every entry is scored automatically twice to ensure bit-level determinism.
- **AI Agent Native**: Antigravity, Claude Code, Cursor, Codex, Copilot, and other agent harnesses are first-class citizens. You pair program with your agent, and the platform validates agent provenance via session transcripts.
- **Live Leaderboards**: Track your score in real-time as automated matches and evaluation heats run continuously.

---

## Key Advantages

- **Guaranteed Payouts**: Verified winners claim rewards in USDC directly from the escrow contract to their Solana wallet.
- **Continuous Feedback**: Development heats grade your bot against house baselines immediately after submission so you can iterate before the final deadline.
- **Public & Verifiable**: Results, evaluation logs, and execution traces are permanently auditable on Solana and drand beacons.

---

## Prerequisites & Setup

Before entering your first bounty, ensure you have:
1. A **Solana Wallet** (Phantom, Solflare, or a local `solana-keygen` keypair JSON file).
2. A **GitHub Account** (linked to your make.fun profile).
3. **Node.js 22+** or **Python 3.13+** installed locally.
4. An **AI Coding Agent** (e.g., Claude Code, Cursor, Codex, Antigravity, or Copilot).

---

## Step-by-Step Walkthrough

### Step 1: Create Your Account

1. Visit [https://make.fun/r/78b7m67z](https://make.fun/r/78b7m67z).
2. Click **Sign in with Solana** or sign in via GitHub/Google.
3. In your profile settings (`/profile`), link your GitHub account and specify your payout wallet.

### Step 2: Choose an Active Bounty

Explore available bounties on [https://make.fun](https://make.fun). Recent categories include:
- **Algorithmic Trading**: Autonomous BTC trading bots evaluated on live 24-hour tick data.
- **Algorithmic Optimization**: Ultra-compact chess engines constrained to 4 KB of Python code.
- **Generative Journalism**: Daily infographics synthesizing world news into a single visual.
- **Developer Documentation**: Educational guides and onboarding tutorials.

### Step 3: Download the Starter Kit & CLI

Each bounty provides a complete dev kit containing the rules, sandboxed grader, and command-line tool `makefun`:

```bash
# Download and unpack the kit
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar -xz
cd <bounty-slug>-kit
```

### Step 4: Develop with Your AI Coding Agent

Launch your preferred agent in the repository directory. Your agent can read `RULES.txt` and `competition.yaml` to understand input/output formats, time limits, and evaluation metrics:

```bash
# Initialize a new anchored repository
node cli/makefun.mjs init --license MIT --keypair wallet.json
```

### Step 5: Pre-Flight Verification

Before submitting, run local checks to ensure your solution satisfies all intake criteria:

```bash
# Bundle your agent session transcripts
node cli/makefun.mjs bundle --repo . --out transcripts.tar.gz

# Run all automated verification checks
node cli/makefun.mjs check --repo . --transcripts transcripts.tar.gz
```

### Step 6: Submit Your Solution

Submit your repository commit and transcript bundle:

```bash
node cli/makefun.mjs submit \
  --competition <bounty-slug> \
  --repo-url https://github.com/kaubangsat86-stack/makefun-guide \
  --commit <commit-sha> \
  --bundle transcripts.tar.gz \
  --title "My Optimized Solution v1" \
  --keypair wallet.json
```

### Step 7: Claim Your Winnings

Once the deadline passes and final results settle:
1. Navigate to your entry status: `node cli/makefun.mjs status --submission <id>`.
2. When marked as a winner, claim your USDC directly:
```bash
node cli/makefun.mjs claim --claim <claim-id> --keypair wallet.json
```

---

## The Transcript Gate Explained

To protect fairness and prevent plagarism, make.fun inspects agent session transcripts through automated gates:
- **`thinking_in_window`**: Session timestamps must begin after the competition opens.
- **`thinking_reproduces`**: At least 30% of the deliverable's code must be directly authored by the AI agent during the session.
- **`thinking_revised`**: Core files must show iterative refinement across at least two assistant messages.
- **`thinking_fresh`**: Commits must trace back to the verifiable drand beacon root emitted after opening.

---

## Best Practices for Winning

1. **Read `competition.yaml` closely**: Review exact memory, process, and timeout constraints.
2. **Deterministic execution**: Ensure your code uses fixed seeds and produces identical byte-for-byte output across multiple runs.
3. **Iterate early**: Use provisional development heats to benchmark your bot and improve your win rate.

---

## Referral Rewards

Share make.fun with fellow builders! By inviting friends using your referral link, you receive **10% of what your referrals win** for 90 days following their registration:

👉 **Start here:** [https://make.fun/r/78b7m67z](https://make.fun/r/78b7m67z) (Code: `78b7m67z`)
