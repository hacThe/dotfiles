# Dotfiles

This repository contains my personal dotfiles managed with [YADM](https://yadm.io/) (Yet Another Dotfiles Manager).

## Overview

These dotfiles include configurations for:

- Zsh shell with Zinit plugin manager
- Neovim (via submodule)
- Tmux with custom configuration
- Starship prompt
- Various CLI tools (fzf, exa, bat, etc.)
- macOS-specific configurations

## Prerequisites

- Git
- YADM
- macOS (primary target, though some configs may work on other systems)

## Installation

### 1. Install YADM

```bash
# macOS with Homebrew
brew install yadm

# Other systems
curl -fLo /usr/local/bin/yadm https://github.com/TheLocehiliosan/yadm/raw/master/yadm
chmod a+x /usr/local/bin/yadm
```

### 2. Clone the repository

```bash
yadm clone https://github.com/hacThe/dotfiles.git
```

### 3. Run the bootstrap script

The bootstrap script will:
- Initialize Git submodules
- Install Homebrew (if on macOS and not already installed)
- Install packages from the Brewfile

```bash
yadm bootstrap
```

## Key Features

### Managed Files

- `.zshrc` - Shell configuration with various aliases and plugin setup
- `.config/nvim` - Neovim configuration (as a Git submodule)
- `.config/tmux` - Tmux configuration with plugins
- `.config/starship.toml` - Starship prompt configuration
- `.config/btop` - System monitoring configuration
- `.Brewfile` - Homebrew packages and applications

### Git Submodules

The following are managed as Git submodules:

- Neovim configuration
- Tmux plugins
- Oh My Tmux configuration

To update all submodules:

```bash
yadm submodule update --recursive --remote
```

### Bootstrap Script

The bootstrap script (`.config/yadm/bootstrap`) performs initial setup:

```bash
yadm bootstrap
```

## Usage

### Adding/Updating Files

```bash
# Add a new file to be tracked
yadm add ~/.some_config_file

# Commit changes
yadm commit -m "Add/update configuration"

# Push changes
yadm push
```

### Working with Alternate Files

YADM supports system-specific alternate files. For example:

```bash
# Create an alternate version of a file for macOS
yadm add ~/.config/app/config##os.Darwin

# Create an alternate for a specific hostname
yadm add ~/.config/app/config##h.myhostname
```

### Encryption (Optional)

To encrypt sensitive files:

```bash
# Configure which files to encrypt (first time)
yadm encrypt

# Add a file to the encrypted archive
yadm add -f ~/.ssh/config
yadm encrypt

# To decrypt files after cloning
yadm decrypt
```

## Tips and Tricks

- Use `yadm list` to see all tracked files
- Use `yadm status` to see the status of your dotfiles repository
- Use `yadm diff` to see changes to tracked files

## Customizing

1. Fork this repository
2. Modify files to suit your preferences
3. Add your own configurations

## License

These dotfiles are available under the MIT License. Feel free to use and modify as you wish. 