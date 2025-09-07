# Android Config Scripts

This repository contains Android device management scripts that work with rooted devices or devices with Shizuku access.

## Does this work?

**YES!** ✅ All scripts are functional and properly configured.

## Scripts Overview

### Core Scripts

- **`rish`** - Shizuku shell access script for privilege escalation
- **`enable`** - Enables Android system packages and apps
- **`disable`** - Disables Android system packages and apps  
- **`clear`** - Clears data for Android packages
- **`delete`** - Removes common Android directories from storage

### Configuration Files

- **`bashrc`** - Shell aliases for convenience
- **`rish_shizuku.dex`** - Required DEX file for Shizuku functionality

### Backup Files

- **`3c_DMData.1dmbak`** - Device Manager backup data
- **`3c_NewPipeData.zip`** - NewPipe application backup
- **`3c_settings.zip`** - Android settings backup

## Usage

### Prerequisites

1. **Rooted Android device** OR **Shizuku installed and activated**
2. **Terminal app** (like Termux) with shell access
3. Copy these scripts to your device (e.g., `/sdcard/`)

### Using with Shizuku

1. Install [Shizuku](https://shizuku.rikka.app/) on your Android device
2. Activate Shizuku (via ADB or root)
3. Copy `rish` and `rish_shizuku.dex` to the same directory
4. Run scripts using: `./rish ./enable` or `./rish ./disable`

### Direct Usage (Root Required)

If you have root access, you can run the scripts directly:
```bash
# Enable all packages
./enable

# Disable packages (for debloating)
./disable

# Clear app data
./clear

# Clean storage directories
./delete
```

### Shell Aliases

Source the bashrc file to get convenient aliases:
```bash
source ./bashrc
```

This provides shortcuts like:
- `pm='sh /sdcard/rish'` - Quick package manager access via Shizuku
- `sd` - Navigate to sdcard and list contents
- `clear` - Clear terminal and history
- `op` - Play Android.mp3 with mpv

## Safety Notes

⚠️ **Warning**: These scripts modify system packages and delete directories. Use with caution!

- The `disable` script includes safety comments (`#`) for critical packages
- The `delete` script removes common Android directories - backup important data first
- Test on a non-production device first

## Testing

Run the included test to verify everything works:
```bash
./test_functionality.sh
```

## Troubleshooting

**Permission denied**: Make sure scripts are executable: `chmod +x script_name`

**Shizuku not working**: Ensure Shizuku is properly activated and `rish_shizuku.dex` is in the same directory as `rish`

**Package manager errors**: Ensure you have proper permissions (root or Shizuku) and the package names are correct for your Android version