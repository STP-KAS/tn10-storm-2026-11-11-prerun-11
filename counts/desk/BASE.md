OBSERVATION

Scored on submit-OK, not on inclusion. Inclusion, reported and not scored: in 8 of 8 minutes our payments included (desk counter) were within 10 percent of submit-OK.

# BASE, desk, pre-run 11

> Counts only. Submit-OK is the desk's sender log. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

BASE is families only: no payment sender was started. 8 whole minutes, after the families were attempting. It is the reference for the steps below, read on the same nodes in the same run. Not scored.

Payment offer 0 tx/s at 150 sompi/gram, from 6 payment senders, 3 per kept public node (2 unique kaspads), each its own process and connection. Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, double (families 5–7) 200 sompi/gram on the desk's private node, triple (families 8–10) 300 sompi/gram on the desk's private node, triple-pub (families 11–13) 300 sompi/gram on the kept public kaspads, high (families 14–16) 1000 sompi/gram on the desk's private node (public map 11:public-1,12:public-5,13:public-1).

Payment pile: 8,400 coins on the payment key at the preflight, dealt evenly over the 6 senders before the first payment (last deal, start: 8,400 coins in all, 1,400 / 1,400 / 1,400 / 1,400 / 1,400 / 1,400, even). A deal never holds more coins than the preflight pile. A coin is re-used about once a second, so one sender's ceiling is about its pool per second.

## Submit-OK and included, per minute

| Minute (UTC) | Pay submit-OK | Our payments included | Included, all non-coinbase | Counter |
|---|---:|---:|---:|---|
| 2026-11-12T09:02 | 0 | 0 | 4,248 | kept pace |
| 2026-11-12T09:03 | 0 | 0 | 4,242 | kept pace |
| 2026-11-12T09:04 | 0 | 0 | 4,212 | kept pace |
| 2026-11-12T09:05 | 0 | 0 | 4,268 | kept pace |
| 2026-11-12T09:06 | 0 | 0 | 4,283 | kept pace |
| 2026-11-12T09:07 | 0 | 0 | 4,339 | kept pace |
| 2026-11-12T09:08 | 0 | 0 | 4,342 | kept pace |
| 2026-11-12T09:09 | 0 | 0 | 4,241 | kept pace |

Submit-OK counts in the minute a submit was answered. Included counts in the minute of the chain block that accepted it, so a payment submitted late in one minute can be included in the next. "Kept pace" means the desk node's DAA stayed within 100 of the kept public kaspad and its sink was under 30 s old in every sample of that minute; "LAGGING" means it did not, and the count is what the node had accepted, not a network figure.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | Double hops (200) | Triple hops (300) | Triple-pub hops (300, public) | High hops (1000) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-12T09:02 | 4,248 | 0 | 130 | 128 | 145 | 217 | 161 | 3,472 | 359 | 1 | 306 | 20 | kept pace |
| 2026-11-12T09:03 | 4,242 | 0 | 117 | 129 | 147 | 217 | 166 | 3,473 | 352 | 0 | 461 | 20 | kept pace |
| 2026-11-12T09:04 | 4,212 | 0 | 153 | 134 | 143 | 228 | 162 | 3,402 | 373 | 0 | 553 | 20 | kept pace |
| 2026-11-12T09:05 | 4,268 | 0 | 151 | 138 | 152 | 240 | 167 | 3,431 | 393 | 1 | 362 | 20 | kept pace |
| 2026-11-12T09:06 | 4,283 | 0 | 164 | 139 | 152 | 229 | 169 | 3,440 | 372 | 1 | 584 | 20 | kept pace |
| 2026-11-12T09:07 | 4,339 | 0 | 117 | 122 | 136 | 218 | 151 | 3,601 | 361 | 1 | 723 | 19 | kept pace |
| 2026-11-12T09:08 | 4,342 | 0 | 160 | 139 | 150 | 233 | 165 | 3,507 | 356 | 1 | 744 | 20 | kept pace |
| 2026-11-12T09:09 | 4,241 | 0 | 175 | 140 | 147 | 246 | 158 | 3,387 | 385 | 1 | 495 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. Double (families 5–7, desk private node): 200 sompi/gram per hop. Triple (families 8–10, desk private node): 300 sompi/gram per hop. Triple-pub (families 11–13, kept public kaspads): 300 sompi/gram per hop. High (families 14–16, desk private node): 1000 sompi/gram per hop. The rate rides on each hop line to the one builder. Payments pay 150.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 26 (607), 27 (598), 25 (561), 28 (507), 29 (478), 24 (469), 30 (379), 23 (379), 31 (253), 22 (235), 32 (178), 21 (159), and 62 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | Double OK / att / rate rej / full rej / waiting | Triple OK / att / rate rej / full rej / waiting | Triple-pub OK / att / rate rej / full rej / waiting | High OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---|---:|---:|---|
| 2026-11-12T09:02 | 0 | 0 | 0 | 0 | 0 | 130 / 336 / 0 / 0 / 4 | 128 / 267 / 0 / 0 / 3 | 147 / 279 / 0 / 0 / 3 | 217 / 279 / 0 / 0 / 2 | 161 / 294 / 0 / 0 / 3 | 0 | 0 | no: proc-row-missing |
| 2026-11-12T09:03 | 0 | 0 | 0 | 0 | 0 | 117 / 334 / 0 / 0 / 4 | 129 / 270 / 0 / 0 / 3 | 147 / 278 / 0 / 0 / 3 | 218 / 276 / 0 / 0 / 3 | 166 / 291 / 0 / 0 / 3 | 0 | 0 | no: proc-row-missing |
| 2026-11-12T09:04 | 0 | 0 | 0 | 0 | 0 | 153 / 357 / 0 / 0 / 4 | 134 / 278 / 0 / 0 / 3 | 143 / 281 / 0 / 0 / 3 | 228 / 284 / 0 / 0 / 3 | 162 / 291 / 0 / 0 / 3 | 0 | 0 | no: proc-row-missing |
| 2026-11-12T09:05 | 0 | 0 | 0 | 0 | 0 | 151 / 352 / 0 / 0 / 4 | 138 / 270 / 0 / 0 / 3 | 152 / 280 / 0 / 0 / 3 | 240 / 283 / 0 / 0 / 3 | 167 / 285 / 0 / 0 / 3 | 0 | 0 | no: proc-row-missing |
| 2026-11-12T09:06 | 0 | 0 | 0 | 0 | 0 | 164 / 348 / 0 / 0 / 4 | 139 / 275 / 0 / 0 / 3 | 151 / 278 / 0 / 0 / 2 | 229 / 286 / 0 / 0 / 3 | 166 / 280 / 0 / 0 / 0 | 0 | 0 | no: proc-row-missing |
| 2026-11-12T09:07 | 0 | 0 | 0 | 0 | 0 | 115 / 334 / 0 / 0 / 2 | 122 / 269 / 0 / 0 / 3 | 137 / 270 / 0 / 0 / 3 | 218 / 284 / 0 / 0 / 3 | 154 / 280 / 0 / 0 / 3 | 0 | 0 | no: proc-row-missing |
| 2026-11-12T09:08 | 0 | 0 | 0 | 0 | 0 | 159 / 355 / 0 / 0 / 1 | 139 / 275 / 0 / 0 / 3 | 150 / 280 / 0 / 0 / 3 | 232 / 280 / 0 / 0 / 2 | 165 / 290 / 0 / 0 / 3 | 0 | 0 | no: proc-row-missing |
| 2026-11-12T09:09 | 0 | 0 | 0 | 0 | 0 | 178 / 361 / 0 / 0 / 4 | 140 / 278 / 0 / 0 / 3 | 147 / 280 / 0 / 0 / 3 | 247 / 289 / 0 / 0 / 3 | 158 / 283 / 0 / 0 / 3 | 0 | 0 | no: proc-row-missing |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 11 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 0 to 0 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits floor, double, triple and high on the desk's private node, which takes no payment submit and which the desk counter reads; triple-pub (11:public-1,12:public-5,13:public-1) reads and submits on kept public kaspads, the payments' nodes.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 621384197 | 0 | 0 | 0 | 41 |
| 5 | yes | 621384197 | 0 | 0 | 0 | 39 |

## Payment senders

| Sender | Node | Pay submit-OK | Rejects | Minutes with a row |
|---|---:|---:|---:|---:|
| 1.1 | 1 | 0 | 0 | 0 of 8 |
| 1.2 | 1 | 0 | 0 | 0 of 8 |
| 1.3 | 1 | 0 | 0 | 0 of 8 |
| 5.1 | 5 | 0 | 0 | 0 of 8 |
| 5.2 | 5 | 0 | 0 | 0 of 8 |
| 5.3 | 5 | 0 | 0 | 0 of 8 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 1167 of 1167 | 1225 | 2929 |
| double | 1069 of 1069 | 1121 | 1914 |
| triple | 1174 of 1174 | 1041 | 1615 |
| triple-pub | 1829 of 1829 | 589 | 1151 |
| high | 1299 of 1299 | 926 | 1412 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Triple and triple-pub pay the same rate; they differ only in the node a hop is read and submitted on.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Floor in mempool / ready | Double in mempool / ready | Triple in mempool / ready | Triple-pub in mempool / ready | High in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: floor | Template: double | Template: triple | Template: triple-pub | Template: high | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-12T09:02 | 3 | 17 | 31 | 6.68 | 23 | 23 | 11 | 266,491 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 3 / 3 | 3 / 3 | 15 | 435,125 | 1 | 0 | 0 | 1 | 1 | 0 | 3 | 12 | 140.2 / 125.6 / 106.8 | 31 | 31 |
| 2026-11-12T09:03 | 3 | 23 | 30 | 8.85 | 15 | 15 | 14 | 266,475 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 2 / 2 | 3 / 3 | 6 | 477,912 | 1 | 0 | 0 | 0 | 1 | 1 | 3 | 1 | 152.3 / 131.7 / 108.0 | 23 | 24 |
| 2026-11-12T09:04 | 3 | 21 | 21 | 5.35 | 8 | 8 | 11 | 266,459 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 1 / 1 | 3 / 3 | 8 | 378,063 | 0 | 0 | 0 | 1 | 2 | 1 | 3 | 1 | 126.3 / 117.7 / 105.0 | 16 | 13 |
| 2026-11-12T09:05 | 3 | 17 | 18 | 4.55 | 6 | 6 | 6 | 266,442 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 0 / 0 | 3 / 3 | 6 | 476,345 | 1 | 0 | 0 | 0 | 1 | 0 | 3 | 1 | 118.4 / 112.8 / 103.8 | 13 | 15 |
| 2026-11-12T09:06 | 3 | 17 | 18 | 5.89 | 10 | 10 | 9 | 266,421 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 0 / 0 | 3 / 3 | 6 | 476,264 | 1 | 0 | 0 | 1 | 0 | 0 | 3 | 1 | 115.5 / 110.9 / 103.3 | 15 | 23 |
| 2026-11-12T09:07 | 3 | 19 | 23 | 5.97 | 9 | 9 | 9 | 266,394 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 1 / 1 | 2 / 2 | 6 | 477,488 | 1 | 0 | 0 | 0 | 0 | 1 | 2 | 1 | 132.7 / 121.5 / 105.9 | 21 | 20 |
| 2026-11-12T09:08 | 3 | 16 | 23 | 6.18 | 10 | 10 | 9 | 266,368 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 0 / 0 | 3 / 3 | 6 | 475,879 | 1 | 0 | 0 | 0 | 1 | 0 | 3 | 1 | 133.8 / 122.1 / 106.0 | 15 | 14 |
| 2026-11-12T09:09 | 3 | 18 | 26 | 4.58 | 10 | 10 | 6 | 266,335 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 1 / 1 | 3 / 3 | 6 | 476,004 | 1 | 0 | 1 | 1 | 1 | 1 | 3 | 1 | 138.8 / 124.9 / 106.6 | 18 | 16 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs; its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
