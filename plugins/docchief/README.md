# DocChief

<img src="assets/logo.svg" alt="DocChief" width="120">

Skills for querying and reporting on corporate records health: get fundraising-ready as a
founder, or run diligence on a target as an investor.

Connect Cursor to DocChief's corporate vault or investment datarooms: surface missing
approvals and conflicting terms, approaching deadlines and maturity dates, stale
certificates, and equity and governance gaps. Trace document relationships and look up who
holds which rights, with evidence linked to every finding. Generate board updates, investor
reports, and portfolio reports for LPs from the same record.

Built for founders getting fundraising ready and reporting to their stakeholders, for VC,
PE, and M&A teams finding risks early and focusing resources where they matter, and for
ongoing portfolio health checks.

## Prerequisites

Requires a DocChief account at [my.docchief.ai](https://my.docchief.ai), and at least one
dataroom that you either created or were invited to by its owner. Signing in alone is not
enough — a user with no dataroom of their own and no invitation can complete the connection
but will read nothing. The assistant sees exactly what that person's own DocChief account
opens: a full dataroom for its owner or only the documents an invited member was given.

## Install

### From the Cursor Marketplace

Search for **DocChief** in the Cursor Marketplace and install the plugin.

### From the xAI plugin marketplace (Grok Build)

Search for **DocChief** in the Grok Build plugin marketplace and install the plugin. The
Grok manifest is `.grok-plugin/plugin.json`. It declares the same server URL and no
credentials.

### By hand (Cursor)

Add this to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "docchief": {
      "url": "https://mcp.docchief.ai/mcp"
    }
  }
}
```

## Sign in

You do not need to copy a token. The first time Cursor connects, it opens your browser.
Sign in to DocChief and approve access for Cursor. The access token lasts one hour, and
the server also issues a refresh token, so Cursor can get a new access token without
asking you to sign in again.

The server uses OAuth with PKCE and dynamic client registration. Cursor finds the
sign-in endpoints from `https://mcp.docchief.ai/.well-known/oauth-protected-resource`.

To remove access, delete the `docchief` server in Cursor's MCP settings.

## Tools

| Tool | What it does |
|------|--------------|
| `list_spaces` | Lists the datarooms you can read, with your role in each. |
| `get_space_vocabulary` | Returns the filter values that exist in a dataroom: document categories, event types, party roles. |
| `search_documents` | Finds documents by type, party, role or event. |
| `semantic_search` | Natural-language search over document text. Returns passages with page numbers. |
| `get_document_summary` | Returns the short AI summary of one document. |
| `get_document` | Returns everything the classifier extracted from one document. |
| `get_extracted_text` | Returns the extracted text of selected pages of one document. |
| `get_document_view_link` | Returns a link that opens the document in the DocChief viewer. |
| `list_space_parties` | Lists the people and companies named in a dataroom, with their roles. |
| `list_space_events` | Lists dated events such as issuances, appointments, grants and transfers. |
| `list_space_relationships` | Lists relationships between parties, such as shareholdings and board seats. |
| `list_watches` | Lists the health checks on a dataroom and whether each one has been generated. |
| `get_watch_section` | Returns the Cap Table Health Check findings for one subject. |
| `get_docchief_updates` | Returns DocChief product news and tips. |
| `send_feedback_to_docchief` | Sends your feedback or a bug report to the DocChief team. The agent calls it only when you ask. |

`send_feedback_to_docchief` is the only tool that writes anything. Every other tool
only reads.

## Support

- Contact: [contact@docchief.ai](mailto:contact@docchief.ai)
- Documentation: [docchief.ai/docs](https://docchief.ai/docs)
- Privacy policy: [docchief.ai/privacy](https://docchief.ai/privacy)
