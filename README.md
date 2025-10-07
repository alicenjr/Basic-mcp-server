# Basic MCP Server 🎲

A simple Model Context Protocol (MCP) server implementation using FastMCP, featuring utility tools for dice rolling and basic arithmetic operations.

## 📋 Overview

This project demonstrates a basic MCP server implementation that exposes tools for AI assistants to interact with. Built with [FastMCP](https://github.com/jlowin/fastmcp), it provides a clean and straightforward example of how to create custom tools that can be used by Claude and other AI assistants.

## ✨ Features

- 🎲 **Dice Rolling Tool**: Roll multiple 6-sided dice
- ➕ **Number Addition Tool**: Add two numbers together
- 🚀 **FastMCP Framework**: Built on the efficient FastMCP library
- 🐍 **Python 3.11+**: Modern Python implementation

## 🛠️ Available Tools

### `roll_dice(n_dice: int = 1) -> list[int]`
Rolls n_dice 6-sided dice and returns the results as a list.

**Parameters:**
- `n_dice` (int, optional): Number of dice to roll. Defaults to 1.

**Returns:**
- `list[int]`: List of dice results (values between 1-6)

**Example:**
```python
roll_dice(3)  # Returns something like [4, 2, 6]
```

### `add_numbers(a: float, b: float) -> float`
Adds two numbers together and returns the result.

**Parameters:**
- `a` (float): First number
- `b` (float): Second number

**Returns:**
- `float`: Sum of a and b

**Example:**
```python
add_numbers(5.5, 3.2)  # Returns 8.7
```

## 🚀 Getting Started

### Prerequisites

- Python 3.11 or higher
- [uv](https://github.com/astral-sh/uv) package manager (recommended) or pip

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/alicenjr/Basic-mcp-server.git
cd Basic-mcp-server
```

2. **Install dependencies:**

Using `uv` (recommended):
```bash
uv sync
```

Or using `pip`:
```bash
pip install fastmcp>=2.12.4
```

### Running the Server

**Using uv:**
```bash
uv run python main.py
```

**Using python directly:**
```bash
python main.py
```

The MCP server will start and be ready to accept connections from compatible AI assistants.

## 📁 Project Structure

```
Basic-mcp-server/
│
├── main.py              # Main MCP server implementation
├── pyproject.toml       # Project metadata and dependencies
├── uv.lock             # Lock file for reproducible builds
├── .python-version     # Python version specification (3.11)
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## 🔧 Configuration

The server is configured in `pyproject.toml`:

```toml
[project]
name = "expense-tracker-mcp-server"
version = "0.1.0"
requires-python = ">=3.11"
dependencies = ["fastmcp>=2.12.4"]
```

## 🔌 Using with Claude Desktop

To use this MCP server with Claude Desktop, add it to your Claude configuration:

1. Locate your Claude config file
2. Add the server configuration:

```json
{
  "mcpServers": {
    "basic-mcp-server": {
      "command": "uv",
      "args": ["run", "python", "/path/to/Basic-mcp-server/main.py"]
    }
  }
}
```

3. Restart Claude Desktop

## 🎯 Extending the Server

To add new tools, simply use the `@mcp.tool` decorator:

```python
@mcp.tool
def your_tool_name(param1: type, param2: type) -> return_type:
    """Clear description of what your tool does"""
    # Your implementation here
    return result
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📚 Resources

- [FastMCP Documentation](https://github.com/jlowin/fastmcp)
- [Model Context Protocol Specification](https://modelcontextprotocol.io/)
- [Claude Desktop MCP Guide](https://docs.anthropic.com/claude/docs/mcp)

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 👤 Author

**alicenjr**
- GitHub: [@alicenjr](https://github.com/alicenjr)
- Email: hniraj51@gmail.com
- Bio: AI Engineer | Computer Vision, Automation & Microservices

## 🙏 Acknowledgments

- Thanks to the FastMCP team for the excellent framework
- Inspired by the Model Context Protocol specification
- Built with ❤️ for the AI community

## 📞 Support

If you encounter any issues or have questions:
- Open an [issue](https://github.com/alicenjr/Basic-mcp-server/issues)
- Check the [FastMCP documentation](https://github.com/jlowin/fastmcp)

---

⭐ If you find this project useful, please consider giving it a star on GitHub!
