# sort-import.nvim

## What it does

This plugin will sort you (type|java)script imports using the [import-sort](https://github.com/renke/import-sort) program. You can sort synchronously or asynchronously by passing `true` or `false` (`true` for async, `false` for sync) to the `sort_import` function. It also provides a `:Sort` command which will asynchronously sort your imports.

The plugin requires that you have the `import-sort` program installed either in your project, or globally on your machine. It will first look for the program in `$PWD/node_modules`, then `<git_project_root>/node_modules`, and finally it will try and see if it is in the `$PATH`.

### Suggested import-sort styles

`import-sort-cli import-sort-parser-babylon import-sort-parser-typescript import-sort-style-renke`

## Installation

Using your plugin manager:

Using [vim-plug](https://github.com/junegunn/vim-plug)
`Plug 'jamestthompson3/sort-import.nvim'`

Using [packer.nvim](https://github.com/wbthomason/packer.nvim)
`use {'jamestthompson3/sort-import.nvim', config = function() require'sort-import.nvim'.setup() end}`

Using [dein](https://github.com/Shougo/dein.vim)
`call dein#add('jamestthompson/sort-import.nvim')`

## Usage

In lua:

```lua
require'sort-import'.setup() -- setup to have access to the :Sort command, not necessary if you put this in packer.nvim's config option for the plugin

require'sort-import'.sort_import() -- for synchronous sorting
require'sort-import'.sort_import(true) -- for asynchronous sorting
```

In viml:

```viml
lua require'sort-import'.setup()  " setup to have access to the :Sort command, not necessary if you put this in packer.nvim's config option for the plugin

lua require'sort-import'.sort_import() " for synchronous sorting
lua require'sort-import'.sort_import(true) " for asynchronous sorting
```

## Notes

If you're not on at least `61aea004d` of Neovim nightly, you may run into some issues with treesitter highlighting and sorting asynchronously.
