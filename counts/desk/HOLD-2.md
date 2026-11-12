MET

Scored on submit-OK, not on inclusion. Inclusion, reported and not scored: in 4 of 4 minutes our payments included (desk counter) were within 10 percent of submit-OK.

# HOLD-2, desk, pre-run 11

> Counts only. Submit-OK is the desk's sender log. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

Payment offer 700 tx/s at 150 sompi/gram, from 6 payment senders, 3 per kept public node (2 unique kaspads), each its own process and connection. Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, double (families 5–7) 200 sompi/gram on the desk's private node, triple (families 8–10) 300 sompi/gram on the desk's private node, triple-pub (families 11–13) 300 sompi/gram on the kept public kaspads, high (families 14–16) 1000 sompi/gram on the desk's private node (public map 11:public-1,12:public-5,13:public-1).

Payment pile: 8,400 coins on the payment key at the preflight, dealt evenly over the 6 senders before the first payment (last deal, start: 8,400 coins in all, 1,400 / 1,400 / 1,400 / 1,400 / 1,400 / 1,400, even). A deal never holds more coins than the preflight pile. A coin is re-used about once a second, so one sender's ceiling is about its pool per second.

## Submit-OK and included, per minute

| Minute (UTC) | Pay submit-OK | Our payments included | Included, all non-coinbase | Counter |
|---|---:|---:|---:|---|
| 2026-11-12T09:16 | 42,182 | 41,943 | 45,603 | kept pace |
| 2026-11-12T09:17 | 41,851 | 41,852 | 45,522 | kept pace |
| 2026-11-12T09:18 | 41,900 | 41,834 | 45,521 | kept pace |
| 2026-11-12T09:19 | 41,934 | 41,889 | 45,828 | kept pace |

Submit-OK counts in the minute a submit was answered. Included counts in the minute of the chain block that accepted it, so a payment submitted late in one minute can be included in the next. "Kept pace" means the desk node's DAA stayed within 100 of the kept public kaspad and its sink was under 30 s old in every sample of that minute; "LAGGING" means it did not, and the count is what the node had accepted, not a network figure.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | Double hops (200) | Triple hops (300) | Triple-pub hops (300, public) | High hops (1000) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-12T09:16 | 45,603 | 41,943 | 145 | 117 | 126 | 178 | 144 | 3,029 | 340 | 0 | 443 | 20 | kept pace |
| 2026-11-12T09:17 | 45,522 | 41,852 | 146 | 114 | 124 | 165 | 144 | 3,042 | 311 | 1 | 578 | 19 | kept pace |
| 2026-11-12T09:18 | 45,521 | 41,834 | 45 | 62 | 85 | 106 | 144 | 3,257 | 311 | 1 | 339 | 20 | kept pace |
| 2026-11-12T09:19 | 45,828 | 41,889 | 9 | 35 | 67 | 80 | 142 | 3,606 | 314 | 0 | 591 | 19 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. Double (families 5–7, desk private node): 200 sompi/gram per hop. Triple (families 8–10, desk private node): 300 sompi/gram per hop. Triple-pub (families 11–13, kept public kaspads): 300 sompi/gram per hop. High (families 14–16, desk private node): 1000 sompi/gram per hop. The rate rides on each hop line to the one builder. Payments pay 150.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 24 (583), 26 (577), 25 (571), 23 (501), 27 (495), 28 (417), 22 (373), 29 (349), 21 (261), 30 (245), 31 (185), 20 (165), and 66 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | Double OK / att / rate rej / full rej / waiting | Triple OK / att / rate rej / full rej / waiting | Triple-pub OK / att / rate rej / full rej / waiting | High OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---|---:|---:|---|
| 2026-11-12T09:16 | 42,182 | 42,182 | 0 | 0 | 0 | 142 / 352 / 0 / 0 / 4 | 114 / 270 / 0 / 0 / 0 | 125 / 266 / 0 / 0 / 1 | 176 / 275 / 0 / 0 / 9 | 144 / 270 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:17 | 41,851 | 41,851 | 0 | 0 | 0 | 149 / 352 / 0 / 0 / 7 | 117 / 258 / 0 / 0 / 3 | 126 / 265 / 0 / 0 / 3 | 167 / 268 / 0 / 0 / 11 | 144 / 285 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:18 | 41,900 | 41,900 | 0 | 0 | 0 | 45 / 304 / 0 / 0 / 7 | 62 / 245 / 0 / 0 / 3 | 85 / 251 / 0 / 0 / 3 | 106 / 250 / 0 / 0 / 11 | 144 / 274 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:19 | 41,934 | 41,934 | 0 | 0 | 0 | 9 / 286 / 0 / 0 / 8 | 35 / 232 / 0 / 0 / 3 | 67 / 239 / 0 / 0 / 3 | 80 / 242 / 0 / 0 / 11 | 142 / 278 / 0 / 0 / 3 | 2 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 11 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 37,800 to 46,200 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits floor, double, triple and high on the desk's private node, which takes no payment submit and which the desk counter reads; triple-pub (11:public-1,12:public-5,13:public-1) reads and submits on kept public kaspads, the payments' nodes.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 621389730 | 84,054 | 0 | 0 | 41 |
| 5 | yes | 621389730 | 83,813 | 0 | 0 | 38 |

## Payment senders

| Sender | Node | Pay submit-OK | Rejects | Minutes with a row |
|---|---:|---:|---:|---:|
| 1.1 | 1 | 28,017 | 0 | 4 of 4 |
| 1.2 | 1 | 28,010 | 0 | 4 of 4 |
| 1.3 | 1 | 28,027 | 0 | 4 of 4 |
| 5.1 | 5 | 28,014 | 0 | 4 of 4 |
| 5.2 | 5 | 27,894 | 0 | 4 of 4 |
| 5.3 | 5 | 27,905 | 0 | 4 of 4 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 342 of 345 | 1484 | 2887 |
| double | 328 of 328 | 1439 | 5368 |
| triple | 403 of 403 | 1348 | 3503 |
| triple-pub | 529 of 529 | 884 | 2822 |
| high | 574 of 574 | 1086 | 1597 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Triple and triple-pub pay the same rate; they differ only in the node a hop is read and submitted on.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Floor in mempool / ready | Double in mempool / ready | Triple in mempool / ready | Triple-pub in mempool / ready | High in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: floor | Template: double | Template: triple | Template: triple-pub | Template: high | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-12T09:16 | 2 | 132 | 132 | 1.48 | 0 | 0 | - | - | 119 | 4 / 4 | 3 / 3 | 3 / 3 | 0 / 0 | 3 / 3 | 126 | 462,424 | 0 | 119 | 3 | 3 | 3 | 0 | 3 | 0 | 270.5 / 167.4 / 112.9 | 488 | 375 |
| 2026-11-12T09:17 | 3 | 130 | 362 | 2.06 | 0 | 0 | - | - | 351 | 4 / 4 | 3 / 3 | 3 / 3 | 1 / 1 | 3 / 3 | 230 | 126,226 | 0 | 217 | 0 | 0 | 0 | 0 | 3 | 0 | 347.5 / 177.7 / 113.9 | 360 | 411 |
| 2026-11-12T09:18 | 3 | 429 | 414 | 11.95 | 49 | 34 | 33 | 266,642 | 367 | 4 / 4 | 3 / 3 | 3 / 3 | 1 / 1 | 3 / 3 | 191 | 168,324 | 0 | 178 | 0 | 1 | 1 | 0 | 3 | 4 | 317.7 / 174.4 / 113.6 | 493 | 493 |
| 2026-11-12T09:19 | 3 | 302 | 270 | 15.83 | 70 | 37 | 58 | 266,640 | 221 | 4 / 4 | 3 / 3 | 3 / 3 | 1 / 1 | 2 / 2 | 80 | 350,456 | 1 | 76 | 0 | 1 | 1 | 0 | 2 | 2 | 258.2 / 165.1 / 112.7 | 602 | 666 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs; its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
