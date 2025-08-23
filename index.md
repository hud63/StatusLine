---
title: Claude Code Statusline Installation Guide (Windows)
---

# Claude Code Statusline Installation Guide (Windows)

This guide provides the exact steps to install and configure the statusline for Claude Code on Windows.

## Prerequisites
- Claude Code installed natively (NOT via npm)
- Windows with PowerShell available

## Installation Steps

### Step 1: Clean Existing Setup
1. Open Claude Code
2. Run the `/statusline` command
3. Tell Claude to completely remove any existing statusline configuration

### Step 2: Install Statusline from Scratch  
1. Run `/statusline` command again in Claude Code
2. Tell Claude to "completely install and set up statusline from the ground up"
3. This will install the `ccusage` tool needed for the statusline

### Step 3: Configure Global Settings
1. Navigate to your Claude Code settings file: `C:\Users\[Username]\.claude\settings.json`
2. Add or update the following configuration:

```json
{
  "statusLine": {
    "type": "command",
    "command": "ccusage statusline"
  }
}
```

### Step 4: Verify Installation

1. Restart Claude Code or start a new session
2. The statusline should now display context usage information
3. If the statusline doesn't appear, try restarting Claude Code completely

## Troubleshooting

### If statusline doesn't display:

1. Verify the `ccusage` command is installed by running `/statusline` again in Claude Code
2. Check that the settings file is correctly formatted JSON
3. Ensure you're using the simple `ccusage statusline` command (not wrapped in PowerShell)
4. Restart Claude Code completely

### Common Issues:

* **"No input provided" error**: This is normal when running `ccusage statusline` manually - it needs session data from Claude Code
* **Command not found**: Run `/statusline` in Claude Code to install the tool
* **PowerShell wrapper not needed**: Use the simple `ccusage statusline` command for global configuration

## Final Configuration

The working configuration in `~/.claude/settings.json`:

```json
{
  "statusLine": {
    "type": "command",
    "command": "ccusage statusline"
  }
}
```

## Notes

* This configuration works globally across all folders where Claude Code is used
* The statusline displays context usage and session information
* No additional files or complex PowerShell wrappers are needed for the basic setup
* The `/statusline` command in Claude Code handles the installation of required tools
