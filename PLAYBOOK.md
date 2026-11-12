> **Experimental. We are just trying this.** [Disclaimer](DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> **This is the playbook for pre-run 11.** It is not Wednesday. It is not Tuesday. It is not pre-run 1, 2, 3, 4, 5, 6, 7, 8, 9, or 10. It does not start a machine and it does not arm one.

# Playbook

Who does what, and the gates before each machine may start. The plan is [plan/PLAN.md](plan/PLAN.md), the locks are [locks/LOCKED.md](locks/LOCKED.md), and the go files are the three GO pages. This page does not override them.

## Oversight

TN10 ops oversees this rehearsal end to end: Mini, the desk (Build), and the bot. TN10 only. Never mainnet. Do not edit the Tuesday repo, the Wednesday repo, or pre-run 1's to 10's go files. Do not write `REVIEW_CLOSED`.

For pre-run 11 the operator does not paste. On 2026-11-12 at 09:02 Brussels time (by voice) and 09:03 (in chat) he left the next congestion probes to TN10 ops' judgment, spending TN10 wallet funds as needed. That is the arm. The agents start their runners once the gates are facts.

## Start gates

1. **Mini node synced.** Existing TN10 kaspad, existing data, no wipe. `isSynced` true, DAA moving.
2. **Desk node synced.** Existing private TN10 kaspad, existing data, loopback only, started with `pwsh`. No wipe. Synced, DAA moving.
3. **No other runner.** No earlier runner, waiter, or counter on any machine. Lane above the abort line. The desk's private candidate list is present and not empty (`HELD candidates-missing` otherwise).
4. **Hashes.** `hashes/SIXTEEN.md` with sixteen rows and an On origin line, from [tools/sixteen](tools/sixteen/README.md).
5. **Open.** The desk pushes `logs/PRE-RUN-OPEN.md`. Mini then pushes `logs/MINI-ARMED.md`.
6. **Counter, families, senders.** The desk runner starts the counter on its private node and waits for its start line (`HELD counter-down` otherwise). Then the genesis from the bundle that wrote `hashes/SIXTEEN.md`, the families, and the payment steps.

## Who does what

| Who | Role | What not to do |
|---|---|---|
| **Desk (Build)** | Sends the sixteen families (five cohorts: four fees, and one fee on two paths) and the payment offers. Its private TN10 node counts what the chain accepted (lock line (iv)). Publishes `hashes/SIXTEEN.md`, `logs/PRE-RUN-OPEN.md`, `counts/desk/` per step, `counts/chain/TIMELINE.md` after the tail, and `logs/METHOD.md`. | Do not stop or wipe the desk node. No Windows PowerShell 5.1, no `KaspaPublicNode`, no devnet. No 8- or 32-family publisher. No second runner. Never restart the runner mid-run. |
| **Mini** | Second chain read on its own node. Does not send, mine, or hold a key. Publishes `logs/MINI-ARMED.md`, then `counts/mini/` when the matching desk file is on origin. Each head is Mini's own read: `READ`, `PARTIAL`, or `NOT READ`. | Do not wipe. Do not repeat the desk's head as Mini's. |
| **Bot (TN10 ops)** | Sends payments in the HOLD-4 minute only, on a synced public kaspad that is not one the desk kept, or publishes a legal `NO SEND`. | Do not send on HOLD-1, HOLD-2, HOLD-3, or RETURN. One waiter. No local node. |

## Status when this repo was opened

Not a gate. A status line, so nobody guesses. Read on 2026-11-12 between 08:05Z and 08:25Z. This is our own TN10 testing; status lines are what we read on our own machines.

- Mini: existing TN10 kaspad 2.1.0, no wipe; its sync is read and logged by its runner before `MINI-ARMED`. Pre-run 10's Mini runner ended at 2026-11-12T08:03:49Z.
- Desk: existing private TN10 kaspad 2.1.0 up with `pwsh` since 2026-11-11, no wipe, synced, DAA moving. It is not stopped for this pre-run. No pre-run 10 runner or child is running.
- Box: no local TN10 node. No bot waiter running.
- Lane and pile: keys 1–15 got a fresh genesis coin from the lane at 2026-11-12T08:18:37Z (15 transactions, none rejected; amounts and transaction ids are in the operator's private notes, not here). After that, status.mjs read the lane at 5,511 coins and 239,371 usable tKAS, above the abort line, and the payment key at 8,400 coins.
- Mempool before the open (read-only, desk node, no load of ours): another sender's chained stream at 100 sompi/gram with about 267,000 storage mass per transaction was in the mempool, its ready mass several blocks' worth; the node's fee estimate read 100 to 126. See the [README](README.md#a-first-read-before-this-repo-was-opened). The pre-open probe file is summarised in `counts/chain/MEMPOOL.md` after the run.
- Known risks, not fixed mid-run:
  - The other sender's stream may stop or change during the run. The probe records it either way; the steps are read against the probe's minutes.
  - Triple-pub's funding coins are still read from the desk node; a public node may briefly refuse a coin it has not yet seen spent. Such rejects are logged.
  - Each family is a chain of hops, so a hop waits for its parent whatever its fee (see [plan/PLAN.md](plan/PLAN.md#selection-rule)).
  - The probe reads the desk node's mempool and template, not a miner's; what a miner's template took is inferred from the chain.
  - `getMempoolEntries` is skipped for a read when the mempool is over 40,000 entries (that read keeps only the size). No step is expected to build such a backlog.
  - Only two unique public kaspads answered in every check so far, and the desk keeps both, so the bot is expected to file `NO SEND no-free-node`.

## Offline rehearsal, recorded before `PRE-RUN-OPEN`

Rehearsal A (p11-a), 2026-11-12 08:23:00Z to 08:23:12Z (desk, Brussels 09:23). It stopped at genesis (`HELD at genesis`, runner exit 3): I had copied the real `submit-sixteen.mjs` into the rehearsal's `six/` instead of the stand-in one. That script threw while building the transactions, before its submit line, so nothing was submitted to any node. Kept here as a record of the mistake, not hidden.

Rehearsal B (p11-b), 2026-11-12 08:24:31Z to 08:55:01Z (desk, Brussels 09:24 to 09:55), with pre-run 10's stand-in `submit-sixteen.mjs`. The real pre-run 11 desk runner, counter, payment sender, rehearsal family sender and the new read-only mempool probe ran against pre-run 9's stand-in node on the desk, with a local bare origin. Short times: BASE 3 minutes, RETURN 3 minutes, 2-minute tail.

- BASE published as `OBSERVATION` (offer 0, families only). HOLD-1 at 400 `MET` (24,007 / 23,976 / 24,076 / 23,969 submit-OK), HOLD-2 at 700 `MET` (42,175 / 41,938 / 41,847 in the last three minutes), HOLD-3 at 1,013 `MET` (60,917 / 60,758 / 60,710 / 60,728). HOLD-4 pinned 08:48Z and ran at 1,013 (`OBSERVATION`, 60,778). The rate went to 0 at 08:49:12Z and RETURN published as `OBSERVATION` (0 submit-OK, families only).
- The runner published `counts/chain/TIMELINE.md`, the new `counts/chain/MEMPOOL.md` and `logs/METHOD.md`, and exited 0. Each step file carried its "Mempool and template, desk node (probe)" table. No rehearsal process was left running.
- The probe in the rehearsal read the real desk private TN10 node (read-only: getInfo, getFeeEstimate, getMempoolEntries, getBlockTemplate, never submitted), so its rows show the other sender's heavy stream (about 266,600 storage mass per transaction, fee rate 100, one in each template) and no families of ours (they went to the stand-in).
- What the rehearsal did not exercise: the public-mempool columns stay empty there (the stand-in's node urls are not wss, so the probe skips them; the table then shows one empty trailing column). No `REORG` line. The stand-in lands hops by its own rule, so its cohort numbers are not a network result.

## Status after the live run

Read on 2026-11-12 between 09:46Z and 09:58Z. Not a gate.

- Desk: the runner (started 09:00:00Z) ran BASE to RETURN without a repair or a restart and ended at 09:46:41Z after publishing `counts/chain/TIMELINE.md`, `counts/chain/MEMPOOL.md` and `logs/METHOD.md`. Its probe (`PROBE_STOP` 09:46:32Z), counter (`COUNTER_STOP` 09:46:32Z), family sender, coordinator, broker (`builder exit 0`) and six payment senders exited with it; no runner process was left on the desk. The pre-open probe had been stopped at 08:58:22Z and the history scan had finished before the open. The private TN10 kaspad was not stopped and is still up, synced. No devnet, `KaspaPublicNode` or miner was started; the faucet process was not touched.
- Mini: the runner (MINI-ARMED 08:59:21Z) published a second read for every step and ended at 09:56:38Z after its 15-minute tail (`RUNNER end`); no runner process was left on Mini. Removals after a minute had closed: 0. Its TN10 kaspad was not wiped or restarted and is still up.
- Bot: the waiter read HOLD-3 on origin at 09:25:27Z, pinned 09:29Z, found no free node at 09:28:31Z, and published `NO SEND no-free-node` (a161644, on origin 09:30:05Z). The waiter and its finish step exited; no bot process is left. Nothing was sent by the bot.
- Lane and pile after the run: lane 5,510 coins, 215,651 usable tKAS, above the abort line, read by status.mjs at about 09:48Z (5,511 coins and 239,371 usable tKAS after the re-funding at 08:22Z); payment key 8,400 coins (185,828.62 tKAS at the end snapshots). Keys 1–15 have no genesis coin left; a next repo funds them again.
- No `FAILED` file was written. Results: [logs/LESSONS.md](logs/LESSONS.md), [logs/METHOD.md](logs/METHOD.md), [counts/chain/MEMPOOL.md](counts/chain/MEMPOOL.md), and the pre-run 11 block in [locks/LOCKED.md](locks/LOCKED.md).

## When something breaks

Append a worked fix to [locks/LOCKED.md](locks/LOCKED.md) in the form that page shows, and a repair line to `logs/FIXES.md`. If the run dies before RETURN, write `logs/FAILED.md`, stop every runner, waiter, and counter, and do not resume. The next attempt is a new repo that starts from this repo's lock file.
