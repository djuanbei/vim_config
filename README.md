# vim_config
##Plugin 
https://github.com/junegunn/vim-plug

curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
  https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
  
https://github.com/xavierd/clang_complete

git clone https://github.com/xavierd/clang_complete.git /tmp/clang_complete
cp -r /tmp/clang_complete/* ~/.vim


### intsall git plugin 

mkdir -p ~/.vim/pack/tpope/start
cd ~/.vim/pack/tpope/start
git clone https://tpope.io/vim/fugitive.git
vim -u NONE -c "helptags fugitive/doc" -c q
call plug#end()



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
