# Tester & Red Team

**A free methodology for testing whether your product actually works — and whether your AI agent
can be tricked into doing something it shouldn't.**

Two independent tools, each a complete methodology you hand to an AI coding agent (Claude Code,
Cursor, or similar) as a prompt. No installation, no shared backend, no account, no dependency on
any company's infrastructure. Bring your own model API key and your own product's URL.

| | What it answers | Who runs it |
|---|---|---|
| **[Naive Tester](./naive-tester.md)** | "Would a real human actually get through my product, and would they buy it?" | Point it at a live URL. It plays a human persona and writes a candid report. |
| **[Red Team](./red-team.md)** | "Can my AI agent be tricked into leaking data, running an unauthorised action, or ignoring its own rules?" | Point it at your agent's prompt/endpoint. It runs adversarial probes and scores the result. |

## Why this exists

Most product testing either never happens (founders are too close to their own product to see it
the way a stranger would) or is outsourced to a tool that needs its own account, its own backend,
and your product's data flowing through someone else's infrastructure. This is neither: it's a
**methodology**, not a product — a detailed brief you give an AI coding agent you already use, and
it does the work using your own model key against your own URL. Nothing about your product leaves
your own tooling.

It was built and proven internally across a real portfolio of live products before being stripped
down to this portable form, specifically so it could be handed to founders with no strings
attached.

## Quickstart

**To run a naive-tester pass:**

1. Open [`naive-tester.md`](./naive-tester.md), pick (or let the picker choose) a persona.
2. Give your AI coding agent the "Execution protocol" block, filled in with your product's URL,
   goal, and your own standards checklist.
3. Read the report it writes. Expect friction points, terminology nitpicks, and "Opportunity:"
   suggestions — not a bug list.

**To run a red-team pass:**

1. Open [`red-team.md`](./red-team.md).
2. Write a handful of probes on the `Probe` shape — start from the seven starter probes, then add
   a few that exploit specific knowledge of *your* product (the highest-signal probes always do).
3. If your agent can take actions (send email, change a record, call a tool), also write
   `EffectProbe`s — the response text is the wrong instrument for an authorisation question; only
   a before/after snapshot tells you whether something actually happened.
4. **Before running any effect probe, the safety guard must prove your test identity is
   synthetic.** This is not optional — see the guard in `red-team.md`.

## What you need

- Your own model API key (any provider your agent already uses).
- A function that calls your model.
- For red-team effect probes: a synthetic/test account you can prove is synthetic.

## What you don't need

- Any package, registry, or shared service from any specific company's infrastructure.
- An account with us, or anyone.
- Your product's data to touch anyone else's systems. The whole run is local to your own agent
  and your own URL.

## License

[MIT](./LICENSE) — use it, modify it, build on it, commercially or not.
