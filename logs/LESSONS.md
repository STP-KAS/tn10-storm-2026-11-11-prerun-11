> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value. Pre-run 11.
>
> **Our own testing.** This is our own Kaspa Testnet-10 testing, run on our own machines and nodes. What this page reports is what we observed in this run; it is not a claim of how TN10 or Kaspa behave in general.

# Lessons, pre-run 11

> Written by the operator after RETURN closed and the counter's tail was read. [METHOD.md](METHOD.md) is the desk runner's own summary; its last section, the reading against the selection rule, was added by the operator afterwards. Included counts are the desk counter's read of the desk's private TN10 node ([counts/chain/TIMELINE.md](../counts/chain/TIMELINE.md)), checked against a kept public kaspad every 10 s. Mempool, ready-set and template figures are the read-only probe on the same node ([counts/chain/MEMPOOL.md](../counts/chain/MEMPOOL.md)), every 20 s, one median per minute. They are one node's view, not a network-wide figure. The probe's template is the desk node's own `getBlockTemplate`, never submitted: it is what that node would build, not a miner's template.

## The question

Why were cheap chained covenant hops slow at 1,013 tx/s in pre-run 10, and where do they actually start to slow? Before this repo was opened we had a candidate ([README](../README.md#a-first-read-before-this-repo-was-opened)): another sender's chained stream of heavy transactions (about 267,000 storage mass each, fee rate exactly 100 sompi/gram, the same as our floor cohort) had been in the desk node's mempool and in the chain since about 06:00Z. Pre-run 11 added a no-load BASE, low payment steps (400 / 700 / 1,013), a RETURN at 0, and a mempool probe.

## What happened

Every step closed on its first evaluated minutes, with no repair. The runner was not restarted, nothing was killed, and no `FAILED` file was written. Every desk count file, the timeline, the mempool timeline, the method file and the bot's file reached origin on the first try. The desk node was not stopped.

MET below means desk submit-OK, as scored. Inclusion is reported next to it, not scored.

| Step | Offer, tx/s | Desk head | Submit-OK per scored minute | Our payments included, same minutes | Payments included within 10 percent | Desk file on origin (UTC), commit |
|---|---:|---|---|---|---|---|
| BASE | 0 (families only) | OBSERVATION | 0 × 8 | 0 × 8 | 8 of 8 (0 against 0) | 09:10:22Z, 5ec9f3d |
| HOLD-1 | 400 | MET | 23,934 / 23,988 / 24,035 / 23,989 | 24,354 / 23,692 / 23,951 / 24,223 | 4 of 4 | 09:15:22Z, 6cc3b34 |
| HOLD-2 | 700 | MET | 42,182 / 41,851 / 41,900 / 41,934 | 41,943 / 41,852 / 41,834 / 41,889 | 4 of 4 | 09:20:22Z, 3f3344d |
| HOLD-3 | 1,013 | MET | 61,120 / 60,967 / 60,655 / 60,656 | 60,650 / 60,943 / 60,320 / 61,492 | 4 of 4 | 09:25:21Z, 51ff6b0 |
| HOLD-4 | 1,013 | OBSERVATION | 61,029 (pinned minute 09:29Z) | 60,659 | 1 of 1 | 09:30:22Z, 5c88236 |
| RETURN | 0 (families only) | OBSERVATION | 0 × 10 | 0 × 10 | 10 of 10 (0 against 0) | 09:41:22Z, 22463d7 |

The bot filed `NO SEND no-free-node` for HOLD-4 (a161644, on origin 09:30:05Z): in its pass at 09:28:30Z every answering endpoint was one of the desk's two kept kaspads. The rate went to 0 at 09:30:12Z. After the 5-minute tail the runner published the timeline (d25fc15, 09:46:33Z), the mempool timeline (327de60, 09:46:36Z) and its method file (44996c0, 09:46:39Z) and ended at 09:46:41Z. Mini published a second read for every step (RETURN e67e8fb, 09:41:33Z).

Whole run, as read by the end of the tail: 923,812 payment submit-OKs, all of them included. Our own landed load peaked at about 64,000–65,000 non-coinbase a minute in HOLD-3 and HOLD-4, about half the 110,000–132,000 band we had observed when we pushed in pre-runs 8 and 9. Landed other traffic on this node was about 3,000–3,650 a minute in every minute. Family hops included over the run: floor 2,571, double 3,260, triple 4,326, triple-pub 6,084, high 6,142.

## Hops per cohort, per step

Sums of the scored minutes, desk counter, and the per-minute mean in brackets. Floor has four families, the other cohorts three.

| Step (scored minutes) | Floor 100 (4 fam.) | Double 200 | Triple 300, desk | Triple-pub 300, public | High 1000 |
|---|---:|---:|---:|---:|---:|
| BASE, 0 tx/s (8) | 1,167 (146) | 1,069 (134) | 1,172 (147) | 1,828 (229) | 1,299 (162) |
| HOLD-1, 400 (4) | 323 (81) | 380 (95) | 465 (116) | 669 (167) | 596 (149) |
| HOLD-2, 700 (4) | 345 (86) | 328 (82) | 402 (101) | 529 (132) | 574 (144) |
| HOLD-3, 1,013 (4) | 12 (3) | 77 (19) | 192 (48) | 220 (55) | 543 (136) |
| HOLD-4, 1,013 (1) | 3 | 17 | 42 | 44 | 135 |
| RETURN, 0 tx/s (10) | 231 (23) | 798 (80) | 1,215 (122) | 1,664 (166) | 1,607 (161) |

Median submit-to-landing per hop, seconds (p95 in brackets), from the step files:

| Step | Floor | Double | Triple | Triple-pub | High |
|---|---|---|---|---|---|
| BASE | 1.2 (2.9) | 1.1 (1.9) | 1.0 (1.6) | 0.6 (1.2) | 0.9 (1.4) |
| HOLD-1 | 1.4 (9.4) | 1.5 (3.6) | 1.3 (2.2) | 0.8 (1.8) | 1.0 (1.5) |
| HOLD-2 | 1.5 (2.9), 342 of 345 | 1.4 (5.4) | 1.3 (3.5) | 0.9 (2.8) | 1.1 (1.6) |
| HOLD-3 | 71.3 (123.2), 9 of 12 | 6.7 (22.8) | 2.7 (8.7) | 2.4 (8.3) | 1.1 (1.7) |
| HOLD-4 | 30.3, 1 of 3 | 8.3 (24.8) | 3.4 (10.3) | 3.0 (8.4) | 1.2 (1.7) |
| RETURN | 7.6 (27.9), 230 of 231 | 1.8 (4.4) | 1.2 (2.2) | 0.8 (2.0) | 0.9 (1.4) |

## Every minute: hops, offer and the probe

Hops: desk counter, by accepting chain block time. Probe columns: medians of that minute's three samples on the desk node. "Ready mass" is the mass of mempool transactions with no parent in the mempool, in blocks of 500,000. "Other at 100" is mempool entries not in our sender logs whose fee rate is 100 sompi/gram; in this run those were, as far as we read them, the outside heavy stream (mean mass about 266,600 in every minute where it was present). Families stopped at 09:41:24Z, so 09:41 is a partial family minute, and 09:42 on has no family hops.

| Minute (UTC) | Step | Pay submit-OK | Floor 100 | Double 200 | Triple 300 | Triple-pub 300 | High 1000 | Mempool | Ready mass, blocks | Other at 100, in mempool | Other ready | Our payments in mempool |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 09:00 | families | - | 1 | 5 | 6 | 8 | 9 | 10 | 4.81 | 9 | 10 | 0 |
| 09:01 | BASE (not scored) | - | 113 | 114 | 141 | 216 | 149 | 16 | 2.98 | 4 | 4 | 0 |
| 09:02 | BASE | 0 | 130 | 128 | 145 | 217 | 161 | 17 | 6.68 | 11 | 23 | 0 |
| 09:03 | BASE | 0 | 117 | 129 | 147 | 217 | 166 | 23 | 8.85 | 14 | 15 | 0 |
| 09:04 | BASE | 0 | 153 | 134 | 143 | 228 | 162 | 21 | 5.35 | 11 | 8 | 0 |
| 09:05 | BASE | 0 | 151 | 138 | 152 | 240 | 167 | 17 | 4.55 | 6 | 6 | 0 |
| 09:06 | BASE | 0 | 164 | 139 | 152 | 229 | 169 | 17 | 5.89 | 9 | 10 | 0 |
| 09:07 | BASE | 0 | 117 | 122 | 136 | 218 | 151 | 19 | 5.97 | 9 | 9 | 0 |
| 09:08 | BASE | 0 | 160 | 139 | 150 | 233 | 165 | 16 | 6.18 | 9 | 10 | 0 |
| 09:09 | BASE | 0 | 175 | 140 | 147 | 246 | 158 | 18 | 4.58 | 6 | 10 | 0 |
| 09:10 | HOLD-1 (not scored) | - | 99 | 107 | 123 | 182 | 146 | 30 | 6.08 | 9 | 9 | 6 |
| 09:11 | HOLD-1 | 23,934 | 49 | 77 | 110 | 154 | 142 | 116 | 9.52 | 16 | 20 | 116 |
| 09:12 | HOLD-1 | 23,988 | 75 | 97 | 114 | 157 | 148 | 63 | 1.29 | 12 | 50 | 0 |
| 09:13 | HOLD-1 | 24,035 | 34 | 81 | 105 | 154 | 154 | 222 | 10.97 | 20 | 19 | 185 |
| 09:14 | HOLD-1 | 23,989 | 165 | 125 | 136 | 204 | 152 | 14 | 1.17 | 0 | 0 | 0 |
| 09:15 | HOLD-2 (not scored) | - | 168 | 132 | 129 | 192 | 142 | 12 | 1.01 | 0 | 0 | 0 |
| 09:16 | HOLD-2 | 42,182 | 145 | 117 | 126 | 178 | 144 | 132 | 1.48 | 0 | 0 | 119 |
| 09:17 | HOLD-2 | 41,851 | 146 | 114 | 124 | 165 | 144 | 130 | 2.06 | 0 | 0 | 351 |
| 09:18 | HOLD-2 | 41,900 | 45 | 62 | 85 | 106 | 144 | 429 | 11.95 | 33 | 34 | 367 |
| 09:19 | HOLD-2 | 41,934 | 9 | 35 | 67 | 80 | 142 | 302 | 15.83 | 58 | 37 | 221 |
| 09:20 | HOLD-3 (not scored) | - | 6 | 23 | 57 | 68 | 139 | 338 | 18.91 | 103 | 43 | 355 |
| 09:21 | HOLD-3 | 61,120 | 2 | 15 | 36 | 38 | 135 | 1,403 | 23.28 | 224 | 150 | 1,383 |
| 09:22 | HOLD-3 | 60,967 | 5 | 20 | 55 | 58 | 137 | 1,455 | 22.11 | 326 | 98 | 1,078 |
| 09:23 | HOLD-3 | 60,655 | 2 | 20 | 48 | 66 | 137 | 770 | 19.19 | 426 | 54 | 272 |
| 09:24 | HOLD-3 | 60,656 | 3 | 22 | 53 | 58 | 134 | 1,666 | 22.15 | 517 | 136 | 1,067 |
| 09:25 | HOLD-3 (not scored) | - | 2 | 20 | 46 | 53 | 135 | 1,494 | 21.28 | 602 | 46 | 871 |
| 09:26 | HOLD-3 (not scored) | - | 3 | 20 | 41 | 50 | 130 | 1,481 | 22.73 | 725 | 100 | 1,243 |
| 09:27 | HOLD-3 (not scored) | - | 6 | 18 | 52 | 50 | 142 | 1,803 | 21.78 | 819 | 111 | 892 |
| 09:28 | HOLD-4 (not scored) | - | 4 | 27 | 67 | 62 | 144 | 1,422 | 20.06 | 875 | 68 | 499 |
| 09:29 | HOLD-4 | 61,029 | 3 | 17 | 42 | 44 | 135 | 1,768 | 21.32 | 982 | 132 | 822 |
| 09:30 | RETURN (not scored) | - | 12 | 65 | 114 | 143 | 176 | 997 | 18.32 | 985 | 34 | 0 |
| 09:31 | RETURN | 0 | 17 | 77 | 127 | 147 | 186 | 878 | 18.02 | 858 | 35 | 0 |
| 09:32 | RETURN | 0 | 19 | 72 | 128 | 168 | 164 | 751 | 17.95 | 744 | 32 | 0 |
| 09:33 | RETURN | 0 | 16 | 72 | 131 | 164 | 174 | 648 | 18.16 | 633 | 39 | 0 |
| 09:34 | RETURN | 0 | 21 | 76 | 122 | 163 | 163 | 592 | 18.32 | 577 | 35 | 0 |
| 09:35 | RETURN | 0 | 19 | 85 | 117 | 143 | 167 | 505 | 17.66 | 482 | 42 | 0 |
| 09:36 | RETURN | 0 | 25 | 75 | 115 | 166 | 150 | 399 | 17.17 | 383 | 31 | 0 |
| 09:37 | RETURN | 0 | 26 | 81 | 114 | 171 | 154 | 295 | 16.04 | 282 | 32 | 0 |
| 09:38 | RETURN | 0 | 23 | 83 | 113 | 175 | 158 | 210 | 16.72 | 170 | 48 | 0 |
| 09:39 | RETURN | 0 | 21 | 77 | 120 | 165 | 144 | 102 | 14.14 | 89 | 27 | 0 |
| 09:40 | RETURN | 0 | 44 | 100 | 128 | 202 | 147 | 39 | 9.17 | 25 | 16 | 0 |
| 09:41 | tail | - | 76 | 60 | 62 | 106 | 76 | 4 | 5.33 | 9 | 10 | 0 |
| 09:42 | tail | - | 0 | 0 | 0 | 0 | 0 | 10 | 5.33 | 10 | 10 | 0 |
| 09:43 | tail | - | 0 | 0 | 0 | 0 | 0 | 2 | 1.07 | 4 | 2 | 0 |
| 09:44 | tail | - | 0 | 0 | 0 | 0 | 0 | 14 | 6.93 | 14 | 13 | 0 |
| 09:45 | tail | - | 0 | 0 | 0 | 0 | 0 | 8 | 4.27 | 8 | 8 | 0 |
| 09:46 | tail | - | 0 | 0 | 0 | 0 | 0 | 12 | 6.40 | 12 | 12 | 0 |

## What this seems to show

- **The floor slowdown tracked the ready mass and the outside heavy stream, not our payment offer.** Over the 40 minutes from 09:01Z to 09:40Z (BASE to the end of RETURN), the floor's hops per minute had a rank correlation (Spearman) of −0.93 with the ready mass, −0.86 with the count of other transactions at fee rate 100 in the mempool, and −0.89 with other ready transactions, against −0.26 with our payment submit-OK that minute. In the 15 minutes with a ready mass at or under 9 blocks the floor landed a median of 146 hops (lowest 75); in the 25 minutes over 9 blocks, a median of 16 (highest 49). No minute crossed that split. In the 16 minutes with fewer than 20 other fee-100 transactions in the mempool the floor's median was 145.5 (lowest 49); in the 24 minutes with 20 or more, 14 (highest 45). We read 9 blocks as where this run's floor fell off, not as a constant.
- **The clearest pair of minutes.** At 09:16–09:17Z, with 700 tx/s of our payments running, the outside stream was absent from the desk mempool (0 other entries, ready mass 1.5–2.1 blocks) and floor landed 145 and 146 hops, at its BASE rate. At 09:31–09:39Z, with our payment offer at 0, the outside stream's backlog was 89–858 entries (ready mass 14–18 blocks) and floor landed 16–26 hops a minute. Load from us was not needed for the floor to be slow, and 700 tx/s of it did not slow the floor while the stream was away. The stream was absent from the desk mempool from about 09:14Z to 09:17Z and present in every other minute of the run.
- **Our load still mattered, through the stream.** From 09:18Z, the outside stream came back and its count in the desk mempool rose from 33 to 982 by the HOLD-4 minute (09:29Z), with 43–150 other entries ready at a time. In the HOLD-3 and HOLD-4 minutes where the node's own template held more than 200 transactions, nearly all our payments (09:21, 09:24, 09:27), that template held no heavy transaction (storage mass about 124,000–126,000). Our payments at 150 sompi/gram seem to have pushed the 100 sompi/gram heavy stream back, so its chained backlog grew to about 1,000 entries. After our offer went to 0, that backlog, not ours, held the floor back: our payments in the desk mempool were 0 from the first RETURN minute.
- **Drain time after RETURN.** Other fee-100 transactions in the desk mempool went 985 (09:30Z), 858, 744, 633, 577, 482, 383, 282, 170, 89, 25 (09:40Z), about 55–125 fewer per minute (96 on average), and 9 at 09:41Z, back in the range the probe read before the open (2–19). That is about 11 minutes from the rate going to 0 (09:30:12Z) to a pre-open-size mempool. Ready mass fell under 9 blocks only at 09:41Z. The floor did not get back to its BASE rate inside the 10 RETURN minutes (16–26 hops a minute, then 44 at 09:40Z). In the partial minute 09:41Z, with a mempool median of 4 and before the families stopped at 09:41:24Z, the floor landed 76 hops, more than in any RETURN minute.
- **The higher tiers, in fee order.** In RETURN, double ran at about 60 percent of its BASE rate (80 against 134 a minute), triple about 83 percent, triple-pub about 73 percent, high about 99 percent. Floor ran at about 16 percent. In HOLD-3, with both the stream's backlog and our payments in the mempool, floor ran at 2 percent, double 14, triple 33, triple-pub 24, high 84. High landed every OK hop in every step, median 0.9–1.2 s.
- **At low payment steps the cheap tiers were not slowed by the offer itself.** HOLD-1 at 400 and HOLD-2 at 700 were mixed minutes: the floor's dips (49, 75, 34 at 09:11–09:13Z; 45 and 9 at 09:18–09:19Z) came in minutes with the stream in the mempool and ready mass over 9 blocks, and its BASE-level minutes (165, 168, 145, 146 at 09:14–09:17Z) in minutes without it. We cannot, from this run, put a payment rate on where cheap chains start to slow on their own, because the outside stream moved the floor more than our steps did.
- **This fits pre-run 10's slow start.** The history scan before the open (desk node, selected chain, read-only) found the stream's transactions (four 0.6 tKAS outputs, over 200,000 storage mass) in 0 of 943 chain blocks of pre-run 9's HOLD-1 window (01:13–01:16Z) and 0 in its RETURN (01:30–01:33Z), its tail (01:34–01:38Z) and the 10 minutes before it (01:00–01:10Z); 0 at 03:00Z and 05:00Z (3-minute windows, 1,139 and 1,085 chain blocks); 416 in 1,141 chain blocks at 06:00Z (91 percent of mass); 1,089 in 1,127 at 07:00Z (96 percent); 1,809 in 1,874 in the 5 minutes before pre-run 10's first payment (07:20–07:25Z, 96 percent of mass); 690 in 909 in pre-run 10's HOLD-1 window (07:28–07:31Z, 87 percent of those blocks' mass); 1,519 in 1,520 in pre-run 10's tail (07:49–07:53Z, 99 percent). So pre-run 9's fast floor ran before the stream, and pre-run 10's slow floor ran with it. That is consistent, and it is still a comparison across two runs and one node.
- **The counter kept pace.** Every whole minute from 09:01Z to the end of the tail was marked kept pace: DAA gap at most 2 against the kept public kaspad, sink age at most about 0.85 s; in RETURN each minute was final about 19–21 s after its end. No minute was `LAGGING`. The start minute (09:00Z) was partial and the last tail minute (09:46Z) not final, as marked.
- **Same fee, different path, again in the same direction.** Triple-pub (300, public) landed more hops than desk triple in every step (6,084 against 4,326 over the run) and faster (BASE 0.6 s against 1.0 s). As in pre-runs 9 and 10, the selection rule does not explain that; the node path may.
- **Mini matched the desk in every cohort cell.** Mini's one-hop-per-transaction count matched the desk's five cohort columns in 155 of 155 cells over the 31 scored minutes (BASE 40, HOLD-1 20, HOLD-2 20, HOLD-3 20, HOLD-4 5, RETURN 50). Mini's non-coinbase ran about 190–270 a minute above the desk's in every minute (0.3–0.8 percent under load, 4.8–6.6 percent at BASE and RETURN, where the totals are small); we did not establish why. Removals after a minute had closed: 0, logged. The desk counter stays the inclusion figure.

## Spend

- Payment fees: the pile's coin total went from 188,079.03 tKAS (the six sender-pool start files, pre-run 10's end) to 185,828.62 tKAS (this run's end pool snapshots): 2,250.41 tKAS for 923,812 payments, about 0.0024 tKAS each, as in pre-run 10. 8,400 coins before and after.
- Family re-funding, before hashes: `fund11.mjs` at 08:18:37Z sent 15 transactions, none rejected, one fresh genesis coin to each of keys 1–15. The lane read 5,511 coins and 239,371 usable tKAS after that funding (08:22Z), and 5,510 coins and 215,651 usable tKAS when status.mjs was read after the run (2026-11-12, about 09:48Z). That is 23,720 usable tKAS over the run, about 1.06 tKAS per family hop landed (22,383), close to pre-run 10's ratio (about 1.09). It is not split further here. Keys 1–15 have no genesis coin left; a next repo funds them again.
- Both stay far above the abort line (2,500 coins, 18,000 usable tKAS). At this run's family spend, the lane covers several more runs of this size, not an open-ended series.

## What a next attempt could try (not opened)

1. Ask the question this run points at: what fee rate keeps a cheap chain ahead of a heavy same-fee competitor? Put the families on rates just above 100 (for example 100 / 110 / 126 / 150 / 200) and read them against the ready mass, rather than against a payment ladder.
2. Leave our payments out of that run, or keep them off the tiers being compared. This run's payments at 150 are what pushed the outside stream back and grew the backlog; a 150 family cohort would share a rate with them.
3. If the outside stream may be gone by then, consider one heavy-mass competitor lane of our own, modest and short, so the condition can be set and switched off. It would also delay other TN10 users' heavy transactions while it runs, so it should be bounded and recorded.
4. Keep the probe; it is what turned pre-run 10's open question into this one. Keep Mini's count; it matched in 155 of 155 cells. The desk counter stays the inclusion figure.
5. The bot stays a `NO SEND` until a third unique kaspad answers.
