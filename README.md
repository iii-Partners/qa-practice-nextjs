# qa-practice-nextjs

A viiibin **practice repo**. Bare Next.js (App Router) + TypeScript +
Tailwind scaffold paired with a [`SPEC.md`](./SPEC.md) describing exactly
what the agent should build.

## Stack

- Next.js **14.2.35** + React **18.3.1** + Tailwind **3.4**
- App Router + TypeScript (strict)
- Dev server on `0.0.0.0:3000`

## Why Next 14, not Next 15?

E2B's official Next.js template ([`e2b-dev/fragments`](https://github.com/e2b-dev/fragments))
and their docs at <https://e2b.mintlify.app/docs/template/examples/nextjs.md>
both pin to Next 14. Next 15 + React 19 + RSC streaming has a documented
incompatibility with E2B's preview tunnel — React hydration silently fails
because the tunnel does not preserve the progressive-flush streaming that
RSC depends on. Tracked in [viiibin#1181](https://github.com/iii-Partners/viiibin/issues/1181)
and E2B [#539](https://github.com/e2b-dev/E2B/issues/539).

When E2B ships tunnel support for Next 15 + RSC, this repo bumps. Until
then, Next 14 LTS is the canonical stack for "Next.js works in viiibin
end-to-end."

## Use it

1. Open viiibin → New Project → Import from GitHub
2. Paste: `https://github.com/iii-Partners/qa-practice-nextjs`
3. Once the workspace loads, ask the agent: **"Read SPEC.md and build it."**

## Framework gotcha — `"use client"`

App Router renders components on the server by default. Components with
event handlers (`onClick`) need `"use client"` at the top of the file.

## Local sanity check

```bash
npm install
npm run dev    # http://localhost:3000
npm run build  # → .next/
```

## License

MIT — see [LICENSE](./LICENSE).
