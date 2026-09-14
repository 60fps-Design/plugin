# Installing 60fps MCP

60fps is a hosted MCP server. There is nothing to install, build or run locally: you connect to
`https://mcp.60fps.design/mcp` over Streamable HTTP.

## You need a licence key

A 60fps MCP key (https://60fps.design/mcp), or a 60fps PRO key bought on or before 12 Sep 2026.
Without a key the server answers 401. That is expected, not a fault.

## Cline

**Option A, with the UI and sign-in (recommended):**

1. Open the **MCP Servers** icon in Cline, then the **Remote Servers** tab.
2. Server Name: `60fps`. Server URL: `https://mcp.60fps.design/mcp`. Transport: **Streamable HTTP**.
3. Click **Add Server**. If Cline opens the 60fps sign-in page (OAuth 2.1 with dynamic client
   registration), paste your licence key there and approve.

**Option B, with the key in the settings file.** Add this to `cline_mcp_settings.json`, replacing
the placeholder with your licence key:

```json
{
  "mcpServers": {
    "60fps": {
      "type": "streamableHttp",
      "url": "https://mcp.60fps.design/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_60FPS_LICENCE_KEY"
      },
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

## Check it works

Ask: "Use 60fps to find a springy bottom sheet interaction." Cline should call
`60fps_search_shots` and return real iOS shots with their app, gesture and motion. Then ask for
"the motion breakdown for the first one" (`60fps_get_motion_breakdown`) or "the SwiftUI for it"
(`60fps_get_motion_code`).

All six tools are read-only: `60fps_search_shots`, `60fps_list_filters`, `60fps_get_shot`,
`60fps_get_related_shots`, `60fps_get_motion_breakdown`, `60fps_get_motion_code`.
