# 🌦️ Weather MCP Server

A modular, async-enabled weather server powered by the [National Weather Service API](https://www.weather.gov/documentation/services-web-api) and [FastMCP](https://github.com/minimaxir/mcp). Built using the `uv` Python toolchain for fast and modern development.

---

## 📦 Project Overview

This project provides:

- 🔔 **Weather alerts** by U.S. state.
- 🌤️ **Forecast data** by latitude/longitude.

Built on `httpx` for async HTTP requests and `FastMCP` for exposing modular tools via CLI or agent interfaces.

---

## 🛠️ Getting Started

### 🧰 Prerequisites

- Python ≥ 3.13
- [`uv`](https://github.com/astral-sh/uv) installed (`pip install uv`)

### 🧑‍💻 Setup

```bash
# Create and enter the project directory
uv init weather
mv weather weather-mcp-server
cd weather-mcp-server

# Create virtual environment and activate it
uv venv
.venv\Scripts\activate  # On Windows
# or
source .venv/bin/activate  # On Unix

# Add dependencies
uv add mcp[cli] httpx

# Create your server file
touch weather.py  # or use new-item on PowerShell
````

---

## 🚀 Usage

### Run the MCP server

```bash
python weather.py
```

### Available Tools

#### 🔹 Get Active Weather Alerts

```bash
mcp run weather get_alerts --state TX
```

#### 🔹 Get Forecast for Coordinates

```bash
mcp run weather get_forecast --latitude 34.05 --longitude -118.25
```

> Returns next 5 periods of weather forecast for Los Angeles, CA.

---

## 📁 Project Structure

```
weather-mcp-server/
├── .venv/                 # Virtual environment (created by uv venv)
├── pyproject.toml         # Project config and dependencies
├── weather.py             # MCP server with tools
└── README.md              # Project documentation
```

---

## ⚙️ Tools Used

* [FastMCP](https://github.com/minimaxir/mcp) — Modular Command Platform framework
* [httpx](https://www.python-httpx.org/) — Async HTTP client
* [uv](https://github.com/astral-sh/uv) — Fast, modern Python packaging and workflow

---

## 📄 License

This project is licensed under the MIT License. See [`LICENSE`](LICENSE) for details.

