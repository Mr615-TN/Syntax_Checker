# 🧩 Syntax Checker

A **fast, parallel syntax checking CLI tool** written in Rust 🦀 — for developers who want to quickly validate source code syntax across multiple programming languages.

***

## ⚡ Overview

`syntax_checker` recursively scans directories for supported source files and checks each file’s syntax **in parallel** for blazing-fast results.
It does *not* execute any code — it simply verifies syntax safely and efficiently.

***

## 🛠️ Supported Languages

| Language | File Extension | Command Used |
| :----------- | :-------------- | :-------------- |
| 🦀 **Rust** | `.rs` | `rustc --emit=metadata` |
| 🐍 **Python** | `.py` | `python3 -m py_compile` |
| 💻 **C++** | `.cpp`, `.cc`, `.cxx` | `g++ -fsyntax-only` |
| ☕ **Java** | `.java` | `javac -Xlint:all` |
| 🌐 **JavaScript** | `.js` | `node --check` |
| 🔷 **TypeScript** | `.ts` | `tsc --noEmit` |
| 🐹 **Go** | `.go` | `go build -o /dev/null` |

***

## 🚀 Installation

You can install directly from this GitHub repository:

```bash
cargo install --git [https://github.com/Mr615-TN/Syntax_Checker](https://github.com/Mr615-TN/Syntax_Checker)
```
### Or Clone and build manually:

```bash
git clone [https://github.com/Mr615-TN/Syntax_Checker](https://github.com/Mr615-TN/Syntax_Checker)
cd Syntax_Checker
cargo build --release
```
### Optionally make it globally available:

```bash
sudo cp target/release/syntax_checker /usr/local/bin
```
## Usage

```bash
syntax_checker [path/to/directory]
```

### Example Output: 

```
🔍 Found 8 files. Checking in parallel...

🐍 Checking Python syntax: ./src/test_script.py
💻 Checking C++ syntax: ./src/engine.cpp
☕ Checking Java syntax: ./src/Main.java
🦀 Checking Rust syntax: ./src/main.rs
✅ ./src/test_script.py — Syntax OK
✅ ./src/engine.cpp — Syntax OK
❌ ./src/Main.java — Syntax Error (line 42: missing semicolon)
```
