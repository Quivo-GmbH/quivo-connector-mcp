<img src="assets/quivo-icon.png" alt="Quivo" width="96" height="96">

# Quivo Connector MCP server

This MCP (Model Context Protocol) server connects AI tools such as GitHub Copilot, Claude, ChatGPT and Cursor to your [Quivo Connector](https://quivo.co) account. You ask in plain words, for example "How much stock do I have of SKU TSHIRT-BLUE-M?", and the AI tool looks up or changes the data for you.

Quivo hosts the server, so there is nothing to run yourself. This repository holds only this description.

## What you can do

- Look up orders, shipments, returns, products and stock.
- With Full access, also create or change data, such as an order or an inbound, and book shipments.

The AI tool acts as you. It sees the same data as you do in the Connector web app and can do only what your Connector role allows.

## Before you start

- A Quivo Connector account. You sign in with your usual Connector login; there is no separate sign-up.
- An authenticator app if you sign in with a username and password, or Google if you linked it in the Connector web app. If an integration uses the same username and password for the API, read [Sign in](https://api-docs.quivo.co/mcp-server/sign-in-and-access#sign-in) first.
- A Quivo package that includes access through AI tools. If yours does not, the sign-in page tells you.
- An AI tool that supports remote MCP servers over Streamable HTTP with OAuth sign-in.

## Set it up in VS Code

[Install in VS Code](https://vscode.dev/redirect?url=vscode%3Amcp%2Finstall%3F%257B%2522name%2522%253A%2522quivo-connector%2522%252C%2522type%2522%253A%2522http%2522%252C%2522url%2522%253A%2522https%253A%252F%252Fmcp.quivo.co%252Fmcp%2522%257D), or add the server to `.vscode/mcp.json`:

```json
{
  "servers": {
    "quivo-connector": { "type": "http", "url": "https://mcp.quivo.co/mcp" }
  }
}
```

Select **Start** above the server entry and sign in in the browser window that opens. You need no API key.

For Claude, ChatGPT, Cursor and other AI tools, see [Connect your AI tool](https://api-docs.quivo.co/mcp-server/connect).

## Choose your access level

When you sign in, you choose what the AI tool may do:

- **Read only** (the default): it can only look up your data.
- **Full access**: it can also create, change, book, cancel and delete. Some AI tools or plans allow only reading.

To end access, open **MCP Server** in the Connector web app, then **Manage connected AI tools**, and select **Revoke**.

## Example prompts

- "Show me the details of order 100234."
- "List the orders I created this week."
- "Create an inbound for 200 units of SKU TSHIRT-BLUE-M arriving next Monday." (needs Full access)

## Before you approve a change

AI tools can make mistakes. Most of them ask you before they change data, but depending on their settings they may act without asking. Check what the AI tool is about to do, especially bookings and cancellations, and approve only changes you asked for. If you only need to look things up, connect with Read only.

## Help

- Full guide: [api-docs.quivo.co/mcp-server/overview](https://api-docs.quivo.co/mcp-server/overview)
- Troubleshooting: [api-docs.quivo.co/mcp-server/troubleshooting](https://api-docs.quivo.co/mcp-server/troubleshooting)
- Support: [support.quivo.co](https://support.quivo.co/)
- Security problems: security@quivo.co
- [Privacy policy](https://quivo.co/en/privacy/) and [Terms and Conditions](https://quivo.co/en/conditions/)

Issues and pull requests here are not monitored. Please use the links above.
