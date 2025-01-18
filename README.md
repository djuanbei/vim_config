# vim_config
##Plugin 
https://github.com/junegunn/vim-plug

```shell
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
  https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```  
https://github.com/xavierd/clang_complete

```shell
git clone https://github.com/xavierd/clang_complete.git /tmp/clang_complete
cp -r /tmp/clang_complete/* ~/.vim
```

### Vundle

```shell
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

### intsall git plugin 

```shell

mkdir -p ~/.vim/pack/tpope/start
cd ~/.vim/pack/tpope/start
git clone https://tpope.io/vim/fugitive.git
vim -u NONE -c "helptags fugitive/doc" -c q

```
### intsall c/c++ header file switch 
down https://www.vim.org/scripts/script.php?script_id=31 a.vim
```shell
cp a.vim ~/.vim/plugin


```


## vim configure file .vimrc 

```plain


set number
set hlsearch 
set nocompatible              " be iMproved, required
filetype off                  " required
set autoindent

" Automatically closing braces
inoremap {<CR> {<CR>}<Esc>ko<tab>
inoremap [<CR> [<CR>]<Esc>ko<tab>
inoremap (<CR> (<CR>)<Esc>ko<tab>

autocmd FileType c,cpp setlocal equalprg=clang-format

call plug#begin()

" List your plugins here
Plug 'tpope/vim-sensible'
Plug 'cdelledonne/vim-cmake'

Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }
Plug 'junegunn/fzf.vim'



call plug#end()



" Vundle Plugin manager 
"
"

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

" The following are examples of different formats supported.
" Keep Plugin commands between vundle#begin/end.
" plugin on GitHub repo
"
Plugin 'godlygeek/tabular'
Plugin 'preservim/vim-markdown'
Plugin 'Valloric/YouCompleteMe'

"Compiling YCM with semantic support for C-family languages through clangd:
"cd ~/.vim/bundle/YouCompleteMe
"python3 install.py --clangd-YcmCompleter
" All of your Plugins must be added before the following line
call vundle#end()            " required

filetype plugin indent on    " required
" To ignore plugin indent changes, instead use:
"filetype plugin on
"
" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
"
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line


 " provide path directly to the library file
 let llvm_root=system("brew --prefix llvm ")
 let g:clang_library_path=llvm_root . '/lib/libclang.dylib'
	

nnoremap <C-l>  :YcmCompleter GoToDefinitionElseDeclaration<CR>


 let gitBranch=system("git rev-parse --abbrev-ref HEAD")
 set laststatus=2
 set statusline=%F%m%r%h%w\ [POS=%04l,%04v]\ [%p%%]\ [LEN=%L]\ 
 execute "set statusline +=" . gitBranch


 ```
