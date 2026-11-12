> **Experimental. We are just trying this.** [Disclaimer](../../DISCLAIMER.md) · Kaspa Testnet-10 only. No key, id, address, host, or port in these files.

# Desk runner, pre-run 11

Pre-run 10's runner, counter and senders, with two pre-run 11 changes (lock lines (xii) and (xiii) in [locks/LOCKED.md](../../locks/LOCKED.md)).

- `mempool-probe.mjs` (new, read-only): every 20 s on the desk's private node, `getInfo`, `getFeeEstimate`, `getMempoolEntries` and `getBlockTemplate` (never submitted); on each kept public kaspad, `getInfo` and `getFeeEstimate`. It sorts the mempool into our payments, our hops by cohort and other traffic, counts what is ready (no parent in the mempool), sums the mass the selector uses (the larger of compute and storage mass), buckets other traffic by fee rate, and matches the template's transactions to mempool entries by their first input. One JSON line per read, counts only. It holds no key and submits nothing; no sender reads its file. Before the open the same file is run by hand with `--out mempool-preopen.jsonl --log probe-preopen.log --stop PREOPEN-STOP`.
- `desk-runner.mjs`: starts the probe before the counter and stops it with the counter after the tail; steps BASE (families only, 8 whole minutes, observation), HOLD-1 400, HOLD-2 700, HOLD-3 1,013 (scored, at least four minutes evaluated), 1,013 kept to the HOLD-4 minute, then RETURN at 0 (families only, 10 whole minutes, observation). Each step file carries a mempool table; after the tail it writes `counts/chain/TIMELINE.md`, `counts/chain/MEMPOOL.md` and `logs/METHOD.md`. Everything else is pre-run 10's.
- `counter.mjs`, `pay2.mjs`, `paypool.mjs`, `preflight.mjs`: pre-run 10's, unchanged.

The family sender is kit19, unchanged from pre-run 9; it stays on the desk ([tools/sixteen/kit19-public-path.patch](../sixteen/kit19-public-path.patch)).

Everything earlier runners did stays: one runner, detached children, unique kaspads, three senders per kaspad, the fair deal and the handoff repair, git retries with a local FAILED file, never restarted mid-run.
