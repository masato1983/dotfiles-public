# dotfiles-public
My personal dot files

## VSCode
### Configuration file path

[Settings Sync](https://code.visualstudio.com/docs/editor/settings-sync)

```
~/Library/Application Support/Code/User/
├── keybindings.json
├── settings.json
└── snippets
    ├── html.json
    ├── php.json
    └── scss.json
```

### extensions

```
~/.vscode/extensions
├── asvetliakov.vscode-neovim-0.0.83
├── ayushchugh.ejs-snippets-and-color-highlighting-0.0.5
├── bmewburn.vscode-intelephense-client-1.8.2
├── cssho.vscode-svgviewer-2.0.0
├── ctcuff.font-preview-1.3.2
├── eamodio.gitlens-12.0.5
├── esbenp.prettier-vscode-9.3.0
├── glenn2223.live-sass-5.3.0
├── jakewilson.vscode-placeholder-images-0.1.0
├── kamikillerto.vscode-linthtml-0.6.2
├── mdickin.markdown-shortcuts-0.12.0
├── mkxml.vscode-filesize-3.1.0
├── natqe.reload-0.0.6
├── ritwickdey.liveserver-5.7.5
├── stylelint.vscode-stylelint-1.2.2
├── threespot.frontline-sass-snippets-1.0.1
├── tomoki1207.pdf-1.2.0
├── vunguyentuan.vscode-css-variables-2.3.6
├── wallabyjs.quokka-vscode-1.0.451
└── wordpresstoolbox.wordpress-toolbox-1.3.12
```

## Homebrew

### cask list

```
/usr/local/Caskroom
├── 1password
├── adobe-creative-cloud
├── aerial
├── amazon-workdocs-drive
├── amazon-workspaces
├── atom
├── brave-browser
├── cmd-eikana
├── deepl
├── discord
├── figma
├── firefox
├── gitkraken
├── google-chrome
├── iterm2
├── local
├── mamp
├── microsoft-auto-update
├── microsoft-edge
├── ogdesign-eagle
├── polypane
├── rectangle
├── slack
├── transmit
├── visual-studio-code
├── zeplin
└── zoom
```

### formulae list

```
/usr/local/Cellar
├── ca-certificates
├── commitizen
├── fzf
├── gdbm
├── gettext
├── gh
├── libevent
├── libtermkey
├── libuv
├── luajit-openresty
├── luv
├── mpdecimal
├── msgpack
├── ncurses
├── neovim
├── openssl@1.1
├── python@3.10
├── readline
├── sqlite
├── tmux
├── tree
├── tree-sitter
├── unibilium
├── utf8proc
└── xz
```

## NeoVim

- version check     `nvim --version`
- install `brew install neovim`

### Migrate from vim to neovim (`~/.zshrc`)

```
# alias
alias vi='nvim'
alias vim='nvim'
alias view='nvim -R'
alias cz='cz commit'

# options
setopt auto_pushd
setopt pushd_ignore_dups
setopt auto_cd
setopt hist_ignore_dups
setopt share_history
setopt inc_append_history

```



### Configure neovim configuration settings (~/.config/nvim/init.vim)

If the directory or file does not exist, create a new one.

```
set shell=/bin/zsh
set shiftwidth=4
set tabstop=4
set expandtab
set textwidth=0
set autoindent
set hlsearch
set clipboard=unnamed
syntax on

call plug#begin()
Plug 'tpope/vim-commentary'
call plug#end()
```

### Vim Plugin managers

- [vim-plug](https://github.com/junegunn/vim-plug)

### Vim Plugin

- [vim-commentary](https://github.com/tpope/vim-commentary)

Installation command

```
mkdir -p ~/.config/nvim/pack/tpope/start
cd ~/.config/nvim/pack/tpope/start
git clone https://tpope.io/vim/commentary.git
vim -u NONE -c "helptags commentary/doc" -c q
```


## zsh
- [ohmyzsh](https://ohmyz.sh/#install)

- plugin
    - [web-search](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/web-search)
    - [fzf](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/fzf)
    - [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
    - [zsh-autosuggestions ](https://github.com/zsh-users/zsh-autosuggestions)
    - [powerlevel10k](https://github.com/romkatv/powerlevel10k)
    - [zsh-nvm](https://github.com/lukechilds/zsh-nvm#as-an-oh-my-zsh-custom-plugin)


```
# Enable Powerlevel10k instant prompt. Should stay close to the top of ~/.zshrc.
# Initialization code that may require console input (password prompts, [y/n]
# confirmations, etc.) must go above this block; everything else may go below.
if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
  source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
fi

# If you come from bash you might have to change your $PATH.
# export PATH=$HOME/bin:/usr/local/bin:$PATH

# Path to your oh-my-zsh installation.
export ZSH="/Users/masato/.oh-my-zsh"
export NVM_AUTO_USE=true

# Set name of the theme to load --- if set to "random", it will
# load a random theme each time oh-my-zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
ZSH_THEME="powerlevel10k/powerlevel10k"

# Set list of themes to pick from when loading at random
# Setting this variable when ZSH_THEME=random will cause zsh to load
# a theme from this variable instead of looking in $ZSH/themes/
# If set to an empty array, this variable will have no effect.
# ZSH_THEME_RANDOM_CANDIDATES=( "robbyrussell" "agnoster" )

# Uncomment the following line to use case-sensitive completion.
# CASE_SENSITIVE="true"

# Uncomment the following line to use hyphen-insensitive completion.
# Case-sensitive completion must be off. _ and - will be interchangeable.
# HYPHEN_INSENSITIVE="true"

# Uncomment one of the following lines to change the auto-update behavior
# zstyle ':omz:update' mode disabled  # disable automatic updates
# zstyle ':omz:update' mode auto      # update automatically without asking
# zstyle ':omz:update' mode reminder  # just remind me to update when it's time

# Uncomment the following line to change how often to auto-update (in days).
# zstyle ':omz:update' frequency 13

# Uncomment the following line if pasting URLs and other text is messed up.
# DISABLE_MAGIC_FUNCTIONS="true"

# Uncomment the following line to disable colors in ls.
# DISABLE_LS_COLORS="true"

# Uncomment the following line to disable auto-setting terminal title.
# DISABLE_AUTO_TITLE="true"

# Uncomment the following line to enable command auto-correction.
# ENABLE_CORRECTION="true"

# Uncomment the following line to display red dots whilst waiting for completion.
# You can also set it to another string to have that shown instead of the default red dots.
# e.g. COMPLETION_WAITING_DOTS="%F{yellow}waiting...%f"
# Caution: this setting can cause issues with multiline prompts in zsh < 5.7.1 (see #5765)
# COMPLETION_WAITING_DOTS="true"

# Uncomment the following line if you want to disable marking untracked files
# under VCS as dirty. This makes repository status check for large repositories
# much, much faster.
# DISABLE_UNTRACKED_FILES_DIRTY="true"

# Uncomment the following line if you want to change the command execution time
# stamp shown in the history command output.
# You can set one of the optional three formats:
# "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"
# or set a custom format using the strftime function format specifications,
# see 'man strftime' for details.
# HIST_STAMPS="mm/dd/yyyy"

# Would you like to use another custom folder than $ZSH/custom?
# ZSH_CUSTOM=/path/to/new-custom-folder

# Which plugins would you like to load?
# Standard plugins can be found in $ZSH/plugins/
# Custom plugins may be added to $ZSH_CUSTOM/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(git npm z fzf web-search zsh-nvm zsh-autosuggestions zsh-syntax-highlighting)

source $ZSH/oh-my-zsh.sh

# User configuration

# export MANPATH="/usr/local/man:$MANPATH"

# You may need to manually set your language environment
# export LANG=en_US.UTF-8

# Preferred editor for local and remote sessions
# if [[ -n $SSH_CONNECTION ]]; then
#   export EDITOR='vim'
# else
#   export EDITOR='mvim'
# fi

# Compilation flags
# export ARCHFLAGS="-arch x86_64"

# Set personal aliases, overriding those provided by oh-my-zsh libs,
# plugins, and themes. Aliases can be placed here, though oh-my-zsh
# users are encouraged to define aliases within the ZSH_CUSTOM folder.
# For a full list of active aliases, run `alias`.
#
# Example aliases
# alias zshconfig="mate ~/.zshrc"
# alias ohmyzsh="mate ~/.oh-my-zsh"
```

## Chrome bookmark
- [Lint Images](https://ausi.github.io/respimagelint/)
- [W3C Markup Validation Service](https://validator.w3.org/)
- [W3C CSS Validation Service](https://jigsaw.w3.org/css-validator/)
- [Test your structured data](https://developers.google.com/search/docs/advanced/structured-data)
- [HTML5 入れ子チートシート](https://yoshikawaweb.com/element/)
- [browsing environment](https://env.mount.jp/)
- [squoosh](https://squoosh.app/)

## Browser extension
- [eagle](https://env.mount.jp/)
- [1Password](https://support.1password.com/getting-started-browser/)
- [Wappalyzer](https://chrome.google.com/webstore/detail/wappalyzer-technology-pro/gppongmhjkpfnbhagpmjfkannfbllamg)
