# elm-vim [![Release](https://img.shields.io/github/release/ajhager/elm-vim.svg?style=flat-square)](https://github.com/ajhager/elm-vim/releases)

Elm [elm-lang](http://elm-lang.org) support for Vim.

## Features

* Improved Syntax highlighting, including backtick operators, booleans, chars, triple quotes, string escapes, and tuple functions.
* Improved Indentation
* Commands and mappings for interfacing with the elm platform.

Check out this [ElmCast video](https://vimeo.com/132107269) for more detail.

## Install

Elm-vim follows the standard runtime path structure, so you should use a common
and well known plugin manager to install it. Do not use elm-vim with other Elm
plugins.

*  [Pathogen](https://github.com/tpope/vim-pathogen)
  * `git clone https://github.com/ajhager/elm-vim.git ~/.vim/bundle/elm-vim`
*  [vim-plug](https://github.com/junegunn/vim-plug)
  * `Plug 'ajhager/elm-vim'`
*  [NeoBundle](https://github.com/Shougo/neobundle.vim)
  * `NeoBundle 'ajhager/elm-vim'`
*  [Vundle](https://github.com/gmarik/vundle)
  * `Plugin 'ajhager/elm-vim'`
*  Manually
	* Copy all of the files into your `~/.vim` directory

Please be sure all necessary binaries are installed (such as `elm-make`, `elm-doc`,
`elm-reactor`, etc..) from http://elm-lang.org/. You may also want to install `elm-test` with `npm install -g elm-test` if you want to run unit tests from within vim.

## Usage

Many of the [features](#features) are enabled by default. There are no
additional settings needed. All usages and commands are listed in
`doc/elm-vim.txt`.

    :help elm-vim

* `:ElmMake [filename]` calls `elm-make` with the given file. If no file is given it uses the current file being edited.

* `:ElmMakeMain` attempts to call `elm-make` with "Main.elm".

* `:ElmTest` calls `elm-test` with the given file. If no file is given it attempts to run the tests in 'Test[filename].elm'.

* `:ElmRepl` runs `elm-repl`, which will return to vim on exiting.

* `:ElmErrorDetail` shows the detail of the current error in the quickfix window.

## Mappings

Elm-vim has several `<Plug>` mappings which can be used to create custom
mappings. Below are some examples you might find useful:

```vim
au FileType elm nmap <leader>b <Plug>(elm-make)
au FileType elm nmap <leader>m <Plug>(elm-make-main)
au FileType elm nmap <leader>t <Plug>(elm-test)
au FileType elm nmap <leader>r <Plug>(elm-repl)
au FileType elm nmap <leader>d <Plug>(elm-error-detail)
```

## Settings

Below are some (default) settings you might find useful to change.

```
let g:elm_jump_to_error = 1
let g:elm_make_output_file = "elm.js"
let g:elm_make_show_warnings = 0
```

## Indentation

The current indentation function is still rough, but should work for a lot of cases. It is not always possible to know the perfect indentation level just from context, but we should be able to generate a list of candidates.

## Credits

* Other vim-plugins, thanks for inspiration (elm.vim, ocaml.vim, haskell-vim)
* [Contributors](https://github.com/ajhager/elm-vim/graphs/contributors) of elm-vim

## License

The BSD 3-Clause License - see `LICENSE` for more details
