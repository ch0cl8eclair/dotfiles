# Dot files repository

This repository is used to host my dot files, it uses dotbot to create symlinks.

## Instructions

1. Check out this repository to your home folder `git clone https://github.com/ch0cl8eclair/dotfiles.git ~/dotfiles/`
2. [Install ZSH](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH)
3. [Install Oh my zsh](https://ohmyz.sh/#install)
4. [Install ZSH plugin manager](https://getantidote.github.io/)
    `git clone --depth=1 https://github.com/mattmc3/antidote.git ${ZDOTDIR:-~}/.antidote`
5. Install tools and utilities, for Ubuntu the following command does the trick
    `sudo apt install tmux neovim fd-find fzf eza jq gh ripgrep unzip make gcc bat`

    note that tool names vary by OS.

    note that the default nvim version may be too old in which case you will need to [manually install](https://blog.mikadifo.com/2024/05/how-to-install-or-upgrade-neovim-easy.html)
6. Clone the neovim repository, I'm using a fork o kickstart nvim
    `gh repo clone ch0cl8eclair/kickstart.nvim ~/.config/nvim`
7. Install the Tmux plugin manager
    `gh repo clone tmux-plugins/tpm ~/.tmux/plugins/tpm`

## Install Fonts

- Download font from [Nerd Fonts](https://www.nerdfonts.com/font-downloads)
- unzip to ~/.fonts/ dir
- fc-cache -fv to rebuild fonts cache

## Install process
- Run dotbot: `cd ~/dotfiles; ./install`
- Restart the zsh after installing all the tools. This will have the zsh plugins installed.
- Start Nvim, this will have the various nvim plugins installed and should show their status.
- Start Tmux, enter: prefix - I to install the plugins.

# Dot files overview

The following is a breakdown of the dotfiles repository and what each file configures:
```txt
.
├── aliases            - common aliases
├── aliases_secondary  - machine specific aliases and env vars
├── bashrc             - bashrc config file
├── config
│  ├── nvim
│  └── tmux            - tmux config dir
├── dotbot             - dotbot executable
├── environment-setup.md
├── gitignore          - root git ignore file
├── install            - dotbot dotfile installer
├── install.conf.yaml  - dotbot config with regards to symlinks
├── tmux               - redundant tmux config
├── vimrc              - vim config where nvim is not installed
├── zsh_plugins.txt    - list of zsh plugins to install
└── zshrc              - zsh config file
```
# ZSH Prompt optimisation

Speed up the zsh prompt for large git repos. Where the prompt displays git information large repos can cause a huge lag:
```shell
git config --add oh-my-zsh.hide-status 1
git config --add oh-my-zsh.hide-dirty 1
```

# Tool pages

Here are links to the key tools that I like to use:
- [bat](https://github.com/sharkdp/bat)
- [fzf](https://github.com/junegunn/fzf)
- [rg](https://github.com/BurntSushi/ripgrep)
- [fd](https://github.com/sharkdp/fd)

