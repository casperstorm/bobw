# init.lua - a configuration for both VSCode and Neovim.

I love modal editing. But I also love VSCode. This repository is my configuration for setting up VSCode with modal editing using a fully embedded Neovim instance with some sane defaults.

## Prerequisite

- [Neovim](https://github.com/neovim/neovim) 0.5.0 or greater.
- [vscode-neovim](https://github.com/asvetliakov/vscode-neovim) extension.
- [Which Key](https://github.com/VSpaceCode/vscode-which-key) extension.

## Installing

```sh
git clone https://github.com/casperstorm/init.lua.git ~/.config/nvim
```

## Setup

### VSCode

In `Settings (JSON)` you need to add the path to Neovim executable and the `vscode/init.vim` path:

```json
{
  "vscode-neovim.neovimExecutablePaths.darwin": "/usr/local/bin/nvim",
  "vscode-neovim.neovimInitVimPaths.darwin": "$HOME/.config/nvim/vimscript/vscode/init.vim"
}
```

In `Keybindings Shortcuts (JSON)` I suggest adding the following keybindings to use <kbd>Ctrl</kbd>+<kbd>h</kbd>/<kbd>j</kbd>/<kbd>k</kbd>/<kbd>l</kbd> for moving between panels.

```json
[
  {
    "key": "ctrl+h",
    "command": "workbench.action.navigateLeft"
  },
  {
    "key": "ctrl+j",
    "command": "workbench.action.navigateDown"
  },
  {
    "key": "ctrl+k",
    "command": "workbench.action.navigateUp",
    "when": "terminalFocus"
  },
  {
    "key": "ctrl+l",
    "command": "workbench.action.navigateRight"
  }
]
```

[Which Key](https://github.com/VSpaceCode/vscode-which-key) ships out of the box with keybindings which mimic the once from spacemacs. If you which to change them, you can do so in `Settings (JSON)`. You can find my bindings in [which-key.json](./utils/vscode/which-key.json).

### Neovim

No setup is needed. Launching `nvim` in your Terminal of choice will use `init.lua`. No plugins. No maintendance.
