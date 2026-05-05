# qa-practice-nextjs

A viiibin **practice repo**. Bare Next.js 15 (App Router) + TypeScript +
Tailwind + Turbopack scaffold paired with a [`SPEC.md`](./SPEC.md) describing
exactly what the agent should build.

## Use it

1. Open viiibin → New Project → Import from GitHub
2. Paste: `https://github.com/iii-Partners/qa-practice-nextjs`
3. Once the workspace loads, ask the agent: **"Read SPEC.md and build it."**
4. Watch the preview update with the implemented feature.

## What you get

- Next.js 15 App Router + React 19 + TypeScript (strict)
- Tailwind 4 (via `@import "tailwindcss"` in globals.css)
- Dev server bound to 0.0.0.0:3000 (so viiibin's preview proxy finds it)
- A clean `app/page.tsx` placeholder — no demo content
- A standard `SPEC.md` with strict, parseable acceptance criteria

## Framework gotcha — `"use client"`

Next.js App Router renders components on the server by default. Any component
with state, event handlers (like `onClick`), or browser APIs needs the
`"use client"` directive at the top of the file. The agent should know this;
the SPEC's `click-then-text` assertion will fail if the agent forgets and
wires an `onClick` to a server component.

## Why "practice"?

Part of viiibin's framework validation matrix
([milestone M57](https://github.com/iii-Partners/viiibin/milestone/103)).

## Local sanity check

```bash
npm install
npm run dev    # http://localhost:3000
npm run build  # → .next/
```

## License

MIT — see [LICENSE](./LICENSE).
