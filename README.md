# simple-loader

A simple Python library for loading and accessing configuration from `.env`, `.json`, and `.yaml` files — all in one place.

---

## 🌟 Features

- ✅ Load `.env`, `.json`, and `.yaml` config files with a single function
- ✅ Access `.env` variables like `os.getenv()`
- ✅ Unified and clean API for config management
- ✅ Minimal dependency: just `python-dotenv` and `PyYAML`

---

## 📦 Installation

```bash
pip install simpleloader
```

---

## 🛠 Usage

### 📁 Example files

```env
# .env
USERNAME=env_user
API_KEY=env_key_123
```

```json
// config.json
{
  "database": {
    "host": "localhost",
    "port": 5432
  },
  "debug": true
}
```

```yaml
# config.yaml
server:
  host: "0.0.0.0"
  port: 8000
logging:
  level: "info"
```

---

### 🧪 Python code

```python
import simpleloader

simpleloader.load(
    envFile=".env",
    jsonFile="config.json",
    yamlFile="config.yaml"
)

print(simpleloader.get_env("USERNAME"))                      # → env_user
print(simpleloader.get_json()["database"]["host"])           # → localhost
print(simpleloader.get_yaml()["server"]["port"])             # → 8000
```

---

## 📘 API

### `load(envFile=None, jsonFile=None, yamlFile=None)`

Load config files. Each argument is optional.

* `envFile` – Path to `.env` file
* `jsonFile` – Path to `.json` file
* `yamlFile` – Path to `.yaml` or `.yml` file

---

### `get_env(key: str, fallback: Any = None)`

Get a variable from the `.env` file (or environment), with optional fallback.

---

### `get_json() -> dict`

Returns the loaded JSON config as a dictionary.

---

### `get_yaml() -> dict`

Returns the loaded YAML config as a dictionary.

---

## 🧾 License

MIT © 2025 redbean0721

---

## 💡 Future Plans

* [ ] Add `get("section.key")` unified access across all config types
* [ ] Support config priority / overrides
* [ ] Add support for `.toml` files
