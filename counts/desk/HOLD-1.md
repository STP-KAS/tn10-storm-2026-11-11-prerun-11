MET

Scored on submit-OK, not on inclusion. Inclusion, reported and not scored: in 4 of 4 minutes our payments included (desk counter) were within 10 percent of submit-OK.

# HOLD-1, desk, pre-run 11

> Counts only. Submit-OK is the desk's sender log. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

Payment offer 400 tx/s at 150 sompi/gram, from 6 payment senders, 3 per kept public node (2 unique kaspads), each its own process and connection. Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, double (families 5–7) 200 sompi/gram on the desk's private node, triple (families 8–10) 300 sompi/gram on the desk's private node, triple-pub (families 11–13) 300 sompi/gram on the kept public kaspads, high (families 14–16) 1000 sompi/gram on the desk's private node (public map 11:public-1,12:public-5,13:public-1).

Payment pile: 8,400 coins on the payment key at the preflight, dealt evenly over the 6 senders before the first payment (last deal, start: 8,400 coins in all, 1,400 / 1,400 / 1,400 / 1,400 / 1,400 / 1,400, even). A deal never holds more coins than the preflight pile. A coin is re-used about once a second, so one sender's ceiling is about its pool per second.

## Submit-OK and included, per minute

| Minute (UTC) | Pay submit-OK | Our payments included | Included, all non-coinbase | Counter |
|---|---:|---:|---:|---|
| 2026-11-12T09:11 | 23,934 | 24,354 | 28,297 | kept pace |
| 2026-11-12T09:12 | 23,988 | 23,692 | 27,711 | kept pace |
| 2026-11-12T09:13 | 24,035 | 23,951 | 27,900 | kept pace |
| 2026-11-12T09:14 | 23,989 | 24,223 | 28,089 | kept pace |

Submit-OK counts in the minute a submit was answered. Included counts in the minute of the chain block that accepted it, so a payment submitted late in one minute can be included in the next. "Kept pace" means the desk node's DAA stayed within 100 of the kept public kaspad and its sink was under 30 s old in every sample of that minute; "LAGGING" means it did not, and the count is what the node had accepted, not a network figure.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | Double hops (200) | Triple hops (300) | Triple-pub hops (300, public) | High hops (1000) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-12T09:11 | 28,297 | 24,354 | 49 | 77 | 110 | 154 | 142 | 3,416 | 348 | 2 | 429 | 20 | kept pace |
| 2026-11-12T09:12 | 27,711 | 23,692 | 75 | 97 | 114 | 157 | 148 | 3,430 | 359 | 2 | 429 | 19 | kept pace |
| 2026-11-12T09:13 | 27,900 | 23,951 | 34 | 81 | 105 | 154 | 154 | 3,424 | 352 | 0 | 583 | 20 | kept pace |
| 2026-11-12T09:14 | 28,089 | 24,223 | 165 | 125 | 136 | 204 | 152 | 3,143 | 378 | 1 | 653 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. Double (families 5–7, desk private node): 200 sompi/gram per hop. Triple (families 8–10, desk private node): 300 sompi/gram per hop. Triple-pub (families 11–13, kept public kaspads): 300 sompi/gram per hop. High (families 14–16, desk private node): 1000 sompi/gram per hop. The rate rides on each hop line to the one builder. Payments pay 150.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 25 (611), 26 (575), 27 (541), 24 (507), 28 (470), 23 (438), 29 (413), 22 (333), 30 (288), 31 (228), 21 (202), 32 (145), and 66 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | Double OK / att / rate rej / full rej / waiting | Triple OK / att / rate rej / full rej / waiting | Triple-pub OK / att / rate rej / full rej / waiting | High OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---|---:|---:|---|
| 2026-11-12T09:11 | 23,934 | 23,934 | 0 | 0 | 0 | 49 / 301 / 0 / 0 / 7 | 77 / 247 / 0 / 0 / 3 | 110 / 255 / 0 / 0 / 3 | 154 / 269 / 0 / 0 / 11 | 142 / 264 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:12 | 23,988 | 23,988 | 0 | 0 | 0 | 75 / 316 / 0 / 0 / 7 | 97 / 258 / 0 / 0 / 3 | 114 / 261 / 0 / 0 / 3 | 157 / 273 / 0 / 0 / 11 | 148 / 282 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:13 | 24,035 | 24,035 | 0 | 0 | 0 | 34 / 301 / 0 / 0 / 7 | 81 / 247 / 0 / 0 / 3 | 105 / 258 / 0 / 0 / 3 | 154 / 271 / 0 / 0 / 11 | 154 / 290 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-12T09:14 | 23,989 | 23,989 | 0 | 0 | 0 | 165 / 364 / 0 / 0 / 7 | 125 / 272 / 0 / 0 / 3 | 135 / 274 / 0 / 0 / 3 | 204 / 278 / 0 / 0 / 11 | 152 / 290 / 0 / 0 / 3 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 11 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 21,600 to 26,400 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits floor, double, triple and high on the desk's private node, which takes no payment submit and which the desk counter reads; triple-pub (11:public-1,12:public-5,13:public-1) reads and submits on kept public kaspads, the payments' nodes.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 621387141 | 48,232 | 0 | 0 | 41 |
| 5 | yes | 621387141 | 47,714 | 0 | 0 | 40 |

## Payment senders

| Sender | Node | Pay submit-OK | Rejects | Minutes with a row |
|---|---:|---:|---:|---:|
| 1.1 | 1 | 16,115 | 0 | 4 of 4 |
| 1.2 | 1 | 16,061 | 0 | 4 of 4 |
| 1.3 | 1 | 16,056 | 0 | 4 of 4 |
| 5.1 | 5 | 16,061 | 0 | 4 of 4 |
| 5.2 | 5 | 15,825 | 0 | 4 of 4 |
| 5.3 | 5 | 15,828 | 0 | 4 of 4 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 323 of 323 | 1397 | 9441 |
| double | 380 of 380 | 1461 | 3604 |
| triple | 464 of 464 | 1292 | 2225 |
| triple-pub | 669 of 669 | 797 | 1840 |
| high | 596 of 596 | 1038 | 1484 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Triple and triple-pub pay the same rate; they differ only in the node a hop is read and submitted on.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Floor in mempool / ready | Double in mempool / ready | Triple in mempool / ready | Triple-pub in mempool / ready | High in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: floor | Template: double | Template: triple | Template: triple-pub | Template: high | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-12T09:11 | 3 | 116 | 183 | 9.52 | 22 | 20 | 16 | 266,219 | 116 | 4 / 4 | 3 / 3 | 3 / 3 | 2 / 2 | 3 / 3 | 54 | 392,227 | 1 | 50 | 0 | 0 | 0 | 0 | 3 | 1 | 388.4 / 181.3 / 114.2 | 228 | 199 |
| 2026-11-12T09:12 | 3 | 63 | 63 | 1.29 | 50 | 50 | 12 | 266,116 | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 0 / 0 | 0 / 0 | 59 | 378,382 | 1 | 0 | 0 | 1 | 3 | 0 | 0 | 42 | 100.0 / 100.0 / 100.0 | 195 | 261 |
| 2026-11-12T09:13 | 3 | 222 | 221 | 10.97 | 23 | 19 | 20 | 265,994 | 185 | 4 / 4 | 3 / 3 | 3 / 3 | 2 / 2 | 3 / 3 | 56 | 391,374 | 1 | 51 | 0 | 0 | 1 | 0 | 3 | 2 | 383.6 / 180.9 / 114.2 | 240 | 223 |
| 2026-11-12T09:14 | 3 | 14 | 14 | 1.17 | 0 | 0 | - | - | 0 | 4 / 4 | 3 / 3 | 3 / 3 | 0 / 0 | 3 / 3 | 11 | 461,481 | 0 | 0 | 1 | 3 | 3 | 0 | 3 | 0 | 100.0 / 100.0 / 100.0 | 176 | 185 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs; its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
