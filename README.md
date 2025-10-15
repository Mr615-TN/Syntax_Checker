# 🧩 Syntax Checker
A **fast, parallel syntax checking CLI tool** written in Rust 🦀 — for developers who want to quickly validate source code syntax across multiple programming languages.

---

## ⚡ Overview
`syntax_checker` recursively scans directories for supported source files and checks each file's syntax **in parallel** for blazing-fast results.

It does *not* execute any code — it simply verifies syntax safely and efficiently.

---

## ✨ Features
- ⚡ **Parallel Processing** — Checks multiple files simultaneously for maximum speed
- 🔒 **Safe** — Never executes code, only validates syntax
- 🎯 **Selective** — Automatically detects and checks only supported file types
- 📊 **Clear Output** — Color-coded results with detailed error messages
- 🚀 **Zero Config** — Works out of the box with sensible defaults

---

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

---

## 📋 Prerequisites
Before using `syntax_checker`, ensure you have the relevant language tools installed:

- **Rust**: `rustc` (comes with Rust installation)
- **Python**: `python3`
- **C++**: `g++` or `clang`
- **Java**: `javac` (JDK)
- **JavaScript**: `node`
- **TypeScript**: `tsc` (install via `npm install -g typescript`)
- **Go**: `go`

> **Note**: Only the tools for languages you want to check need to be installed.

---

## 🚀 Installation

### Install directly from GitHub:
```bash
cargo install --git https://github.com/Mr615-TN/Syntax_Checker
```

### Or clone and build manually:
```bash
git clone https://github.com/Mr615-TN/Syntax_Checker
cd Syntax_Checker
cargo build --release
```

### Optionally make it globally available:
```bash
sudo cp target/release/syntax_checker /usr/local/bin
```

---

## 📖 Usage

### Basic Usage
```bash
# Check current directory
syntax_checker .

# Check specific directory
syntax_checker /path/to/project

# Check from parent directory
syntax_checker ..
```

### Example Output
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

### Exit Codes
- `0` — All files passed syntax checks
- `1` — One or more files have syntax errors

---

## 📊 Performance
Designed for speed! Checks hundreds of files in seconds using parallel processing.

*(Performance varies based on hardware, file complexity, and number of files)*

---

## ⚠️ Limitations
- Requires language-specific compilers/interpreters to be installed
- TypeScript checking requires a `tsconfig.json` in the project (create one with `tsc --init`)
- Does not check semantic errors, only syntax
- Go builds may create temporary files despite `/dev/null` output

---

## 🔧 Troubleshooting

### "Command not found" errors
Ensure the relevant compiler/interpreter is installed and in your PATH:
```bash
# Check what's installed
which rustc python3 g++ javac node tsc go
```

### TypeScript "Cannot find tsconfig.json"
Create a basic config:
```bash
tsc --init
```

### Permission denied on installation
Use `sudo` for system-wide installation or install to a user directory.

---

## 🤝 Contributing
Contributions are welcome! To add support for a new language:

1. Fork the repository
2. Add the language detection in `src/main.rs`
3. Implement the syntax check command
4. Update this README
5. Submit a pull request

### Running Tests
```bash
cargo test
```

---

## 📄 License
This project is licensed under the [GNU General Public License v3.0](LICENSE) - see the LICENSE file for details.

---

## 👤 Author
**Mr615-TN**
- GitHub: [@Mr615-TN](https://github.com/Mr615-TN)

---

⭐ **Star this repo if you find it useful!**