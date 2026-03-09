# 🚀 Kaggle MCP Setup for Antigravity

[![Model Context Protocol](https://img.shields.io/badge/MCP-Protocol-blue)](https://modelcontextprotocol.io)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A simple, clear guide to integrating the **Kaggle MCP Server** with **Antigravity**. This allows your AI agent to browse datasets, search kernels, and interact with Kaggle's vast data science ecosystem directly.

---

## 🛠 Prerequisites

- An active [Kaggle](https://www.kaggle.com) account.
- [Antigravity](https://github.com/google/antigravity) (or any compatible MCP host) installed.
- [Node.js](https://nodejs.org/) (for `npx`).

---

## 🔑 1. Generate Your Kaggle Access Token

The Kaggle MCP server uses a **General Access Token (KGAT)**.

1.  Log in to [Kaggle](https://www.kaggle.com).
2.  Go to your **Account Settings** ([kaggle.com/settings](https://www.kaggle.com/settings)).
3.  Scroll down to the **API** or **MCP** section.
4.  Generate a new token. It will look like `KGAT_xxxxxxxxxxxxxxxxxxxxxxxxxxx`.

---

## ⚙️ 2. Edit Your Config

Locate your `mcp_config.json` file. This is typically found at:
- **Windows**: `%USERPROFILE%\.gemini\antigravity\mcp_config.json`
- **macOS/Linux**: `~/.gemini/antigravity/mcp_config.json`

Add the following configuration to the `mcpServers` object:

```json
{
  "mcpServers": {
    "kaggle": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://www.kaggle.com/mcp",
        "--header",
        "Authorization: Bearer YOUR_KGAT_TOKEN"
      ],
      "disabled": false
    }
  }
}
```

> [!CAUTION]
> Replace `YOUR_KGAT_TOKEN` with your actual token. Never commit this file to a public repository!

---

## 🚀 3. Usage & Testing

Restart Antigravity and try a prompt like:

> *"Searching for the top 5 most downloaded datasets on Kaggle about Climate Change."*

---

## ⚖️ License

Distributed under the **MIT License**. See `LICENSE` for more information.

---

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request
