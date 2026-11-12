OBSERVATION

Scored on submit-OK, not on inclusion. Inclusion, reported and not scored: in 10 of 10 minutes our payments included (desk counter) were within 10 percent of submit-OK.

# RETURN, desk, pre-run 11

> Counts only. Submit-OK is the desk's sender log. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

RETURN is families only: the payment offer went to 0 right after the HOLD-4 minute (the senders idled; none was stopped). 10 whole minutes, to read how fast the mempool drained and the cheap chains recovered against BASE. Not scored. Pre-runs 7 to 10 scored RETURN at 1,013; pre-run 11 does not, on purpose.

Payment offer 0 tx/s at 150 sompi/gram, from 6 payment senders, 3 per kept public node (2 unique kaspads), each its own process and connection. Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, double (families 5–7) 200 sompi/gram on the desk's private node, triple (families 8–10) 300 sompi/gram on the desk's private node, triple-pub (families 11–13) 300 sompi/gram on the kept public kaspads, high (families 14–16) 1000 sompi/gram on the desk's private node (public map 11:public-1,12:public-5,13:public-1).

Payment pile: 8,400 coins on the payment key at the preflight, dealt evenly over the 6 senders before the first payment (last deal, start: 8,400 coins in all, 1,400 / 1,400 / 1,400 / 1,400 / 1,400 / 1,400, even). A deal never holds more coins than the preflight pile. A coin is re-used about once a second, so one sender's ceiling is about its pool per second.

## Submit-OK and included, per minute

| Minute (UTC) | Pay submit-OK | Our payments included | Included, all non-coinbase | Counter |
|---|---:|---:|---:|---|
| 2026-11-12T09:31 | 0 | 0 | 4,200 | kept pace |
| 2026-11-12T09:32 | 0 | 0 | 4,121 | kept pace |
| 2026-11-12T09:33 | 0 | 0 | 4,037 | kept pace |
| 2026-11-12T09:34 | 0 | 0 | 4,055 | kept pace |
| 2026-11-12T09:35 | 0 | 0 | 4,021 | kept pace |
| 2026-11-12T09:36 | 0 | 0 | 4,038 | kept pace |
| 2026-11-12T09:37 | 0 | 0 | 4,059 | kept pace |
| 2026-11-12T09:38 | 0 | 0 | 4,058 | kept pace |
| 2026-11-12T09:39 | 0 | 0 | 3,985 | kept pace |
| 2026-11-12T09:40 | 0 | 0 | 4,123 | kept pace |

Submit-OK counts in the minute a submit was answered. Included counts in the minute of the chain block that accepted it, so a payment submitted late in one minute can be included in the next. "Kept pace" means the desk node's DAA stayed within 100 of the kept public kaspad and its sink was under 30 s old in every sample of that minute; "LAGGING" means it did not, and the count is what the node had accepted, not a network figure.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | Double hops (200) | Triple hops (300) | Triple-pub hops (300, public) | High hops (1000) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-12T09:31 | 4,200 | 0 | 17 | 77 | 127 | 147 | 186 | 3,646 | 397 | 0 | 402 | 20 | kept pace |
| 2026-11-12T09:32 | 4,121 | 0 | 19 | 72 | 128 | 168 | 164 | 3,570 | 421 | 2 | 559 | 19 | kept pace |
| 2026-11-12T09:33 | 4,037 | 0 | 16 | 72 | 131 | 164 | 174 | 3,481 | 385 | 1 | 564 | 20 | kept pace |
| 2026-11-12T09:34 | 4,055 | 0 | 21 | 76 | 122 | 163 | 163 | 3,510 | 397 | 0 | 484 | 21 | kept pace |
| 2026-11-12T09:35 | 4,021 | 0 | 19 | 85 | 117 | 143 | 167 | 3,490 | 345 | 1 | 676 | 19 | kept pace |
| 2026-11-12T09:36 | 4,038 | 0 | 25 | 75 | 115 | 166 | 150 | 3,507 | 418 | 1 | 450 | 20 | kept pace |
| 2026-11-12T09:37 | 4,059 | 0 | 26 | 81 | 114 | 171 | 154 | 3,513 | 395 | 1 | 690 | 19 | kept pace |
| 2026-11-12T09:38 | 4,058 | 0 | 23 | 83 | 113 | 175 | 158 | 3,506 | 399 | 1 | 599 | 20 | kept pace |
| 2026-11-12T09:39 | 3,985 | 0 | 21 | 77 | 120 | 165 | 144 | 3,458 | 377 | 0 | 655 | 20 | kept pace |
| 2026-11-12T09:40 | 4,123 | 0 | 44 | 100 | 128 | 202 | 147 | 3,502 | 380 | 1 | 374 | 19 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. Double (families 5–7, desk private node): 200 sompi/gram per hop. Triple (families 8–10, desk private node): 300 sompi/gram per hop. Triple-pub (families 11–13, kept public kaspads): 300 sompi/gram per hop. High (families 14–16, desk private node): 1000 sompi/gram per hop. The rate rides on each hop line to the one builder. Payments pay 150.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 24 (583), 23 (579), 22 (496), 25 (478), 26 (464), 21 (462), 20 (343), 27 (333), 28 (256), 19 (233), 29 (202), 30 (155), and 67 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | Double OK / att / rate rej / full rej / waiting | Triple OK / att / rate rej / full rej / waiting | Triple-pub OK / att / rate rej / full rej / waiting | High OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---|---:|---:|---|
| 2026-11-12T09:31 | 0 | 0 | 0 | 0 | 0 | 16 / 290 / 0 / 0 / 7 | 76 / 248 / 0 / 0 / 2 | 128 / 265 / 0 / 0 / 3 | 148 / 264 / 0 / 0 / 10 | 186 / 288 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:32 | 0 | 0 | 0 | 0 | 0 | 20 / 294 / 0 / 0 / 8 | 73 / 247 / 0 / 0 / 3 | 128 / 264 / 0 / 0 / 3 | 169 / 277 / 0 / 0 / 11 | 164 / 284 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:33 | 0 | 0 | 0 | 0 | 0 | 16 / 292 / 0 / 0 / 8 | 72 / 249 / 0 / 0 / 2 | 131 / 266 / 0 / 0 / 3 | 164 / 270 / 0 / 0 / 11 | 174 / 296 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-12T09:34 | 0 | 0 | 0 | 0 | 0 | 21 / 294 / 0 / 0 / 8 | 76 / 248 / 0 / 0 / 3 | 122 / 266 / 0 / 0 / 3 | 163 / 271 / 0 / 0 / 11 | 163 / 281 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:35 | 0 | 0 | 0 | 0 | 0 | 19 / 293 / 0 / 0 / 8 | 85 / 251 / 0 / 0 / 3 | 117 / 258 / 0 / 0 / 3 | 143 / 264 / 0 / 0 / 11 | 167 / 295 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:36 | 0 | 0 | 0 | 0 | 0 | 25 / 296 / 0 / 0 / 8 | 74 / 250 / 0 / 0 / 2 | 116 / 265 / 0 / 0 / 4 | 166 / 280 / 0 / 0 / 11 | 150 / 272 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:37 | 0 | 0 | 0 | 0 | 0 | 26 / 296 / 0 / 0 / 9 | 83 / 248 / 0 / 0 / 3 | 112 / 261 / 0 / 0 / 2 | 171 / 277 / 0 / 0 / 11 | 154 / 286 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:38 | 0 | 0 | 0 | 0 | 0 | 23 / 293 / 0 / 0 / 9 | 81 / 251 / 0 / 0 / 2 | 114 / 264 / 0 / 0 / 3 | 175 / 271 / 0 / 0 / 11 | 158 / 287 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:39 | 0 | 0 | 0 | 0 | 0 | 21 / 292 / 0 / 0 / 9 | 78 / 247 / 0 / 0 / 3 | 120 / 262 / 0 / 0 / 3 | 165 / 268 / 0 / 0 / 11 | 144 / 276 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:40 | 0 | 0 | 0 | 0 | 0 | 44 / 304 / 0 / 0 / 9 | 100 / 259 / 0 / 0 / 3 | 127 / 267 / 0 / 0 / 2 | 202 / 282 / 0 / 0 / 11 | 147 / 279 / 0 / 0 / 3 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 11 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 0 to 0 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits floor, double, triple and high on the desk's private node, which takes no payment submit and which the desk counter reads; triple-pub (11:public-1,12:public-5,13:public-1) reads and submits on kept public kaspads, the payments' nodes.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 621402265 | 0 | 0 | 0 | 41 |
| 5 | yes | 621402265 | 0 | 0 | 0 | 38 |

## Payment senders

| Sender | Node | Pay submit-OK | Rejects | Minutes with a row |
|---|---:|---:|---:|---:|
| 1.1 | 1 | 0 | 0 | 10 of 10 |
| 1.2 | 1 | 0 | 0 | 10 of 10 |
| 1.3 | 1 | 0 | 0 | 10 of 10 |
| 5.1 | 5 | 0 | 0 | 10 of 10 |
| 5.2 | 5 | 0 | 0 | 10 of 10 |
| 5.3 | 5 | 0 | 0 | 10 of 10 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 230 of 231 | 7611 | 27888 |
| double | 798 of 798 | 1812 | 4356 |
| triple | 1215 of 1215 | 1249 | 2248 |
| triple-pub | 1666 of 1666 | 812 | 1951 |
| high | 1607 of 1607 | 942 | 1372 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Triple and triple-pub pay the same rate; they differ only in the node a hop is read and submitted on.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Floor in mempool / ready | Double in mempool / ready | Triple in mempool / ready | Triple-pub in mempool / ready | High in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: floor | Template: double | Template: triple | Template: triple-pub | Template: high | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-12T09:31 | 3 | 878 | 48 | 18.02 | 869 | 35 | 858 | 266,637 | 0 | 4 / 4 | 3 / 3 | 2 / 2 | 1 / 1 | 3 / 3 | 6 | 392,661 | 1 | 0 | 0 | 0 | 0 | 0 | 3 | 1 | 100.0 / 100.0 / 100.0 | 879 | 879 |
| 2026-11-12T09:32 | 3 | 751 | 48 | 17.95 | 745 | 32 | 744 | 266,637 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 3 / 3 | 3 / 3 | 6 | 476,071 | 1 | 0 | 0 | 1 | 1 | 0 | 3 | 1 | 100.0 / 100.0 / 100.0 | 784 | 784 |
| 2026-11-12T09:33 | 3 | 648 | 54 | 18.16 | 636 | 39 | 633 | 266,637 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 2 / 2 | 3 / 3 | 8 | 391,972 | 1 | 0 | 0 | 0 | 0 | 0 | 3 | 5 | 100.0 / 100.0 / 100.0 | 647 | 647 |
| 2026-11-12T09:34 | 3 | 592 | 50 | 18.32 | 578 | 35 | 577 | 266,637 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 2 / 2 | 3 / 3 | 6 | 434,494 | 1 | 0 | 0 | 0 | 0 | 1 | 3 | 2 | 102.8 / 102.0 / 100.7 | 613 | 614 |
| 2026-11-12T09:35 | 3 | 505 | 54 | 17.66 | 493 | 42 | 482 | 266,637 | 0 | 4 / 4 | 2 / 2 | 3 / 3 | 2 / 2 | 3 / 3 | 6 | 392,306 | 1 | 0 | 0 | 0 | 0 | 0 | 3 | 2 | 106.5 / 104.7 / 101.5 | 502 | 494 |
| 2026-11-12T09:36 | 3 | 399 | 44 | 17.17 | 386 | 31 | 383 | 266,637 | 0 | 4 / 4 | 3 / 3 | 2 / 2 | 1 / 1 | 3 / 3 | 6 | 477,599 | 1 | 0 | 0 | 0 | 1 | 0 | 3 | 1 | 107.2 / 105.2 / 101.7 | 394 | 440 |
| 2026-11-12T09:37 | 3 | 295 | 42 | 16.04 | 283 | 32 | 282 | 266,637 | 0 | 4 / 4 | 3 / 3 | 2 / 2 | 1 / 1 | 3 / 3 | 6 | 434,052 | 1 | 0 | 0 | 0 | 1 | 0 | 3 | 1 | 109.6 / 106.9 / 102.2 | 290 | 301 |
| 2026-11-12T09:38 | 3 | 210 | 61 | 16.72 | 196 | 48 | 170 | 266,635 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 1 / 1 | 3 / 3 | 7 | 392,086 | 1 | 0 | 0 | 0 | 0 | 0 | 3 | 4 | 118.6 / 112.9 / 103.8 | 198 | 204 |
| 2026-11-12T09:39 | 3 | 102 | 42 | 14.14 | 91 | 27 | 89 | 266,634 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 2 / 2 | 3 / 3 | 7 | 475,585 | 1 | 0 | 0 | 1 | 1 | 0 | 3 | 2 | 115.3 / 110.8 / 103.3 | 110 | 110 |
| 2026-11-12T09:40 | 3 | 39 | 29 | 9.17 | 26 | 16 | 25 | 266,634 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 1 / 1 | 3 / 3 | 6 | 474,374 | 1 | 0 | 0 | 0 | 1 | 1 | 3 | 1 | 100.4 / 100.3 / 100.1 | 35 | 39 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs; its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
