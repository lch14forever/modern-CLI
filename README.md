# modern-CLI

This is a collection of CLI tools that I find handy for bioinformatics work.

Basic:

- [Ghostty](https://ghostty.org/). Replacement for terminal or iTerm2. Highlighted for its speed over iTerm2. However, I don't feel the differences except for mouse drag in Zellij (I think iTerm2 has a conflict). I am currently still on iTerm2.
- [starship](https://starship.rs/). Replacement for oh-my-zsh.
  <img width="846" height="91" alt="image" src="https://github.com/user-attachments/assets/99feb55c-a7be-48b0-83db-dfbac3364663" />
  
  <img width="796" height="69" alt="image" src="https://github.com/user-attachments/assets/c1a3ea75-e483-40b9-b7b6-be4fedb3bfbd" />



Tools:

- [Zellij](https://zellij.dev/). Replacement for Screen or Tmux. The floating pane function is super helpful.
  <img width="1902" height="1008" alt="image" src="https://github.com/user-attachments/assets/0bdf70af-e99b-4866-b054-d6a840d9d898" />

- [btop](https://github.com/aristocratos/btop). Replacement for top or htop.
- [zoxide](https://github.com/ajeetdsouza/zoxide). `z` or `zi` - replacement for cd.
  <img width="1899" height="467" alt="image" src="https://github.com/user-attachments/assets/2a8d928b-779b-47ea-b17f-272e1b1385d1" />

- [bat](https://github.com/sharkdp/bat). Replacement for cat.
  <img width="503" height="498" alt="image" src="https://github.com/user-attachments/assets/93e3d3e5-2731-42a6-977f-11cd50bb66d5" />

- [ripgrep](https://github.com/burntsushi/ripgrep). `rg` - replacement for grep (much faster).
- [fd](https://github.com/sharkdp/fd). Replacement for find. Simpler syntax.
  <img width="360" height="305" alt="image" src="https://github.com/user-attachments/assets/762a47f4-876c-4303-bb42-fdc0d661f1fa" />

- [fzf](https://github.com/junegunn/fzf). Fuzzy search. It replaces the cmd history search using Ctrl+r.

CSV processing:

- [xan](https://github.com/medialab/xan). Powerful, concepts similar to dplyr.
<img width="410" height="440" alt="image" src="https://github.com/user-attachments/assets/6f13a719-b382-4440-9709-7da89b5de53c" />



## Setting up

### Installation

#### Using cargo (rust)

```
cargo install starship zellij zoxide bat ripgrep fd-find xan
```

We can use [cargo binstall](https://github.com/cargo-bins/cargo-binstall) to avoid compilation.

`btop` and `fzf` to be installed separately

#### Using homebrew (probably easist)

Haven't tested this.

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
