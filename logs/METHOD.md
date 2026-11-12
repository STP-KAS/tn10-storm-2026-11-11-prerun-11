# Method, pre-run 11

> This is our own Kaspa Testnet-10 testing. What follows is what we observed in this run, on our own nodes; it is not a claim of how TN10 or Kaspa behave in general.

> Counts only. Desk side. Submit-OK is the desk sender log; included is the desk counter's read of what the desk's private TN10 node accepted on chain. Mini's files are a second read.

Accepted hops per cohort, as the desk's coordinator read them: floor 2,559, double 3,257, triple 4,323, triple-pub 6,073, high 6,139.

Payment submit-OK and included per scored minute:

- BASE: OBSERVATION, submit-OK 0 / 0 / 0 / 0 / 0 / 0 / 0 / 0; our payments included 0 / 0 / 0 / 0 / 0 / 0 / 0 / 0; hops included floor/double/triple/triple-pub/high 1167/1069/1172/1828/1299; counter minutes not kept-pace 0 of 8.
- HOLD-1: MET on submit-OK, submit-OK 23,934 / 23,988 / 24,035 / 23,989; our payments included 24,354 / 23,692 / 23,951 / 24,223; hops included floor/double/triple/triple-pub/high 323/380/465/669/596; counter minutes not kept-pace 0 of 4.
- HOLD-2: MET on submit-OK, submit-OK 42,182 / 41,851 / 41,900 / 41,934; our payments included 41,943 / 41,852 / 41,834 / 41,889; hops included floor/double/triple/triple-pub/high 345/328/402/529/574; counter minutes not kept-pace 0 of 4.
- HOLD-3: MET on submit-OK, submit-OK 61,120 / 60,967 / 60,655 / 60,656; our payments included 60,650 / 60,943 / 60,320 / 61,492; hops included floor/double/triple/triple-pub/high 12/77/192/220/543; counter minutes not kept-pace 0 of 4.
- HOLD-4: OBSERVATION, submit-OK 61,029; our payments included 60,659; hops included floor/double/triple/triple-pub/high 3/17/42/44/135; counter minutes not kept-pace 0 of 1.
- RETURN: OBSERVATION, submit-OK 0 / 0 / 0 / 0 / 0 / 0 / 0 / 0 / 0 / 0; our payments included 0 / 0 / 0 / 0 / 0 / 0 / 0 / 0 / 0 / 0; hops included floor/double/triple/triple-pub/high 231/798/1215/1664/1607; counter minutes not kept-pace 0 of 10.

Decent on the desk side: HOLD-1 met.

## Selection rule, read before the run

The desk node and the kept public kaspads answered serverVersion 2.1.0 at the preflight. In rusty-kaspa tag v2.1.0 (commit 01b532e8b553523216471682649693af92f0fd16), `mining/src/mempool/model/frontier.rs` `build_selector` takes every ready transaction best-first while the ready set's mass fits one block, and otherwise samples at random with weight (fee/mass)^3 (`ALPHA = 3` in `mining/src/mempool/model/frontier/selectors.rs`, weight in `mining/src/mempool/model/frontier/feerate_key.rs`): `sample_inplace` above four blocks' mass, `MutatingTreeSelector` between one and four. Only a transaction with no parent in the mempool is in the ready set (`mining/src/mempool/model/transactions_pool.rs`), so a chained hop is not a candidate until its parent is out of the mempool. Against payments at 150, the weights are 0.30 (100), 2.4 (200), 8 (300) and 296 (1000). A higher fee raises the odds; it does not buy a place in a queue. This is the source's rule, read from the code; the run does not see a miner's template.

Hop rates per hop, one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, double (families 5–7) 200 sompi/gram on the desk's private node, triple (families 8–10) 300 sompi/gram on the desk's private node, triple-pub (families 11–13) 300 sompi/gram on the kept public kaspads, high (families 14–16) 1000 sompi/gram on the desk's private node. Payments 150. The funding coins were not one size, so the fee is not called the whole cause. Triple-pub (11:public-1,12:public-5,13:public-1) was read and submitted on the kept public kaspads; every other cohort on the desk's private TN10 node, which took no payment submit and also ran the counter. Payments: 6 senders, 3 per kept kaspad, 2 unique kaspads, pile 8,400 coins.

## Misses

- none

## Fixes

- none

## On origin

- counts/desk/BASE.md: 2026-11-12T09:10:22Z
- counts/desk/HOLD-1.md: 2026-11-12T09:15:22Z
- counts/desk/HOLD-2.md: 2026-11-12T09:20:22Z
- counts/desk/HOLD-3.md: 2026-11-12T09:25:21Z
- counts/desk/HOLD-4.md: 2026-11-12T09:30:22Z
- counts/desk/RETURN.md: 2026-11-12T09:41:22Z
- counts/chain/TIMELINE.md: 2026-11-12T09:46:33Z
- counts/chain/MEMPOOL.md: 2026-11-12T09:46:36Z
