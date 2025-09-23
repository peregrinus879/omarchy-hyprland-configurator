# Omarchy Hyprland Configurator

**Dynamic Hyprland configuration management with symlink support for live editing.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-2.1-brightgreen.svg)](https://github.com/peregrinus879/omarchy-hyprland-configurator)

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/peregrinus879/omarchy-hyprland-configurator.git
cd omarchy-hyprland-configurator

# IMPORTANT: Replace configs/ with YOUR configurations
rm -rf configs/*
cp ~/.config/hypr/*.conf configs/  # Or add your custom configs

# Run the configurator
chmod +x omarchy-hyprland-config
./omarchy-hyprland-config --setup

# Enable live editing with symlinks (recommended!)
./omarchy-hyprland-config --link
```

## ⚠️ Important Note

This script is designed for **general use** - it will work with ANY Hyprland configuration files. However, the configs in this repository are **my personal Omarchy Hyprland configurations** tailored to my specific setup and preferences.

**Before using:**
1. Download the script
2. **Replace** the `configs/` directory contents with YOUR OWN configuration files
3. Run the configurator to manage your configs

The beauty of v2.0's dynamic discovery is that it works with ANY configuration structure - just add your files and go!

## ✨ What's New in v2.1

### **Symlink Support for Live Editing**
- **`--link` command** creates symlinks instead of copies
- Edit configs anywhere - changes are instant
- No more copying files back and forth
- Perfect for frequent config tweaking

### **Enhanced Sync Features**  
- **`--sync` command** for two-way synchronization
- Pull changes from system or push to system
- Show differences between repo and installed configs
- Works with both copies and symlinks

### **Better Status Display**
- Shows whether files are copied or symlinked
- Visual indicators: ✓ (copied), ↔ (symlinked), ⚠ (different)
- Summary of file states

## ✨ What's New in v2.0

### **Dynamic File Discovery**
- **No configuration needed!** Automatically discovers ALL files in `configs/` directory
- **Zero maintenance** - Add new config files anytime without editing the script
- **Future-proof** - Works with any Hyprland configuration structure
- **Smart backups** - Only backs up files that exist in your system

## 🎯 What It Does

### **Automatic Everything**
- **Discovers** all configuration files in `configs/` directory automatically
- **Validates** source files before making any changes
- **Backs up** existing configurations with timestamps
- **Installs** all discovered configurations to `~/.config/hypr/`
- **Reloads** Hyprland to apply changes immediately

### **Intelligent Management**  
- Dynamic file discovery - no hardcoded file lists
- Compare repository vs installed configurations
- Restore any previous configuration instantly
- Debug mode shows exactly what's happening
- Handles any number of config files automatically

### **Error-Resilient**
- Comprehensive error handling with detailed feedback
- Pre-flight validation prevents failures
- State tracking prevents partial installations
- Never fails silently - always shows what went wrong
- Recovery guidance for any issues

## 📁 How It Works

Simply add ANY Hyprland configuration files to the `configs/` directory:

```
omarchy-hyprland-configurator/
├── omarchy-hyprland-config    # The universal script (v2.0)
├── configs/                   # YOUR config files go here
│   ├── hyprland.conf         # Main configuration
│   ├── bindings.conf         # Key bindings
│   ├── monitors.conf         # Monitor setup
│   └── [any_config].conf     # ANY config file works!
└── README.md                 # This documentation
```

**That's it!** The script automatically discovers and manages ALL files in `configs/`.

## 🛠️ Commands

```bash
./omarchy-hyprland-config --setup         # Complete setup with auto-discovery
./omarchy-hyprland-config --status        # Check all configuration status
./omarchy-hyprland-config --backup        # Create manual backup
./omarchy-hyprland-config --list-backups  # List available backups
./omarchy-hyprland-config --restore <name># Restore from backup
./omarchy-hyprland-config --update        # Update configurations
./omarchy-hyprland-config --help          # Show all commands

# Debug mode (see everything)
DEBUG=1 ./omarchy-hyprland-config --setup
```

## 🔄 Workflow Examples

### Recommended: Live Editing with Symlinks (v2.1)
```bash
# 1. Initial setup
./omarchy-hyprland-config --setup

# 2. Enable symlinks (one time)
./omarchy-hyprland-config --link

# 3. Edit anywhere - changes are instant!
vim ~/.config/hypr/bindings.conf
# The file in configs/ is already updated!

# 4. Commit when ready
git add configs/ && git commit -m "Updated bindings" && git push

# That's it! No manual copying ever needed!
```

### Alternative: Traditional Copy Method

### Setting Up Your Own Configs
```bash
# 1. Clone the script
git clone https://github.com/peregrinus879/omarchy-hyprland-configurator.git
cd omarchy-hyprland-configurator

# 2. Remove my configs, add yours
rm -rf configs/*
cp ~/.config/hypr/*.conf configs/

# 3. Run setup
./omarchy-hyprland-config --setup

# 4. (Optional) Push to your own repository
git add configs/
git commit -m "Add my personal Hyprland configs"
git remote set-url origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push
```

### Adding New Configuration Files
```bash
# 1. Add any new config to configs/
echo "# My custom config" > configs/custom.conf

# 2. Check status - automatically detected!
./omarchy-hyprland-config --status

# 3. Install it
./omarchy-hyprland-config --update
```

### Managing Multiple Configs
```bash
# Add ANY number of files to configs/
# The script handles them all automatically!
./omarchy-hyprland-config --setup
```

## 🎨 Features

✅ **Dynamic Discovery** - Automatically finds all configs in `configs/` directory  
✅ **Zero Configuration** - No script editing ever needed  
✅ **Smart Backups** - Only backs up files that exist  
✅ **Flexible Restore** - Restores exactly what was backed up  
✅ **Debug Mode** - See detailed operations step-by-step  
✅ **State Tracking** - Knows what succeeded/failed  
✅ **Auto-Reload** - Applies changes immediately  
✅ **Universal** - Works with any Hyprland setup  
✅ **Future-Proof** - Adapts to any configuration structure  

## 🏗️ Technical Details

### Architecture (v2.0)
- **Dynamic file discovery** via `get_config_files()` function
- **No hardcoded file lists** - completely flexible
- **Automatic adaptation** to configs directory contents
- **Smart backup system** - backs up only existing files
- **Comprehensive validation** before any changes

### File Management
- **Source**: `configs/` directory (repository)
- **Target**: `~/.config/hypr/` (system)
- **Backups**: `~/.config/hypr/backups/backup_YYYYMMDD_HHMMSS/`
- **Discovery**: Finds all non-hidden files in `configs/`
- **Installation**: Copies all discovered files to target

### Debug Mode
```bash
DEBUG=1 ./omarchy-hyprland-config --setup

# Shows:
# - Files being discovered
# - Validation steps
# - Backup operations
# - Installation progress
# - Detailed error information
```

## 🔧 Requirements

- **Bash** shell (for the script)
- **Hyprland** (optional - configs work when installed later)
- **Standard Unix tools** (cp, find, mkdir)
- **Git** (for cloning the repository)

## 🚦 Troubleshooting

### See What's Happening
```bash
# Check current status
./omarchy-hyprland-config --status

# Run with debug output
DEBUG=1 ./omarchy-hyprland-config --setup
```

### Backup and Restore
```bash
# Manual backup
./omarchy-hyprland-config --backup

# List all backups
./omarchy-hyprland-config --list-backups

# Restore specific backup
./omarchy-hyprland-config --restore backup_20241218_143022
```

### Common Solutions

| Issue | Solution |
|-------|----------|
| No files found | Add config files to `configs/` directory |
| Permission denied | Run `chmod +x omarchy-hyprland-config` |
| Hyprland not reloading | Manual reload: `hyprctl reload` |
| Need to see operations | Use `DEBUG=1` mode |

## 📝 Version History

- **v2.1** (2025-09-23)
  - Added symlink support with `--link` command
  - Two-way sync with `--sync` command  
  - Enhanced status display
  - Improved backup handling for symlinks
  - Better workflow for daily editing

- **v2.0** (2025-09-22)
  - Complete rewrite with dynamic file discovery
  - Removed all hardcoded file lists
  - Automatic adaptation to any config structure
  - Enhanced debug output
  - Smart backup/restore system
  - Zero maintenance design

- **v1.0** (2025-09-18)
  - Initial release
  - Basic configuration management
  - Static file list approach

## 🤝 Contributing

1. Fork the repository
2. Replace configs with your own
3. Test with debug mode: `DEBUG=1 ./omarchy-hyprland-config --setup`
4. Submit improvements to the script (not configs)

## 📄 License

MIT License - The script is free to use, modify, and distribute.

## 💬 Support

- **Issues**: [GitHub Issues](https://github.com/peregrinus879/omarchy-hyprland-configurator/issues)
- **Discussions**: [GitHub Discussions](https://github.com/peregrinus879/omarchy-hyprland-configurator/discussions)
- **Debug**: Always try `DEBUG=1` mode first

---

**Universal Hyprland configuration management that just works.** Replace configs with yours. No maintenance. No hassle. 🚀
