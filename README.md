<div align="center">
  <img src="./assets/banner.png" alt="Kaggle MCP Banner" width="800">

  # 🚀 Kaggle MCP for Antigravity

  [![Model Context Protocol](https://img.shields.io/badge/MCP-Protocol-blue?style=for-the-badge)](https://modelcontextprotocol.io)
  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
  [![Awesome MCP](https://img.shields.io/badge/Awesome-MCP-orange?style=for-the-badge)](https://github.com/punkpeye/awesome-mcp-servers)

  **Give your Antigravity AI agent direct access to the world's largest data science community.**

  [Installation](#-installation) • [Features](#-key-features) • [Usage](#-usage--examples) • [Troubleshooting](#-troubleshooting)
</div>

<br/>

## 🌟 Why this matters?
Kaggle is the home of data science. By adding this MCP server to **Antigravity**, your AI agent can now:
- 🔍 **Search** millions of datasets instantly.
- 📊 **Analyze** competition leaderboards.
- � **Read** community kernels for best practices.
- 🚀 **Pull** data directly into your workspace.

---

## ⚡ Quick Start

### 🔑 1. Get your Token (KGAT)
1.  Log in to [Kaggle Settings](https://www.kaggle.com/settings).
2.  Find the **API/MCP** section.
3.  Click **Create New Token** and copy the `KGAT_...` string.

### ⚙️ 2. One-Line Config
Open your `mcp_config.json` and paste this inside `"mcpServers"`:

```json
"kaggle": {
  "command": "npx",
  "args": [
    "mcp-remote",
    "https://www.kaggle.com/mcp",
    "--header",
    "Authorization: Bearer YOUR_TOKEN_HERE"
  ]
}
```

---

## ✨ Key Features
| Feature | Description |
| :--- | :--- |
| **Global Search** | Find datasets, competitions, and notebooks. |
| **Remote Execution** | Run commands against the Kaggle API. |
| **Secure Auth** | Uses Kaggle's official General Access Tokens. |
| **Zero Setup** | Works instantly with `npx` and Antigravity. |

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

## 🚀 Usage & Examples

Once configured, Antigravity becomes your data science assistant. Try these prompts:

> *"Searching for the top 5 most downloaded datasets on Kaggle about Climate Change."*

> *"What are the current top 3 active competitions on Kaggle related to Computer Vision?"*

> *"Find a popular Kaggle notebook that explains Random Forests using Titanic data."*

---

## 🛡️ Best Practices & Security
- **Do not share your `mcp_config.json`**: It contains your private Kaggle token.
- **Rotate keys**: Periodically revoke and regenerate tokens in Kaggle settings.
- **Limit Context**: Only use the Kaggle server when you actually need data science info to save tokens.

---

## 🤝 Contributing
Found a bug or have a suggestion? Open an [issue](https://github.com/msrtarit/Antigravity-Kaggle-MCP-setup-guide/issues)!

---

## ⭐ Support
If you find this guide useful, please **give it a star** to help others find it!

---

<div align="center">
  Made with ❤️ by <a href="https://github.com/msrtarit">msrtarit</a>
</div>
