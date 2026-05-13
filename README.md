# 📂 Project Structure Extractor

A Python tool that scans any project directory and generates a clean, organized view of its folder structure with all files grouped by their directories. Perfect for documentation, project overviews, and sharing codebase structure with teams.

---

## ✨ Features

- 🗂️ **Directory-first organization** - Files grouped under their parent folders
- 🚫 **Smart ignore system** - Built-in ignore lists for Laravel, Node.js, Git, IDE files, and more
- 📊 **Summary statistics** - Total directories and files count
- 💾 **Export to file** - Save output to `.txt` for documentation
- 🎯 **Depth control** - Limit how deep to scan
- ⚡ **Fast execution** - Efficient directory walking
- 🔧 **Customizable** - Add your own ignore patterns

---

## 📦 Requirements

- Python 3.6 or higher
- No external dependencies (uses only standard library)

---

## 🚀 Installation

```bash
# Download the script
wget https://raw.githubusercontent.com/your-repo/project-structure-extractor/main/project_structure.py

# Or clone the repository
git clone https://github.com/your-repo/project-structure-extractor.git
cd project-structure-extractor
```

---

## 📝 Usage

### Basic Usage

```bash
# Scan current directory
python project_structure.py

# Scan specific directory
python project_structure.py "C:/my-project"

# Save output to file
python project_structure.py "C:/my-project" -o structure.txt
```

### Advanced Options

```bash
# Limit depth to 3 levels
python project_structure.py "." -d 3

# Add custom directories to ignore
python project_structure.py "." --ignore-dirs "backup" "old_code" "temp"

# Add custom files to ignore
python project_structure.py "." --ignore-files "test.php" "debug.log" "*.tmp"

# Combine options
python project_structure.py "C:/laravel-project" -o docs/structure.txt -d 5 --ignore-dirs "storage" "tests"
```

---

## 📋 Command Line Arguments

| Argument | Short | Description | Default |
|----------|-------|-------------|---------|
| `directory` | - | Project root directory to scan | `.` (current) |
| `--output` | `-o` | Output file path | Print to console |
| `--format` | `-f` | Output format (`flat`, `tree`, `simple`) | `flat` |
| `--max-depth` | `-d` | Maximum directory depth | Unlimited |
| `--ignore-dirs` | - | Additional directories to ignore | - |
| `--ignore-files` | - | Additional files/patterns to ignore | - |

---

## 📄 Example Output

```
📁 Root/:
    .env.example, artisan, composer.json, package.json, README.md, vite.config.js

📁 app/:
    Helpers>NewSystem.php, OldSystem.php, ResultFunctions.php
    Http>Controllers>AttendanceController.php, BatchesController.php, ...
    Http>Controllers>admin>adminController.php
    Http>Controllers>student>std_controller.php
    Http>Middleware>Authenticate.php
    Models>Student.php, Result.php, Course.php, User.php
    Providers>AppServiceProvider.php

📁 config/:
    app.php, database.php, mail.php, session.php

📁 routes/:
    api.php, web.php, console.php

📁 resources/views/:
    layout>header.blade.php, sidebar.blade.php, navbar.blade.php
    results>all.blade.php, search.blade.php
    admins>index.blade.php, login.blade.php

📁 database/:
    migrations>2025_08_15_041626_create_admins_table.php, ...
    seeders>DatabaseSeeder.php

📁 public/:
    index.php, favicon.ico, robots.txt
    assets>css>style.css
    assets>js>app.js

📊 Total: 45 directories, 280 files
```

---

## 🚫 Default Ignored Items

### Directories
- `vendor/`, `node_modules/` - Package dependencies
- `.git/`, `.idea/`, `.vscode/`, `.nova/` - Version control & IDE settings
- `storage/framework/`, `storage/logs/` - Laravel cache/logs
- `bootstrap/cache/` - Laravel compiled files
- `public/build/`, `public/hot/` - Vite compiled assets
- `__pycache__/`, `__MACOSX/`, `.DS_Store` - OS files

### Files
- `composer.lock`, `package-lock.json` - Lock files
- `.env`, `.env.local`, `.env.production` - Environment files
- `*.log` - Log files
- `*.map` - Source maps
- `*.dev.js` - Development JavaScript
- `*.d.ts` - TypeScript declarations

---

## 🎯 Use Cases

- **Project Documentation** - Include structure in README or wiki
- **Onboarding New Developers** - Quick overview of codebase organization
- **Code Reviews** - Share structure context with reviewers
- **Architecture Discussions** - Visual reference for refactoring
- **Client Deliverables** - Show project organization to clients
- **Audit & Compliance** - Document file organization

---

## 🛠️ Customization

### Adding Custom Ignores via Command Line

```bash
python project_structure.py "." \
    --ignore-dirs "backup" "experiments" "docs" \
    --ignore-files "*.bak" "*.tmp" "test-*.php"
```

### Editing Default Ignores

Open `project_structure.py` and modify the `ignore_dirs` and `ignore_files` lists at the top of the `get_project_structure()` function.

---

## 📊 Supported Project Types

Works with any project structure:
- ✅ **Laravel** (built-in Laravel ignores)
- ✅ **Django / Flask / FastAPI**
- ✅ **Node.js / React / Vue / Angular**
- ✅ **WordPress / Drupal**
- ✅ **Java / Spring Boot**
- ✅ **Any directory on your system**

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👤 Author
**Sabbah Eltaj**
---

## ⭐ Support

If this tool helps you, please consider:
- ⭐ Starring the repository
- 🐛 Reporting issues
- 💡 Suggesting features
- 📢 Sharing with your team

---

## 📋 Changelog

### v1.0.0 (2026-05-13)
- Initial release
- Directory-first file listing
- Smart ignore system for Laravel projects
- Export to file support
- Depth control
- Summary statistics

---
**Made with ❤️ for developers who love clean project documentation**
