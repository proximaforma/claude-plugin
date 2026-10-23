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
| Publisher / operator | Proxima Forma / Agentikus LTD |
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

A dedicated Anthropic reviewer account has been provisioned with editor access to four existing sample projects. Production password sign-in and access to all four projects were verified on 2026-10-22; no unrelated projects were visible. Supply its credentials and login instructions only in Anthropic's private reviewer-access fields. Do not publish the account identity, password, tokens or private project links in this repository.

Verify that a reviewer can complete the Proxima Forma sign-in and Claude OAuth flow with that account before submission. Use a disposable sample canvas for write tests so the baseline examples remain usable.

## Known test status — 2026-10-23

The owner confirmed that end-to-end testing is complete on 2026-10-23. This records the owner's confirmation. Production password sign-in and editor access to all four reviewer sample projects were separately verified on 2026-10-22, with no unrelated projects visible.

Supply the dedicated review account and connection instructions privately in the portal. Use a disposable sample canvas for reviewer write tests so the baseline examples remain usable.

## Data-handling answers to verify before submission

- This is a first-party Proxima Forma integration operated by Agentikus LTD.
- Tool inputs and returned design data may contain personal information supplied by users.
- The plugin's declared MCP destination is the Proxima Forma endpoint. URL imports and externally linked resources may contact the hosts supplied by users.
- Storage, hosting, retention and deletion are covered by the public privacy policy. Do not claim the service never stores data or never uses subprocessors.
- This connector creates editable designs; it does not expose AI image/video/audio generation or financial transactions.
- The owner confirmed on 2026-10-23 that the intended audience includes under-18 users. The service terms exclude children under 13 and require parental or guardian authorization and supervision where users cannot independently enter the agreement. Answer the portal’s under-18 question Yes.
- The authorized developer must complete the directory policy and legal acknowledgements.

## Local structure validation

With Claude Code installed, run from the repository root:

```sh
claude plugin validate . --strict
```

Anthropic's portal performs additional listing and security checks. A local pass is not approval.

Official guidance: [Publishing](https://claude.com/docs/directory/publish), [plugin submission](https://claude.com/docs/plugins/submit), [connector submission](https://claude.com/docs/connectors/building/submission).
