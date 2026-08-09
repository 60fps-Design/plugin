# 60fps for Cursor

Describe the motion you want. Get back a real iOS clip that does it, and a SwiftUI file that
recreates it.

The library holds 2,000+ interaction clips from apps that shipped. Each one comes with a written
breakdown of its motion: the start state, the transition, the end state, and the timing and easing
behind it. Use it instead of guessing numbers.

## What you get

| Tool | What it does |
|---|---|
| `60fps_search_shots` | Semantic search. Describe the motion, not keywords. |
| `60fps_get_shot` | One shot in full, with keyframes. |
| `60fps_get_motion_breakdown` | Start, transition, end, plus timing and easing. |
| `60fps_get_motion_code` | A self-contained SwiftUI file for that shot. |
| `60fps_get_related_shots` | For when the first pick is close but not right. |

There is also a `motion-reference` skill. It tells the agent when to use the library and when to
leave it alone.

## Install

Install from the Cursor marketplace, or from the Customize panel. The server is hosted, so there is
nothing to run. Signing in opens OAuth in your browser.

You need a [60fps PRO](https://60fps.design/pro) licence. Without one the tools connect but return a
401. That is intended, not a fault.

## What it covers

iOS only, and motion only.

It will not help with Android, Material, Flutter, React Native or web. It will not design icons,
palettes, logos or brands. It has nothing to do with frame-rate profiling, which shares the name and
nothing else. The skill tells the agent to answer those directly instead of searching.

Search always returns something, because it ranks the whole library by closeness. Judge the results
on their merits, not on how many were searched.

## About the code

Each file is standalone. Paste it into Xcode and run it.

It carries none of the original app's words, colours, branding or assets, by design. Restyle it to
your own design system. The motion is the part worth keeping.

## Links

- [60fps.design/mcp](https://60fps.design/mcp)
- [Privacy](https://60fps.design/privacy) and [Terms](https://60fps.design/terms)

`mcp.60fps.design` sets no cookies and runs no analytics. It makes exactly one outbound third-party
request, for storyboard frames from Framer's image CDN, and sends nothing about the caller.

## Licence

MIT, for this repository only: the manifest, the skill text and the logo.

It does not license the 60fps library, the hosted service, or the clips and code they return. Those
stay under the [terms](https://60fps.design/terms).
