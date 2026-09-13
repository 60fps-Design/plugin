# 60fps

[![60fps MCP on Glama: tool definition quality and endpoint health](https://glama.ai/mcp/connectors/design.60fps/library/badges/score.svg)](https://glama.ai/mcp/connectors/design.60fps/library)
[![smithery badge](https://smithery.ai/badge/pyxelapps/MCP-60fps)](https://smithery.ai/servers/pyxelapps/MCP-60fps)

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

The server is hosted, so there is nothing to run locally. Signing in opens OAuth in your browser.

- **Cursor**: install from the marketplace, or from the Customize panel.
- **Grok Build**: install from the plugin marketplace.
- **Claude Code**: add this repo as a marketplace, then install the plugin.

  ```
  /plugin marketplace add 60fps-Design/plugin
  /plugin install 60fps@60fps-design
  ```

  Or skip the plugin and add only the server:
  `claude mcp add --transport http 60fps https://mcp.60fps.design/mcp`
- **Anything else that speaks MCP**: point it at `https://mcp.60fps.design/mcp` over streamable
  HTTP. See [mcp.json](mcp.json).

You need a 60fps licence key: a [60fps MCP](https://60fps.design/mcp) key, or a
[60fps PRO](https://60fps.design/pro) key bought on or before 12 Sep 2026. PRO bought after that date
does not include the MCP. Without a key the tools connect but return a 401. That is intended, not a
fault.

## Use it with Xcode

Xcode 26.3 and later ship their own MCP server, so an agent can drive the build system, the
Simulator, Previews and the debugger. Point that agent at 60fps at the same time and the loop closes:
it finds a real interaction, reads the motion breakdown, writes the SwiftUI, builds it, and looks at
the result.

Xcode launches the agent for you, with its own tools already wired in:

```bash
xcrun mcpbridge run-agent claude
```

Anything you have installed in that agent comes along, so with this plugin the session has both
toolsets. A prompt like "find how Threads does pull to refresh, then build it in this project and
show me the Preview" is one agent turn rather than three tools and a copy and paste.

`xcrun mcpbridge --help` lists the rest, including `--no-xcode-tools` to leave Xcode's tools out and
`run-agent skills export` to dump the skills Xcode ships. The bridge needs Xcode open on a project,
and agent access enabled in Xcode's settings, before it will hand anything over.

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

MIT, for this repository only: the manifests, the skill text and the logo.

It does not license the 60fps library, the hosted service, or the clips and code they return. Those
stay under the [terms](https://60fps.design/terms).
