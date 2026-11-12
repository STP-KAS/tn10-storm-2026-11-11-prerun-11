> **Experimental. We are just trying this.** [Disclaimer](DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> **This is a pre-run. Pre-run 11.** It is not the Wednesday run. It is not the Tuesday run. It is not pre-run 1, 2, 3, 4, 5, 6, 7, 8, 9, or 10. A read does not start a runner.

# tn10-storm-2026-11-11-prerun-11

**Pre-run 11 of the Wednesday neuron.** The neuron stays [tn10-storm-2026-11-11](https://github.com/STP-KAS/tn10-storm-2026-11-11). This repo does not edit that repo, does not write `REVIEW_CLOSED`, and does not set or move a clock for it. [tn10-storm-2026-11-10](https://github.com/STP-KAS/tn10-storm-2026-11-10) (Tuesday) is not edited from here either.

> **Our own testing.** This is our own Kaspa Testnet-10 testing, run on our own machines and nodes. What these pages report is what we observed in this run; it is not a claim of how TN10 or Kaspa behave in general.

**Where this starts.** Pre-runs 1 to 4 failed and are closed. Pre-runs 5 to 10 finished through RETURN and are closed. The index of all of them is the [pre-run 2 README](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-2#pre-runs-in-this-rehearsal); the cumulative findings are in [tn-master](https://github.com/STP-KAS/tn-master). This repo starts from [pre-run 10's locks/LOCKED.md](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-10/blob/ef3ee51/locks/LOCKED.md) at commit ef3ee51, copied here as [locks/LOCKED.md](locks/LOCKED.md), with a pre-run 11 section added at the end.

## What pre-run 10 left open

In [pre-run 10](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-10) the cheap chained covenant tiers were already slow at HOLD-1, 1,013 tx/s: floor (100 sompi/gram) landed 20 hops in the three scored minutes against 373 in pre-run 9's HOLD-1, with a median submit-to-landing of 14.0 s against 1.6 s. Double (200) and triple (300) were slower too; high (1000) was not. Pre-run 10 had no read of the mempool, so it could not say why.

## A first read before this repo was opened

Before opening this repo we read the desk node's mempool, block template and fee estimate (read-only, no load of ours), and walked the desk node's selected chain back to 2026-11-12 00:58Z, reading the transactions each chain block carried (its miner's template). What we observed, on our one node:

- With none of our load running, the mempool held a stream of another sender's chained transactions: 2 inputs, 5 outputs (four small outputs and a change output), fee rate 100 sompi/gram, about 267,000 storage mass each. Storage mass, not compute mass, is their largest mass. Only a few dozen were ready at a time, but their ready mass alone was about 6 to 25 blocks' worth (block limit 500,000 per mass dimension). The node's fee estimate read 100 to 126 sompi/gram at that time.
- None of them matched our run's family transaction ids or our keys' scripts. We did not attribute them to anyone.
- In the chain blocks we read: 0 such transactions in pre-run 9's HOLD-1 minutes (01:13–01:16Z) and 0 at 03:00Z and 05:00Z; about one per chain block from about 06:00Z on, including pre-run 10's HOLD-1 minutes (690 in 909 chain blocks, 87 percent of those blocks' storage mass).

So a candidate explanation for pre-run 10's slow start: the selector of rusty-kaspa v2.1.0 takes every ready transaction while the ready set fits one block, and samples at random weighted by (fee/mass)^3 once it does not. With this stream in the mempool the ready set was over one block before any load of ours, so the node was in its sampling mode, where a 100 sompi/gram hop is no more likely to be drawn than one of the stream's transactions, and a chained hop must win a draw for each link. In pre-run 9's HOLD-1 the stream was not there. This is a candidate; pre-run 11 is built to test it.

## What pre-run 11 tries

The question: why were cheap chained hops slow at 1,013 tx/s in pre-run 10, and where do they actually start to slow?

- **A new instrument.** A read-only probe on the desk's private node, every 20 s: mempool size and composition (ours by cohort and payments, other traffic by fee-rate bucket, ready versus chained, mass in blocks), the desk node's own block template by the same classes, and the node's fee estimate. It runs before the open (started by hand, same code) and through the whole run ([tools/desk/mempool-probe.mjs](tools/desk/mempool-probe.mjs)). Each step file carries a mempool table; `counts/chain/MEMPOOL.md` is the whole timeline.
- **BASE first.** Families only, no payments, eight minutes: the reference for the steps, in the same run, on the same nodes, under whatever other traffic TN10 carries at that time.
- **Low steps.** HOLD-1 400, HOLD-2 700, HOLD-3 1,013 tx/s of payments (scored as before: three clean minutes on submit-OK; at least four minutes per step). The rate stays at 1,013 to the HOLD-4 observation minute.
- **RETURN at 0.** After the HOLD-4 minute the payment offer goes to 0 and the families run alone for ten minutes, to read how fast the mempool drains and the cheap chains recover against BASE. Pre-runs 7 to 10 scored RETURN at 1,013; this one observes it, on purpose.
- **Kept from pre-run 10, so the runs compare.** Floor (families 1–4) 100, double (5–7) 200, triple (8–10) 300 on the desk node, triple-pub (11–13) 300 on the kept public kaspads, high (14–16) 1000. Payments 150. The desk counter is the inclusion figure; Mini is a second read (one hop per transaction); the bot sends in HOLD-4 only on a free third public kaspad, or files a legal `NO SEND`.

All locked lines from earlier pre-runs stay. Nothing is offered over the block space we observed before.

## Machines

| Machine | Go file | First sentence |
|---|---|---|
| Desk | [GO-DESK.md](GO-DESK.md) | DESK. I send and count on pre-run 11. This is not Wednesday. |
| Mini | [GO-MINI.md](GO-MINI.md) | MINI. I count pre-run 11 as the second read. I do not send. This is not Wednesday. |
| Bot | [GO-BOT.md](GO-BOT.md) | GROKBOT. I send payments on the pre-run 11 HOLD-4 only. I do not count. This is not Wednesday. |

The operator does not paste. On 2026-11-12 at 09:02 Brussels time (by voice) and 09:03 (in chat) he left the next congestion probes to TN10 ops' judgment, spending TN10 wallet funds as needed; that is the arm for pre-run 11. The agents start the runners once the gates are facts. [GO.md](GO.md) is the map, [PLAYBOOK.md](PLAYBOOK.md) has the roles and gates, and [plan/PLAN.md](plan/PLAN.md) has the targets and the reasons.

## Gates, in order

No clock. Each gate is a fact read from a node or from origin.

1. Mini's TN10 node is up from its own data, synced, DAA moving.
2. The desk's private TN10 node is up from its own data (PowerShell 7), synced, DAA moving.
3. No other runner or waiter is up. The lane is above the abort line (2,500 coins, 18,000 usable tKAS). The desk's private candidate list is present.
4. `hashes/SIXTEEN.md` is on origin: sixteen rows and an On origin line, from the sixteen-family path.
5. The desk pushes `logs/PRE-RUN-OPEN.md`; Mini pushes `logs/MINI-ARMED.md`.
6. The probe and the desk counter are up. Then the families, BASE, then the payment steps.

## What a decent result is

- `hashes/SIXTEEN.md` on origin before the first family submit.
- BASE observed and HOLD-1 met.
- Every step file carries submit-OK and an inclusion count per minute, hops per minute for all five cohorts, and the probe's mempool table for the same minutes.
- `counts/chain/TIMELINE.md` and `counts/chain/MEMPOOL.md` after the tail.
- An answer to the question, or an honest "not explained".
- A HOLD-4 desk file, a bot file or a legal `NO SEND`, and a Mini file.
- No id, txid, key, address, host, or port in this repo.

A miss stays in this repo. A next attempt is a new repo and starts from this repo's lock file.

**Part of [tn-master](https://github.com/STP-KAS/tn-master).** The rule is [docs/NEURON.md](https://github.com/STP-KAS/tn-master/blob/main/docs/NEURON.md). This pre-run is its own row. It is not row 47.
