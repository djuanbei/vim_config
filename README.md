# vim_config

## vim configure file .vimrc 

set number

set nocompatible              " be iMproved, required
filetype off                  " required


" Automatically closing braces
inoremap {<CR> {<CR>}<Esc>ko<tab>
inoremap [<CR> [<CR>]<Esc>ko<tab>
inoremap (<CR> (<CR>)<Esc>ko<tab>

autocmd FileType c,cpp setlocal equalprg=clang-format

call plug#begin()

" List your plugins here
Plug 'tpope/vim-sensible'
Plug 'cdelledonne/vim-cmake'

call plug#end()


 " provide path directly to the library file
 let g:clang_library_path='/opt/homebrew/opt/llvm/lib/libclang.dylib'
