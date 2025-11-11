
<!-- markdownlint-disable -->
<p align="center">
      <img src="https://raw.githubusercontent.com/the-lupaxa-test-org/branding/main/logos/test/logo.png" alt="Project Logo" width="256"/>
    <br />
    <a href="#">
        <img src="https://img.shields.io/github/actions/workflow/status/CICDToolbox/shellcheck/cicd.yml?branch=master&label=build%20status&style=for-the-badge" alt="Github Build Status" />
    </a>
    <a href="#">
        <img src="https://img.shields.io/github/license/CICDToolbox/shellcheck?color=blue&label=License&style=for-the-badge" alt="License">
    </a>
    <a href="#">
        <img src="https://img.shields.io/github/created-at/CICDToolbox/shellcheck?color=blue&label=Created&style=for-the-badge" alt="Created">
    </a>
    <br />
    <a href="#">
        <img src="https://img.shields.io/github/v/release/CICDToolbox/shellcheck?color=blue&label=Latest%20Release&style=for-the-badge" alt="Release">
    </a>
    <a href="#">
        <img src="https://img.shields.io/github/release-date/CICDToolbox/shellcheck?color=blue&label=Released&style=for-the-badge" alt="Released">
    </a>
    <a href="#">
        <img src="https://img.shields.io/github/commits-since/CICDToolbox/shellcheck/latest.svg?color=blue&style=for-the-badge" alt="Commits since release">
    </a>
    <br />
    <a href="https://github.com/templabs/.github/blob/master/CODE_OF_CONDUCT.md">
        <img src="https://img.shields.io/badge/Code%20of%20Conduct-blue?style=for-the-badge" />
    </a>
    <a href="https://github.com/templabs/.github/blob/master/.github/CONTRIBUTING.md">
        <img src="https://img.shields.io/badge/Contributing-blue?style=for-the-badge" />
    </a>
    <a href="https://github.com/templabs/.github/blob/master/.github/SECURITY.md">
        <img src="https://img.shields.io/badge/Report%20Security%20Concern-blue?style=for-the-badge" />
    </a>
    <a href="">
        <img src="https://img.shields.io/badge/Get%20Support-blue?style=for-the-badge" />
    </a>
</p>

<h1 align="center">🧠 SmartCache</h1>

> A fast, lightweight, and extensible in-memory caching library for Python — built for developers who care about performance, transparency, and testability.

---

## ✨ Overview

**SmartCache** is a simple but powerful caching utility that lets you cache expensive function calls or arbitrary data structures in-memory with time-to-live (TTL), size limits, and optional persistence.  
It’s ideal for data pipelines, microservices, and CLI tools that need a zero-dependency, drop-in cache mechanism.

✅ Lightweight – pure Python, no external dependencies  
✅ Transparent – decorators and explicit cache objects both supported  
✅ Flexible – TTL, size limit, auto-eviction, and statistics  
✅ Tested – 100% test coverage with type hints and linting  
✅ Safe – thread-safe design for concurrent access  

---

## 🚀 Installation

```bash
pip install smartcache

Or install from source:

git clone https://github.com/wolfsoftware/smartcache.git
cd smartcache
pip install .
```

⸻

🧩 Quick Start

Example 1 — Decorator Usage

```python
from smartcache import cache

@cache(ttl=60)
def slow_function(x):
    print("Computing...")
    return x * 2

print(slow_function(10))  # First call — computes
print(slow_function(10))  # Cached result
```

Example 2 — Manual Cache Object

```python
from smartcache import Cache

cache = Cache(max_items=100, ttl=30)

cache.set("user_123", {"name": "Alice", "role": "admin"})
print(cache.get("user_123"))
```

⸻

⚙️ Configuration Options

Parameter	Type	Default	Description
ttl	int	None	Time (in seconds) before cache entry expires.
max_items	int	None	Maximum number of items before eviction.
persist	bool	False	Whether to persist cache to disk on shutdown.
serializer	object	pickle	Serializer to use for persistence.


⸻

🧪 Running Tests

Run the full test suite (requires pytest):

pytest -v

Lint the code (requires ruff):

ruff check smartcache


⸻

📦 Project Structure

smartcache/
├── __init__.py
├── core.py
├── decorators.py
├── exceptions.py
├── utils.py
tests/
├── test_cache.py
├── test_decorator.py
LICENSE
README.md
pyproject.toml


⸻

🧠 Design Philosophy

SmartCache follows Security by Design and Simplicity First principles:
	•	Transparent – cache logic should be explicit and easy to test.
	•	Predictable – TTL, eviction, and persistence behave consistently.
	•	Composable – can be safely embedded into larger frameworks.
	•	Secure – no unsafe deserialization or code execution paths.

⸻

📚 API Reference (Excerpt)

Cache

Cache(max_items: Optional[int] = None, ttl: Optional[int] = None, persist: bool = False)

Methods

Method	Description
get(key)	Retrieve an item or None if expired or missing.
set(key, value)	Store a value with optional TTL override.
delete(key)	Remove an item from cache.
clear()	Remove all cached items.
stats()	Return cache hit/miss metrics.


⸻

🧑‍💻 Contributing

Contributions are welcome! Please:
	1.	Fork this repository.
	2.	Create a feature branch (git checkout -b feature/my-feature).
	3.	Commit your changes with clear messages.
	4.	Submit a pull request with a detailed description.

All contributions must pass:
	•	Linting: ruff check .
	•	Type checks: mypy smartcache
	•	Tests: pytest

Please see CONTRIBUTING.md￼ for details.

⸻

🛡️ Security

If you discover a vulnerability, please do not open a public issue.
Instead, email: security@wolfsoftware.com￼

⸻

🧾 License

Licensed under the MIT License￼.
Copyright © 2025 Wolf Software Limited￼

⸻

🌍 Links & Resources
	•	📦 PyPI: smartcache￼
	•	🧭 Documentation￼
	•	🧰 Related Tools￼
	•	💬 Discussions￼

