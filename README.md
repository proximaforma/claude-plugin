![Proxima Forma](assets/proxima-forma-mark-192.png)

# Proxima Forma for Claude

Create and edit persistent, editable designs with Claude on a shared Proxima Forma canvas. Build landing-page concepts, UI mockups and vector artwork; refine existing designs; inspect artboards; respond to feedback; and export SVGs.

[Proxima Forma](https://proximaforma.com) · [MCP documentation](https://proximaforma.com/docs/mcp) · [Support](https://proximaforma.com/support)

## What this plugin includes

- A hosted MCP connection to **https://proximaforma.com/mcp**.
- The **design-with-proxima** skill: read the canvas and references, make scoped edits using current revisions, preserve unrelated artwork, inspect saved artboards and return design or export links.
- The Proxima Forma brand icon and public setup, privacy and support information.

The plugin works with the hosted Proxima Forma service. The application source and infrastructure are maintained separately.

## Connect in Claude

You need a Proxima Forma account and access to the canvas you want to use. Account requirements and any paid service features are described on the [website](https://proximaforma.com).

Until a directory listing is published, you can test the connector directly:

1. Open Claude's settings and add a custom connector named **Proxima Forma**.
2. Enter **https://proximaforma.com/mcp** as the server URL.
3. Use automatic OAuth client registration (DCR). No manually supplied client ID or client secret is needed.
4. Sign in to Proxima Forma, choose the canvas and permissions, approve the connection, and return to Claude.
5. Ask Claude to read the connected canvas.

To test the full plugin in Claude, zip the contents of this repository with `.claude-plugin/plugin.json` at the ZIP root, preserving hidden files. Use **Customize → Plugins → Add → Upload plugin**, then connect Proxima Forma from its Connectors tab. This repository's existence does not mean the plugin has been accepted into Anthropic's directory.

## Use in Claude Code

Install directly from this repository's marketplace:

```text
/plugin install proxima-forma --marketplace proximaforma/claude-plugin
```

Then open `/mcp` to authenticate. To work on a local checkout instead, clone this repository, open its parent directory, and run:

```sh
claude --plugin-dir ./claude-plugin
```

Open `/mcp` to authenticate the Proxima Forma connection. The skill is discovered from the plugin's skills directory.

## Try these prompts

- “Read my connected Proxima Forma canvas and summarize its pages and artboards.”
- “Create an editable landing-page concept in Proxima Forma for a project management app.”
- “Change this artboard's headline to ‘Make room for better ideas’, preserving the rest of the artwork.”
- “Create a second variant of this artboard with a calmer color palette.”
- “Inspect the changed artboard, fix any overflow, and give me an SVG download.”

## Permissions and revocation

**Read** access inspects designs. **Comment** access supports feedback. **Design** access changes artwork and can create canvases. A connection cannot access unrelated private canvases. The account's membership and the connection's scopes both apply.

Revoke an unwanted connection from **Connect agent** in the Proxima Forma workspace. Revocation stops future access; it does not remove data already received by Claude.

## Images, exports and limits

Use supplied assets or editable vector geometry. Existing public HTTPS PNGs can be imported through `upload_image_url`. Local image bytes or self-contained SVGs can use `put_asset` when the host exposes those bytes. The integration does not generate AI images, video or audio, and does not purchase credits or transfer money.

Designs remain editable in Proxima Forma. The full interactive editor opens on the Proxima Forma website; this plugin does not embed the editor inside Claude. SVG export links may expire and can be regenerated.

## Privacy and data handling

This plugin declares one MCP destination: **https://proximaforma.com/mcp**. Tool calls send the canvas IDs, design content, asset inputs or feedback needed for the requested action. Proxima Forma stores account information, designs, assets, comments and activity as described in its [privacy policy](https://proximaforma.com/privacy). Information read by Claude is shared with Anthropic under the user's Claude agreement.

The plugin runs no hooks, local servers, installers or shell commands. It contains no credentials. Claude manages OAuth credentials. URL-based image imports cause the service to fetch the supplied image URL without forwarding account credentials; linked resources may also be requested from their original hosts. The separate Forma assistant in the Proxima Forma website has its own AI provider behavior, described in the service privacy policy.

Workspace data is retained while the service is used unless removed or deletion is requested. Some stored versions and billing records have separate retention rules. See the policy for details or contact **support@proximaforma.com**. Do not include tokens, sign-in codes or private design contents in public GitHub issues.

## Support and publisher

Proxima Forma is operated by **RatioSky LTD**. Contact **support@proximaforma.com** for connection, account, billing, privacy or security issues.

- [Setup and API documentation](https://proximaforma.com/docs/mcp)
- [Support](https://proximaforma.com/support)
- [Privacy policy](https://proximaforma.com/privacy)
- [Terms of service](https://proximaforma.com/terms)
- [Legal notice](https://proximaforma.com/impressum)

Brand assets and trademarks remain the property of their owner. See [branding information](assets/README.md). The plugin configuration, workflow skill and documentation use the [MIT license](LICENSE). Brand assets are excluded from that license; trademark rights are reserved. The hosted service remains governed by its terms of service.
