# DocChief MCP plugin

<img src="plugins/docchief/assets/logo.svg" alt="DocChief" width="120">

Skills for querying and reporting on corporate records health: get fundraising-ready as a
founder, or run diligence on a target as an investor.

This repository holds the DocChief plugin for the Cursor Marketplace and the xAI plugin
marketplace (Grok Build). It contains only the plugin manifests and the MCP configuration.
The MCP server runs at `https://mcp.docchief.ai/mcp`, and no code from this repository
runs on your machine.

See [plugins/docchief/README.md](plugins/docchief/README.md) for what the plugin does, the
prerequisites, install steps and the tool list.

## Listings

| Directory | Submission | Pinned commit |
|-----------|------------|---------------|
| xAI plugin marketplace (Grok Build) | [xai-org/plugin-marketplace#1013](https://github.com/xai-org/plugin-marketplace/pull/1013) | `a958270` |

The xAI entry pins one commit of this repository. A change here does not reach Grok
users until a new PR to `xai-org/plugin-marketplace` bumps the `sha` to a newer commit.

## Layout

This repository follows the structure of
[cursor/plugin-template](https://github.com/cursor/plugin-template):

| Path | Purpose |
|------|---------|
| `.cursor-plugin/marketplace.json` | Marketplace manifest. Lists the plugins in this repository. |
| `plugins/docchief/.cursor-plugin/plugin.json` | Plugin manifest: name, description, author, license, logo. |
| `plugins/docchief/.grok-plugin/plugin.json` | Grok Build manifest. Declares the MCP server inline, URL only. |
| `plugins/docchief/mcp.json` | MCP server definition. Only the server URL, no credentials. |
| `plugins/docchief/assets/logo.svg` | Logo shown in the marketplace. |
| `scripts/validate-template.mjs` | The template's validator. |

## Validate

```bash
node scripts/validate-template.mjs
```

## Contributing

Pull requests can be opened by collaborators on this repository. Changes to `main` need
approval from a code owner (see `.github/CODEOWNERS`).

## Support

- Contact: [contact@docchief.ai](mailto:contact@docchief.ai)
- Documentation: [docchief.ai/docs](https://docchief.ai/docs)
- Privacy policy: [docchief.ai/privacy](https://docchief.ai/privacy)

## License

[MIT](LICENSE)
