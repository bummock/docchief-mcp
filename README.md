# DocChief MCP for Cursor

<img src="assets/logo.svg" alt="DocChief" width="120">

Connect Cursor to [DocChief](https://docchief.ai) so the agent can search, read and
answer questions about the documents in your data rooms.

This repository contains only the Cursor plugin manifest and the MCP configuration.
The server itself runs at `https://mcp.docchief.ai/mcp`. No code from this repository
runs on your machine.

## What you can do

- Find documents by type, by the parties they name, or by the events they record.
- Search the text of your documents in natural language and get passages with page numbers.
- Read a document's summary, its extracted text, or the full structured record the
  classifier produced.
- List the people and companies in a data room, the dated events, and the relationships
  between parties (shareholdings, board seats, employment, lending).
- Read the findings of the Cap Table Health Check.
- Get a link that opens a document in the DocChief viewer.

The agent sees exactly what your DocChief account can see. If you can read only some
documents in a space, the agent can read only those documents too.

## Install

### From the Cursor Marketplace

Search for **DocChief** in the Cursor Marketplace and install the plugin.

### By hand

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
| `list_spaces` | Lists the spaces (data rooms) you can read, with your role in each. |
| `get_space_vocabulary` | Returns the filter values that exist in a space: document categories, event types, party roles. |
| `search_documents` | Finds documents by type, party, role or event. |
| `semantic_search` | Natural-language search over document text. Returns passages with page numbers. |
| `get_document_summary` | Returns the short AI summary of one document. |
| `get_document` | Returns everything the classifier extracted from one document. |
| `get_extracted_text` | Returns the extracted text of selected pages of one document. |
| `get_document_view_link` | Returns a link that opens the document in the DocChief viewer. |
| `list_space_parties` | Lists the people and companies named in a space, with their roles. |
| `list_space_events` | Lists dated events such as issuances, appointments, grants and transfers. |
| `list_space_relationships` | Lists relationships between parties, such as shareholdings and board seats. |
| `list_watches` | Lists the health checks on a space and whether each one has been generated. |
| `get_watch_section` | Returns the Cap Table Health Check findings for one subject. |
| `get_docchief_updates` | Returns DocChief product news and tips. |
| `send_feedback_to_docchief` | Sends your feedback or a bug report to the DocChief team. The agent calls it only when you ask. |

`send_feedback_to_docchief` is the only tool that writes anything. Every other tool
only reads.

## Requirements

- A DocChief account. Sign up at [docchief.ai](https://docchief.ai).
- Cursor with MCP support.

## License

[MIT](LICENSE)
