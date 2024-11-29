---
title: Neovim
---

Neovim is a text editor that is based on VIm (which itself is based on VI).

The configuration file for Neovim is stored at `~/.config/nvim/init.lua`. Inside of Neovim, this file can be edited by entering the command `:edit $MYVIMRC`.

At the time of writing, my `init.lua` starts with:

```lua
vim.cmd('colorscheme habamax')  -- This changes the colour
vim.opt.number = true           -- This shows numbers in the gutter
vim.opt.tabstop = 2             -- This changes the number of spaces a tab is worth
vim.opt.shiftwidth = 2          -- This should be the same as tabstop
vim.opt.wrap = false            -- This turns off wrapping long lines
```
