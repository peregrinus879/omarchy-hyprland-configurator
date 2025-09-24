# Omarchy Hyprland Configurator

**Smart Hyprland configuration management with intelligent merging.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-3.0-brightgreen.svg)](https://github.com/peregrinus879/omarchy-hyprland-configurator)

## 🚀 Quick Start

```bash
# Clone the repository
git clone git@github.com:peregrinus879/omarchy-hyprland-configurator.git
cd omarchy-hyprland-configurator

# Add your personal configs to configs/ directory
cp ~/.config/hypr/{bindings,input}.conf configs/

# Run the configurator
chmod +x omarchy-hyprland-config
./omarchy-hyprland-config --sync
```

## 📋 Overview

This tool intelligently manages YOUR Hyprland configurations while preserving omarchy defaults as commented references. It only manages files YOU choose to customize, leaving other omarchy configurations untouched.

### Key Features

- **Smart Merging**: Your settings stay active, omarchy defaults added as comments
- **Selective Management**: Only handles configs YOU add to the repository
- **Automatic Backups**: Preserves last 5 backups before any changes
- **Two-Way Sync**: Push to system or pull from system
- **Clean Diffs**: See what's different between repo and system

## 🎯 Core Concept

Instead of managing ALL Hyprland configs, this tool manages ONLY the ones you customize:

- **Your configs** (e.g., `bindings.conf`, `input.conf`): Fully managed
- **Other omarchy configs** (e.g., `animations.conf`, `colors.conf`): Left untouched

This approach keeps your repository clean and focused on YOUR customizations.

## 🛠️ Commands

```bash
./omarchy-hyprland-config --sync    # Interactive menu (main command)
./omarchy-hyprland-config --status  # Check current status
./omarchy-hyprland-config --backup  # Create manual backup
./omarchy-hyprland-config --help    # Show help
```

### The Sync Menu

Running `--sync` presents three options:

1. **Apply configs + merge** - For fresh installs or after omarchy updates
2. **Pull from system** - Save your edits back to the repository  
3. **Show differences** - Compare repo and system configs

## 📁 Directory Structure

```
omarchy-hyprland-configurator/
├── omarchy-hyprland-config    # The script
├── configs/                   # YOUR config files
│   ├── bindings.conf         # Your key bindings
│   ├── input.conf           # Your input settings
│   └── ...                  # Any other configs you customize
└── README.md                # This file
```

## 🔄 Workflow Examples

### Fresh Install

```bash
# 1. Clone your repository
git clone git@github.com:peregrinus879/omarchy-hyprland-configurator.git
cd omarchy-hyprland-configurator

# 2. Run sync and choose option 1
./omarchy-hyprland-config --sync
# Choose: 1) Apply configs + merge

# Your configs are now active with omarchy defaults as comments!
```

### After Omarchy Updates

```bash
# Omarchy updated the system configs
./omarchy-hyprland-config --sync
# Choose: 1) Apply configs + merge

# Result: Your settings remain active, new omarchy options added as comments
```

### After Editing Configs

```bash
# You edited configs in ~/.config/hypr/
./omarchy-hyprland-config --sync
# Choose: 2) Pull from system

# Your changes are saved to the repository
git add configs/
git commit -m "Updated bindings"
git push
```

## 💡 How Merging Works

When you choose option 1 (Apply + merge), for each of YOUR config files:

```bash
# Your config (active)
bind = SUPER, T, exec, alacritty
bind = SUPER, F, exec, thunar

## ============================================
## OMARCHY DEFAULTS BELOW (for reference)
## Uncomment any you want to use
## ============================================
# bind = SUPER, E, exec, dolphin
# bind = SUPER, TAB, workspace, e+1
```

Your customizations stay active, while omarchy's defaults are visible as comments.

## 🔍 Important Notes

### Personal Configs

The configs in this repository are MY personal Omarchy Hyprland configurations. Before using:

1. **Remove** the example configs
2. **Add** your own customized configs
3. **Run** the configurator

### What Gets Managed

- ✅ Files YOU add to `configs/` directory
- ❌ Other omarchy system configs (left untouched)
- ✅ Automatic backups before changes
- ✅ Smart merging that preserves your choices

### Backup System

- Automatically backs up before changes
- Keeps last 5 backups
- Located in `~/.config/hypr/.backups/`

## 🧩 Requirements

- Hyprland window manager
- Bash 4.0+
- Standard Unix tools (diff, sed, find)
- Git (for version control)

## 📝 Version History

### v3.0 (2025-09-24)
- Complete rewrite with smart merging
- Simplified to 3 main operations
- Fixed loop issues with reliable operations
- Reduced code by 37% while adding features
- Intelligent diff system

### v2.1 (2025-09-23)
- Added symlink support with `--link` command
- Two-way sync with `--sync` command
- Enhanced status display
- Improved backup handling for symlinks
- Better workflow for daily editing

### v2.0 (2025-09-22)
- Dynamic file discovery
- Removed all hardcoded file lists
- Automatic adaptation to any config structure
- Enhanced debug output
- Smart backup/restore system

### v1.0 (2025-09-18)
- Initial release
- Basic configuration management

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch
3. Test your changes thoroughly
4. Submit a pull request

## 📄 License

MIT License - See LICENSE file for details

## 🐛 Troubleshooting

### Configs not applying?
- Check file permissions
- Ensure Hyprland is running
- Run with `--status` to see current state

### Merge not working?
- Verify configs exist in both locations
- Check for syntax errors in configs
- Review backup directory for previous versions

### Manual Operations

```bash
# Manual backup
./omarchy-hyprland-config --backup

# Check differences
./omarchy-hyprland-config --sync
# Choose option 3

# Force reload Hyprland
hyprctl reload
```

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/peregrinus879/omarchy-hyprland-configurator/issues)
- **Discussions**: [GitHub Discussions](https://github.com/peregrinus879/omarchy-hyprland-configurator/discussions)

---

*Smart Hyprland configuration management that respects your choices.* 🚀
