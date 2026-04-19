# modern-CLI

This is a collection of CLI tools that I find handy for bioinformatics work.

Basic:

- [Ghostty](https://ghostty.org/). Replacement for terminal or iTerm2. Highlighted for its speed over iTerm2. However, I don't feel the differences except for mouse drag in Zellij (I think iTerm2 has a conflict). I am currently still on iTerm2.
- [starship](https://starship.rs/). Replacement for oh-my-zsh.

Tools:

- [Zellij](https://zellij.dev/). Replacement for Screen or Tmux. The floating pane function is super helpful.
- [btop](https://github.com/aristocratos/btop). Replacement for top or htop.
- [zoxide](https://github.com/ajeetdsouza/zoxide). `z` or `zi` - replacement for cd.
- [bat](https://github.com/sharkdp/bat). Replacement for cat.
- [ripgrep](https://github.com/burntsushi/ripgrep). `rg` - replacement for grep (much faster).
- [fd](https://github.com/sharkdp/fd). Replacement for find. Simpler syntax.
- [fzf](https://github.com/junegunn/fzf). Fuzzy search. It replaces the cmd history search using Ctrl+r.

CSV processing:

- [xan](https://github.com/medialab/xan). Powerful, concepts similar to dplyr.


## Setting up

### For zsh (`.zshrc`)

```bash
eval "$(starship init zsh)"
eval "$(zoxide init zsh)"
source <(fzf --zsh)
```

### For bash (`.bashrc`)

```bash
export PATH="$HOME/.local/bin:$PATH" ## The software path need to be executed before initializing them
eval "$(starship init bash)"
eval "$(zoxide init bash)"
eval "$(fzf --bash)"
```

### Useful aliases

```bash
# Use the modern replacements
alias cat='bat'
alias grep='rg'
alias find='fd'
alias top='btop'

alias ls='eza'
alias ll='eza -lAh --group-directories-first'
alias l='eza -F --group-directories-first'
alias lt='eza -T -L 2 --group-directories-first'

export FZF_DEFAULT_COMMAND='fd --type f'
export FZF_CTRL_T_COMMAND="$FZF_DEFAULT_COMMAND"
export FZF_ALT_C_COMMAND='fd --type d'
```
