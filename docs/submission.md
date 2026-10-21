# Anthropic directory submission

This repository is the standalone plugin package. It contains no application backend, infrastructure source, account secrets or reviewer credentials.

## Listing fields

| Field | Value |
| --- | --- |
| Name | Proxima Forma |
| Identifier | proxima-forma |
| One-liner | Create and edit persistent, editable designs with Claude on a shared Proxima Forma canvas. |
| Website | https://proximaforma.com |
| MCP endpoint | https://proximaforma.com/mcp |
| Authentication | OAuth with dynamic client registration; no manually supplied client secret |
| Documentation | https://proximaforma.com/docs/mcp |
| Privacy | https://proximaforma.com/privacy |
| Terms | https://proximaforma.com/terms |
| Support | https://proximaforma.com/support |
| Contact | support@proximaforma.com |
| Publisher / operator | Proxima Forma / RatioSky LTD |
| Plugin repository | https://github.com/proximaforma/claude-plugin |
| Plugin path | Repository root (leave the portal's optional path empty) |
| Tracked branch | main |
| Use cases | Read designs, create editable UI concepts, refine artwork, inspect artboards, discuss feedback, export SVGs |

## Suggested listing description

Proxima Forma gives Claude access to an editable design canvas shared with people and other agents. Read existing pages, artboards and references; create landing-page concepts and UI mockups; refine text, layout and vector artwork; inspect results; and export designs as SVGs. The bundled skill helps Claude work with current canvas revisions and preserve unrelated artwork. Sign in with a Proxima Forma account and approve read, comment or design access. Open saved work in the Proxima Forma editor to continue editing.

## Submission sequence

1. Use the Claude organization that should own the listings long term and connect a GitHub account with push access to this repository.
2. At https://claude.ai/directory/manage, submit the remote server first as an **MCP connector** using the exact endpoint above.
3. Provide the listing icon, public links, data-handling answers and populated reviewer-account access in the private portal. Never commit reviewer credentials here.
4. Submit this repository as a **Plugin bundle**, with its root as the plugin folder and `main` as the tracked branch.
5. Keep the connector and bundle in the same Claude organization and use the identical MCP URL so they can be paired.
6. Run portal validation for the exact commit, address findings, submit and track review. This document is preparation, not evidence of an accepted or published listing.

## Reviewer access

The owner confirmed that the existing OpenAI reviewer account already has access to sample projects. Reuse that populated account and its approved sample projects for Anthropic review; a new account is not required. Enter its existing credentials and login instructions only in Anthropic's private reviewer-access fields. Do not publish the account identity, password, tokens or private project links in this repository.

Verify that a reviewer can complete the Proxima Forma sign-in and Claude OAuth flow with that account before submission. Use a disposable sample canvas for write tests so the baseline examples remain usable.

## Known test status — 2026-10-22

The owner confirmed that Claude can authenticate and read the connected canvas. Creation, editing, image imports, inspection, comments, exports, permission denials, renewal and revocation still need explicit end-to-end confirmation in Claude. Do not mark all tools tested based only on authentication and reading.

Before making submission attestations, exercise every exposed tool in MCP Inspector and Claude as required by Anthropic's checklist, and test each surface claimed in the listing. Use a disposable populated reviewer canvas for write tests.

## Data-handling answers to verify before submission

- This is a first-party Proxima Forma integration operated by RatioSky LTD.
- Tool inputs and returned design data may contain personal information supplied by users.
- The plugin's declared MCP destination is the Proxima Forma endpoint. URL imports and externally linked resources may contact the hosts supplied by users.
- Storage, hosting, retention and deletion are covered by the public privacy policy. Do not claim the service never stores data or never uses subprocessors.
- This connector creates editable designs; it does not expose AI image/video/audio generation or financial transactions.
- Confirm the intended age audience and policy acknowledgements from the product owner's actual policies. Do not infer or pre-accept these for the owner.

## Local structure validation

With Claude Code installed, run from the repository root:

```sh
claude plugin validate . --strict
```

Anthropic's portal performs additional listing and security checks. A local pass is not approval.

Official guidance: [Publishing](https://claude.com/docs/directory/publish), [plugin submission](https://claude.com/docs/plugins/submit), [connector submission](https://claude.com/docs/connectors/building/submission).
