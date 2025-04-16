# Dotfiles

Personal configuration repository for development environment on macOS.

## Contents

- Zsh configuration (`.zshrc`) with Zinit, aliases and environment settings
- Neovim configuration
- Tmux configuration with useful plugins
- Homebrew application list (`.Brewfile`)
- Advanced CLI tools (fzf, ripgrep, zoxide, atuin, ...)
- Terminal configuration (Ghostty, Wezterm)

## Installation on a new machine

### 1. Install basic tools

```bash
# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Git
brew install git
```

### 2. Clone repository

```bash
# Clone repository to home directory
git clone --recursive https://github.com/yourusername/dotfiles.git ~/dotfiles

# Or if already cloned, update submodules
git submodule update --init --recursive
```

### 3. Link configuration files

```bash
# Navigate to dotfiles directory
cd ~/dotfiles

# Create symbolic links for configuration files
ln -sf ~/dotfiles/.zshrc ~/.zshrc
ln -sf ~/dotfiles/.config ~/.config
ln -sf ~/dotfiles/.local ~/.local
ln -sf ~/dotfiles/.Brewfile ~/.Brewfile
```

### 4. Install applications from Brewfile

```bash
# Install all applications from Brewfile
brew bundle --file=~/.Brewfile
```

### 5. Install Zinit (Zsh plugin manager)

```bash
# Zinit will be automatically installed when you open Zsh for the first time
# However, you can install it manually with the command:
mkdir -p ~/.local/share/zinit
git clone https://github.com/zdharma-continuum/zinit ~/.local/share/zinit/zinit.git
```

### 6. Install fonts (optional)

```bash
# Will be automatically installed through Brewfile if you use Homebrew
# Or manually install Nerd Fonts and SF Mono
```

### 7. Restart shell

```bash
# Restart shell to apply new configuration
exec zsh
```

## Key Features

- **Modern Terminal**: Customized prompt via Starship
- **Command History**: Store and search shell history with Atuin
- **Directory Navigation**: Quickly switch directories with Zoxide
- **Fuzzy Finding**: Search files, history and more with fzf
- **Terminal Sessions**: Manage work sessions with Tmux
- **Editor**: Optimized Neovim configuration for development

## Customization

You can customize the configurations to suit your personal needs:

- Edit `.zshrc` to add/remove aliases or shell configuration
- Edit `.Brewfile` to add/remove applications
- Customize Neovim through the `.config/nvim` directory
- Customize Tmux in `.config/tmux`

## Updates

```bash
# Navigate to dotfiles directory
cd ~/dotfiles

# Pull latest changes
git pull

# Update submodules
git submodule update --remote

# Update Homebrew applications
brew bundle --file=~/.Brewfile
```

## Useful Shortcuts

- `^P`, `^N`: Search command history
- `^Space`: Accept suggestion from zsh-autosuggestions
- `Alt+C`: Jump to subdirectory with fzf
- `Ctrl+R`: Search command history with Atuin
- `z <keyword>`: Jump to previously accessed directory

## Included Tools

- [Bat](https://github.com/sharkdp/bat): Cat with syntax highlighting and Git integration
- [Eza](https://github.com/eza-community/eza): A replacement for ls with more features
- [Ripgrep](https://github.com/BurntSushi/ripgrep): Text search faster than grep
- [Lazygit](https://github.com/jesseduffield/lazygit): TUI interface for Git
- [FZF](https://github.com/junegunn/fzf): Fuzzy finder
- [Zoxide](https://github.com/ajeetdsouza/zoxide): Smart directory navigation
- [Tmux](https://github.com/tmux/tmux): Terminal session management and persistence 