# Omarchy Hyprland Configurator

**Complete Hyprland configuration management with automatic backups.**

One script handles everything from validation to installation with robust error handling.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0-brightgreen.svg)](https://github.com/YOUR_USERNAME/omarchy-hyprland-configurator)

## Quick Start

```bash
# Clone and run
git clone https://github.com/YOUR_USERNAME/omarchy-hyprland-configurator.git
cd omarchy-hyprland-configurator
chmod +x omarchy-hyprland-config

# Complete setup (robust)
./omarchy-hyprland-config --setup
```

## What It Does

🔧 **Complete Setup**
- **Validates everything FIRST** (never gets stuck or fails silently)
- Installs optimized Hyprland configurations (`bindings.conf`, `input.conf`, `monitors.conf`)
- **Creates backups FIRST** (never loses your existing settings)
- Handles errors gracefully - essential validation prevents all failures

⚡ **Automatic Management**  
- Pre-flight validation ensures clean installation
- Safe installation with timestamped backups
- Compare repository vs installed configurations
- Restore any previous configuration instantly
- Debug mode shows exactly what's happening

🛡️ **Error-Resilient**
- Comprehensive error handling with detailed feedback
- Debug mode for troubleshooting (`DEBUG=1`)
- State tracking prevents partial installations
- Never fails silently - always shows what went wrong
- Recovery guidance for any issues

## Commands

```bash
./omarchy-hyprland-config --setup         # Complete robust setup
./omarchy-hyprland-config --status        # Check configuration status
./omarchy-hyprland-config --backup        # Create manual backup
./omarchy-hyprland-config --list-backups  # List available backups
./omarchy-hyprland-config --restore <n>   # Restore from backup
./omarchy-hyprland-config --update        # Update configurations
./omarchy-hyprland-config --help          # Show all commands

# Debug mode (shows exactly what happens)
DEBUG=1 ./omarchy-hyprland-config --setup
```

## Setup Process

### For New Systems
1. **Clone and setup**: `./omarchy-hyprland-config --setup`
   - ✅ **Validates source files exist** (prevents all common failures)
   - ✅ **Creates backup of existing configurations** (never loses settings)
   - ✅ **Installs optimized configurations** (professional setup)
   - ✅ **Reloads Hyprland automatically** (changes active immediately)
   
2. **Enjoy your optimized setup**: 
   - Professional key bindings for window management
   - Optimized input device settings
   - Multi-monitor configurations ready
   - Everything backed up and restorable
   
3. **Done!** Your Hyprland is now optimized and reliable

### For New PCs/Laptops
```bash
git clone https://github.com/YOUR_USERNAME/omarchy-hyprland-configurator.git
cd omarchy-hyprland-configurator
./omarchy-hyprland-config --setup
# Setup complete! Configurations active immediately
```

## Features

✅ **Complete Setup** - Pre-flight validation prevents all common failures  
✅ **Error-Resilient** - Never fails silently, always shows what went wrong  
✅ **Debug Mode** - See exactly what the script is doing step-by-step  
✅ **Instant Backup** - Timestamped backups before any changes  
✅ **State Tracking** - Knows what operations succeeded/failed  
✅ **Auto-Reload** - Hyprland configuration reloaded automatically  
✅ **Comprehensive Validation** - Checks everything before making changes  
✅ **User-Friendly** - Clear instructions and colored output with debug info  
✅ **Smart Recovery** - Detailed guidance when things go wrong  

## Robust Design

### Setup Flow (v1.0)
1. **Pre-flight validation** (checks all source files exist - prevents failures)
2. **Check dependencies** (verifies Hyprland installation)
3. **Create directories** (ensures proper structure)
4. **Backup existing configs FIRST** (ensures complete safety)
5. **Install configurations** (copies optimized settings)
6. **Reload Hyprland** (applies changes immediately)

### Error Handling
- Setup never proceeds without validation - prevents all common failures
- Debug mode shows exact operations and file paths
- Clear error messages with specific recovery instructions
- State tracking prevents partial installations
- Smart status reporting based on actual system state
- Automatic Hyprland reload with graceful fallback

### Debug Mode
```bash
# See exactly what the script is doing
DEBUG=1 ./omarchy-hyprland-config --setup

# Shows:
# - File path validation
# - Backup operations
# - Installation steps
# - Error details
```

## Requirements

- **Hyprland** window manager (or configs ready for when installed)
- **Bash** shell (for the management script)
- **Standard Unix tools** (cp, find, cmp)
- **Repository structure** with `configs/` directory containing your files

## Technical Details

### Configuration Files Managed
- `~/.config/hypr/bindings.conf` - Professional key bindings and shortcuts
- `~/.config/hypr/input.conf` - Input device settings (mouse, keyboard, touchpad)  
- `~/.config/hypr/monitors.conf` - Monitor setup and multi-display configuration

### Integration
- Source directory: `configs/` (in repository)
- Backup directory: `~/.config/hypr/backups/`
- Timestamped backups: `backup_YYYYMMDD_HHMMSS/`
- Automatic Hyprland reload via `hyprctl reload`
- File comparison for update detection
- Debug logging for troubleshooting

### Version History
- **v1.0** - Initial release with pre-flight validation and comprehensive error handling

## Troubleshooting

### Check Status
```bash
./omarchy-hyprland-config --status
```

### Debug Mode (See Everything)
```bash
DEBUG=1 ./omarchy-hyprland-config --setup
```

### Create Manual Backup
```bash
./omarchy-hyprland-config --backup
```

### List All Backups
```bash
./omarchy-hyprland-config --list-backups
```

### Restore Previous Configuration
```bash
# See available backups
./omarchy-hyprland-config --list-backups

# Restore specific backup
./omarchy-hyprland-config --restore backup_20241218_143022
```

### Common Issues

**Pre-flight validation fails**: Missing files in `configs/` directory - add them first

**Backup directory issues**: Script creates directories automatically with proper permissions

**Configuration not applying**: Hyprland reloads automatically, but manual restart may help

**Script behavior unclear**: Use `DEBUG=1` mode to see exactly what's happening

## Configuration Details

### Bindings (`bindings.conf`)
- Professional window management shortcuts
- Application launchers and workspace controls
- System controls (volume, brightness, etc.)
- Optimized workflow enhancements

### Input (`input.conf`)  
- Mouse sensitivity and acceleration
- Keyboard layout and repeat settings
- Touchpad gestures and scrolling
- Natural input behavior

### Monitors (`monitors.conf`)
- Multi-monitor setup optimization
- Resolution and refresh rate settings
- Positioning and orientation
- Workspace assignments

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your configuration improvements
4. Test thoroughly with debug mode
5. Submit a pull request

## Repository Structure

```
omarchy-hyprland-configurator/
├── omarchy-hyprland-config    # The reliable solution
├── configs/
│   ├── bindings.conf         # Professional key bindings
│   ├── input.conf            # Input device settings
│   └── monitors.conf         # Monitor configurations
└── README.md                 # This documentation
```

## License

MIT License - Feel free to use, modify, and distribute.

## Support

- **Issues**: Use GitHub Issues for bug reports (include debug output)
- **Discussions**: Use GitHub Discussions for questions
- **Documentation**: This README covers all functionality
- **Debug**: Always try `DEBUG=1` mode first for troubleshooting

---

**Hyprland configuration should be simple and reliable. This tool makes it so.**
