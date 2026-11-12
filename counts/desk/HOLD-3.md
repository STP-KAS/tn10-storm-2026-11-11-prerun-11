MET

Scored on submit-OK, not on inclusion. Inclusion, reported and not scored: in 4 of 4 minutes our payments included (desk counter) were within 10 percent of submit-OK.

# HOLD-3, desk, pre-run 11

> Counts only. Submit-OK is the desk's sender log. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

Payment offer 1,013 tx/s at 150 sompi/gram, from 6 payment senders, 3 per kept public node (2 unique kaspads), each its own process and connection. Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, double (families 5–7) 200 sompi/gram on the desk's private node, triple (families 8–10) 300 sompi/gram on the desk's private node, triple-pub (families 11–13) 300 sompi/gram on the kept public kaspads, high (families 14–16) 1000 sompi/gram on the desk's private node (public map 11:public-1,12:public-5,13:public-1).

Payment pile: 8,400 coins on the payment key at the preflight, dealt evenly over the 6 senders before the first payment (last deal, start: 8,400 coins in all, 1,400 / 1,400 / 1,400 / 1,400 / 1,400 / 1,400, even). A deal never holds more coins than the preflight pile. A coin is re-used about once a second, so one sender's ceiling is about its pool per second.

## Submit-OK and included, per minute

| Minute (UTC) | Pay submit-OK | Our payments included | Included, all non-coinbase | Counter |
|---|---:|---:|---:|---|
| 2026-11-12T09:21 | 61,120 | 60,650 | 64,103 | kept pace |
| 2026-11-12T09:22 | 60,967 | 60,943 | 64,562 | kept pace |
| 2026-11-12T09:23 | 60,655 | 60,320 | 63,914 | kept pace |
| 2026-11-12T09:24 | 60,656 | 61,492 | 65,127 | kept pace |

Submit-OK counts in the minute a submit was answered. Included counts in the minute of the chain block that accepted it, so a payment submitted late in one minute can be included in the next. "Kept pace" means the desk node's DAA stayed within 100 of the kept public kaspad and its sink was under 30 s old in every sample of that minute; "LAGGING" means it did not, and the count is what the node had accepted, not a network figure.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | Double hops (200) | Triple hops (300) | Triple-pub hops (300, public) | High hops (1000) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-12T09:21 | 64,103 | 60,650 | 2 | 15 | 36 | 38 | 135 | 3,227 | 281 | 0 | 494 | 19 | kept pace |
| 2026-11-12T09:22 | 64,562 | 60,943 | 5 | 20 | 55 | 58 | 137 | 3,345 | 331 | 1 | 704 | 20 | kept pace |
| 2026-11-12T09:23 | 63,914 | 60,320 | 2 | 20 | 48 | 66 | 137 | 3,321 | 320 | 1 | 847 | 19 | kept pace |
| 2026-11-12T09:24 | 65,127 | 61,492 | 3 | 22 | 53 | 58 | 134 | 3,365 | 320 | 1 | 575 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. Double (families 5–7, desk private node): 200 sompi/gram per hop. Triple (families 8–10, desk private node): 300 sompi/gram per hop. Triple-pub (families 11–13, kept public kaspads): 300 sompi/gram per hop. High (families 14–16, desk private node): 1000 sompi/gram per hop. The rate rides on each hop line to the one builder. Payments pay 150.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 24 (580), 25 (579), 26 (552), 23 (517), 27 (484), 22 (399), 28 (389), 29 (321), 21 (289), 30 (223), 20 (191), 31 (178), and 65 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | Double OK / att / rate rej / full rej / waiting | Triple OK / att / rate rej / full rej / waiting | Triple-pub OK / att / rate rej / full rej / waiting | High OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---|---:|---:|---|
| 2026-11-12T09:21 | 61,120 | 61,120 | 0 | 0 | 0 | 2 / 284 / 0 / 0 / 8 | 15 / 220 / 0 / 0 / 3 | 36 / 227 / 0 / 0 / 3 | 38 / 224 / 0 / 0 / 11 | 133 / 267 / 0 / 0 / 1 | 2 | 0 | yes |
| 2026-11-12T09:22 | 60,967 | 60,967 | 0 | 0 | 0 | 5 / 285 / 0 / 0 / 8 | 20 / 221 / 0 / 0 / 3 | 55 / 241 / 0 / 0 / 3 | 57 / 234 / 0 / 0 / 10 | 139 / 278 / 0 / 0 / 3 | 2 | 0 | yes |
| 2026-11-12T09:23 | 60,655 | 60,655 | 0 | 0 | 0 | 2 / 285 / 0 / 0 / 8 | 20 / 220 / 0 / 0 / 3 | 48 / 234 / 0 / 0 / 3 | 67 / 243 / 0 / 0 / 11 | 137 / 272 / 0 / 0 / 3 | 4 | 0 | yes |
| 2026-11-12T09:24 | 60,656 | 60,656 | 0 | 0 | 0 | 3 / 285 / 0 / 0 / 8 | 22 / 223 / 0 / 0 / 3 | 53 / 236 / 0 / 0 / 3 | 58 / 241 / 0 / 0 / 11 | 134 / 269 / 0 / 0 / 3 | 1 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 11 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 54,702 to 66,858 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits floor, double, triple and high on the desk's private node, which takes no payment submit and which the desk counter reads; triple-pub (11:public-1,12:public-5,13:public-1) reads and submits on kept public kaspads, the payments' nodes.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 621392448 | 121,728 | 0 | 0 | 42 |
| 5 | yes | 621392448 | 121,670 | 0 | 0 | 38 |

## Payment senders

| Sender | Node | Pay submit-OK | Rejects | Minutes with a row |
|---|---:|---:|---:|---:|
| 1.1 | 1 | 40,469 | 0 | 4 of 4 |
| 1.2 | 1 | 40,617 | 0 | 4 of 4 |
| 1.3 | 1 | 40,642 | 0 | 4 of 4 |
| 5.1 | 5 | 40,663 | 0 | 4 of 4 |
| 5.2 | 5 | 40,612 | 0 | 4 of 4 |
| 5.3 | 5 | 40,395 | 0 | 4 of 4 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 9 of 12 | 71271 | 123228 |
| double | 77 of 77 | 6706 | 22847 |
| triple | 192 of 192 | 2652 | 8667 |
| triple-pub | 220 of 220 | 2386 | 8281 |
| high | 543 of 543 | 1129 | 1733 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Triple and triple-pub pay the same rate; they differ only in the node a hop is read and submitted on.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Floor in mempool / ready | Double in mempool / ready | Triple in mempool / ready | Triple-pub in mempool / ready | High in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: floor | Template: double | Template: triple | Template: triple-pub | Template: high | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-12T09:21 | 3 | 1,403 | 1,574 | 23.28 | 343 | 150 | 224 | 266,640 | 1,383 | 4 / 4 | 3 / 3 | 3 / 3 | 3 / 3 | 3 / 3 | 221 | 123,957 | 0 | 206 | 0 | 0 | 0 | 0 | 2 | 13 | 381.1 / 180.7 / 114.2 | 1,842 | 1,844 |
| 2026-11-12T09:22 | 3 | 1,455 | 1,177 | 22.11 | 392 | 98 | 326 | 266,640 | 1,078 | 4 / 4 | 3 / 3 | 3 / 3 | 3 / 3 | 3 / 3 | 94 | 350,388 | 1 | 89 | 0 | 0 | 0 | 0 | 2 | 3 | 341.5 / 177.1 / 113.8 | 1,586 | 1,529 |
| 2026-11-12T09:23 | 3 | 770 | 336 | 19.19 | 484 | 54 | 426 | 266,640 | 272 | 4 / 4 | 3 / 3 | 3 / 3 | 1 / 1 | 3 / 3 | 61 | 392,396 | 1 | 35 | 0 | 0 | 0 | 0 | 3 | 4 | 208.4 / 153.1 / 111.3 | 1,418 | 1,421 |
| 2026-11-12T09:24 | 3 | 1,666 | 1,203 | 22.15 | 632 | 136 | 517 | 266,640 | 1,067 | 4 / 4 | 3 / 3 | 3 / 3 | 3 / 3 | 3 / 3 | 216 | 125,719 | 0 | 125 | 0 | 0 | 0 | 0 | 2 | 6 | 316.1 / 174.2 / 113.6 | 2,092 | 2,318 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs; its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
