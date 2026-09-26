# Foundry MCP Server

A Model Context Protocol server for interacting with Foundry.
It allows AI assistants to interact with datasets, ontology objects and functions.

## Tools 🌟

- list datasets
- query datasets
- list ontology objects
- query ontology objects
- list functions
- execute functions


## Prerequisites 

* Python 3.9+
* mcp
* pyarrow
* pandas
* foundry-platform-sdk

# Environment Variables 🌍

The server requires few configuration variables to run:

| Variable            | Description                                             | Requirement                    |
|---------------------|---------------------------------------------------------|--------------------------------|
| `FOUNDRY_HOSTNAME` | Hostname of your Foundry instance                       | Required                       |
| `TOKEN`            | User token generated from your profile                  | Use this or client credentials |
| `CLIENT_ID`        | Service user created in the developer console           | Required if TOKEN is unset     |
| `CLIENT_SECRET`    | Secret associated with the service user                 | Required if TOKEN is unset     |
| `SCOPES`           | OAuth scopes                                             | Optional                       |
| `ONTOLOGY_ID`      | Your ontology ID                                         | Required                       |

* Set `TOKEN`, or set both `CLIENT_ID` and `CLIENT_SECRET` for OAuth client authentication. When `TOKEN` is set, it takes precedence.

## Usage

### uv 

first you need to clone the repository and add the config to your app

``` json
{
  "mcpServers": {
    "foundry": {
      "command": "uv",
      "args": [
        "--directory", 
        "<path_to_mcp_server>",
        "run",
        "mcp-server-foundry"
      ],
      "env": {
        "FOUNDRY_HOSTNAME": "<hostname>",
        "TOKEN": "<token>",
        "CLIENT_ID": "<client_id>",
        "CLIENT_SECRET": "<client_secret>",
        "SCOPES": "<scopes>",
        "ONTOLOGY_ID": "<ontology_id>"
      }
    }
  }
}
```

## Development

To run the server in development mode:

```bash
# Clone the repository
git clone git@github.com:qwert666/mcp-server-foundry.git

# Run the server
npx @modelcontextprotocol/inspector uv --directory /path/to/mcp-foundry-server run mcp-server-foundry
```

# Contributing
- Fork the repository
- Create your feature branch (git checkout -b feature/amazing-feature)
- Commit your changes (git commit -m 'Add some amazing feature')
- Push to the branch (git push origin feature/amazing-feature)
- Open a Pull Request

# License  📜

MIT License - see LICENSE file for details
