# Android Studio Setup Guide for MacOS

## Prerequisites
- Android Studio installed
- Terminal access
- Basic understanding of terminal commands

## Finding SDK Location
1. Open Android Studio
2. Navigate to:
   - Android Studio > Settings (or Preferences)
   - Appearance & Behavior > System Settings > Android SDK
   - Note the "Android SDK Location" path

## Default Locations
```bash
Android Studio: /Applications/Android Studio.app
Android SDK: ~/Library/Android/sdk
```

## Setting up Environment Variables

### 1. Identify Your Shell
Check which shell you're using:
```bash
echo $SHELL
```

### 2. Edit Profile File
Based on your shell:
- For Zsh (default on newer Macs): `~/.zshrc`
- For Bash: `~/.bash_profile` or `~/.bashrc`

### 3. Add Environment Variables
Add these lines to your profile file:
```bash
# Android SDK
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
export PATH=$PATH:$ANDROID_HOME/emulator
```

### 4. Apply Changes
Reload your profile:
```bash
# For Zsh
source ~/.zshrc

# For Bash
source ~/.bash_profile
```

## Verification
Verify your setup with these commands:
```bash
# Should display SDK path
echo $ANDROID_HOME

# Should display adb version
adb --version
```

## Troubleshooting
If paths aren't working:
1. Ensure Android Studio is properly installed
2. Verify SDK location in Android Studio settings
3. Check if profile file is correctly sourced
4. Make sure all paths exist in your filesystem

## Additional Resources
- [Android Studio Documentation](https://developer.android.com/studio)
- [Android SDK Documentation](https://developer.android.com/studio/command-line)