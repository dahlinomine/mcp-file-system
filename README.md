# MCP File System

![mcp](https://img.shields.io/badge/mcp-blue?style=flat-square) ![fs](https://img.shields.io/badge/fs-blue?style=flat-square) ![security](https://img.shields.io/badge/security-blue?style=flat-square)

A standard MCP server for secure, scoped file system access for AI agents.

## Overview
MCP File System provides a Model Context Protocol (MCP) compliant interface that allows LLMs to interact with the local file system under strict security constraints. It acts as a bridge, enabling AI agents to read, write, and manage files within explicitly defined directories while preventing unauthorized access to the rest of the host machine.

## Features
*   **Path Scoping:** Restrict agent access to specific "allow-listed" directories to ensure data privacy.
*   **Standardized CRUD:** Full support for reading, writing, moving, and deleting files via MCP tool calls.
*   **Metadata Inspection:** Retrieve file stats, directory listings, and permissions without full file reads.
*   **Python-Native:** Built using the official MCP Python SDK for high performance and easy integration.

## Installation
Clone the repository and install the necessary dependencies using pip:

```bash
git clone https://github.com/yourusername/mcp-file-system.git
cd mcp-file-system
pip install -r requirements.txt
```

## Usage
Start the MCP server by running the main entry point. You must provide the root directory you wish to expose to the AI agent.

```bash
python main.py --root-dir /path/to/safe/workspace
```

Example integration in a `config.json` for an MCP client:
```json
{
  "mcpServers": {
    "filesystem": {
      "command": "python",
      "args": ["/path/to/mcp-file-system/main.py", "--root-dir", "./data"]
    }
  }
}
```

## Contributing
Contributions are welcome! Please submit a Pull Request with a clear description of your changes. Ensure your code adheres to standard Python PEP 8 styling and includes updates to documentation where necessary.

## License
This project is licensed under the [MIT License](LICENSE).