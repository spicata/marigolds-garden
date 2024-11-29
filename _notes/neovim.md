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

Neovim also supports plugins. It is easier to use plugins with a package manager than it is to do manually. Lazy.nvim is a popular package manager.

As shown on [this website](https://vonheikemen.github.io/devlog/tools/build-your-first-lua-config-for-neovim/), the following code snippet should be put into `init.lua` under the options above.

```lua
local lazy = {}

function lazy.install(path)
  if not vim.loop.fs_stat(path) then
    print('Installing lazy.nvim....')
    vim.fn.system({
      'git',
      'clone',
      '--filter=blob:none',
      'https://github.com/folke/lazy.nvim.git',
      '--branch=stable', -- latest stable release
      path,
    })
  end
end

function lazy.setup(plugins)
  if vim.g.plugins_ready then
    return
  end

  -- You can "comment out" the line below after lazy.nvim is installed
  lazy.install(lazy.path)

  vim.opt.rtp:prepend(lazy.path)

  require('lazy').setup(plugins, lazy.opts)
  vim.g.plugins_ready = true
end
```

To import plugins, write:

```lua
lazy.setup({
  {'plugin-1'},
  {'plugin-2'},
})
```

For example:

```lua
lazy.setup({
  {'nvim-lualine/lualine.nvim', dependencies = { 'nvim-tree/nvim-web-devicons' }},
  {'windwp/nvim-autopairs', event = "InsertEnter", opts = {}},
})

require('lualine').setup() -- some plugins will require stuff like this afterwards.
                           -- Check the plugin's help page/github for info   
```
