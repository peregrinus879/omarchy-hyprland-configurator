# Omarchy Hyprland Configurator

**Dynamic Hyprland configuration management with automatic backups and zero maintenance.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-2.0-brightgreen.svg)](https://github.com/peregrinus879/omarchy-hyprland-configurator)

## 🚀 Quick Start

```bash
# Clone and run
git clone https://github.com/peregrinus879/omarchy-hyprland-configurator.git
cd omarchy-hyprland-configurator
chmod +x omarchy-hyprland-config

# Complete setup (automatic file discovery)
./omarchy-hyprland-config --setup
```

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
├── omarchy-hyprland-config    # The script (v2.0)
├── configs/
│   ├── bindings.conf         # Your key bindings
│   ├── input.conf            # Input device settings
│   ├── monitors.conf         # Monitor configurations
│   ├── animations.conf       # Add any file - automatically handled!
│   ├── windowrules.conf      # No script changes needed!
│   └── [any_config].conf     # Literally ANY config file works!
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

### Adding New Configuration Files
```bash
# 1. Add any new config to configs/
echo "# My custom config" > configs/custom.conf

# 2. Check status - automatically detected!
./omarchy-hyprland-config --status
# Shows: custom.conf: Not installed

# 3. Install it
./omarchy-hyprland-config --update
# Done! No script editing needed!
```

### Setting Up a New System
```bash
# Clone your configs
git clone https://github.com/YOUR_USERNAME/omarchy-hyprland-configurator.git
cd omarchy-hyprland-configurator

# One command setup - handles any configs in the directory
./omarchy-hyprland-config --setup
```

### Managing Multiple Configs
```bash
# Add 10 new config files to configs/
# Add 50 new config files to configs/
# Add ANY number of files...

# Script handles them all automatically!
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

- **v2.0** (2024-09-22)
  - Complete rewrite with dynamic file discovery
  - Removed hardcoded file lists
  - Automatic adaptation to any config structure
  - Enhanced debug output
  - Smart backup/restore system

- **v1.1** (Previous)
  - Robust error handling
  - Pre-flight validation
  - Static file list management

## 🤝 Contributing

1. Fork the repository
2. Add your configs to `configs/` directory
3. Test with debug mode: `DEBUG=1 ./omarchy-hyprland-config --setup`
4. Submit a pull request

## 📄 License

MIT License - Feel free to use, modify, and distribute.

## 💬 Support

- **Issues**: [GitHub Issues](https://github.com/peregrinus879/omarchy-hyprland-configurator/issues)
- **Discussions**: [GitHub Discussions](https://github.com/peregrinus879/omarchy-hyprland-configurator/discussions)
- **Debug**: Always try `DEBUG=1` mode first

---

**Hyprland configuration management that just works.** No maintenance. No hassle. Just add files and go. 🚀
