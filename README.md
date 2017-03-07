## vimconfig





set nu
sy on                
set cindent        
set nobackup     
set tabstop=4   
set shiftwidth=4 
set number   
set hlsearch
"set nobomb
set compatible
set autoindent
set background=dark
"set ai
syntax enable
"colorscheme molokai
"colorscheme solarized

set nocompatible              " required
"filetype off                  " required
set splitbelow
set splitright

set noswapfile

set cursorline
hi CursorLine term=bold cterm=bold guibg=Grey40

let &t_Co=256

set runtimepath^=~/.vim/bundle/ctrlp.vim

"nmap <leader>h :tabprevious<CR>
"nmap <leader>l :tabnext<CR>
"nmap <leader>n :tabnew<CR>
"nmap <leader>d :tabclose<CR>
"nmap <leader>q :bp <BAR> bd #<CR>
noremap  {  :tabprevious<CR>
noremap  }  :tabnext<CR>
noremap  +  :tabnew<CR>
noremap  _  :tabclose<CR>
noremap  D  :tabclose<CR>



noremap  J  :wincmd j<CR>
noremap  K  :wincmd k<CR>
noremap  H  :wincmd h<CR>
noremap  L  :wincmd l<CR>

noremap  <S-UP>  :wincmd j<CR>
noremap  <S-DOWN> :wincmd k<CR>
noremap  <S-Left>  :wincmd h<CR>
noremap  <S-Right> :wincmd l<CR>


noremap <leader>q :bp <BAR> bd #<CR>

" Load rope plugin  For Jeji Problem
"let g:pymode_rope = 0
set rtp +=~/.vim/bundle/vundle
call vundle#begin()

	Bundle 'gmarik/vundle'
	Bundle 'vim-airline/vim-airline'
	Bundle 'vim-airline/vim-airline-themes'
	Bundle 'kien/ctrlp.vim'
	Bundle 'altercation/vim-colors-solarized'
	Bundle 'scrooloose/syntastic'
	Bundle 'python-mode/python-mode'
	Bundle 'fatih/molokai'
    Bundle 'ervandew/supertab'
	Bundle 'tagbar'
   	Bundle 'The-NERD-tree'
	Bundle 'matchit.zip'
	Bundle 'Command-T'
	Bundle 'tpope/vim-sensible'
"	Bundle 'Valloric/YouCompleteMe'
	Bundle 'amix/vimrc'
	Bundle 'tpope/vim-fugitive'
	"Bundle 'rkulla/pydiction'
	Bundle 'shougo/neocomplete.vim'
"	Bundle 'jiangmiao/auto-pairs' Bundle 'auto-pairs'
	Bundle 'itchyny/lightline.vim'
	Bundle 'skammer/vim-css-color'

	Bundle 'mattn/emmet-vim'
	Bundle 'easymotion/vim-easymotion'
	Bundle 'Yggdroot/indentLine'

	" Track the engine.
	Bundle 'SirVer/ultisnips'

	" Snippets are separated from the engine. Add this if you want them:


call vundle#end()  

filetype plugin on
filetype plugin indent on



call pathogen#infect()
call pathogen#helptags()

filetype plugin indent on
syntax on

let g:airline#extensions#tabline#enabled = 0 



autocmd StdinReadPre * let s:std_in=1
autocmd VimEnter * if argc() == 0 && !exists("s:std_in") | NERDTree | endif



let g:NERDTreeWinSize = 15 


nmap <F9>hi! link linenr folded <CR>
nmap <F3> :NERDTreeToggle<CR>
nmap <F4> :TagbarToggle<CR>
map <C-g> :!python %<CR>


set nocompatible              " required
"filetype off                  " required
set splitbelow
set splitright


set autowrite
map <C-n> :cnext<CR>
map <C-m> :cprevious<CR>

let g:go_list_type = "quickfix"
let g:go_auto_sameids = 1


let g:rehash256 = 1
let g:molokai_original = 1
colorscheme molokai

autocmd FileType go nmap <leader>b  <Plug>(go-build)
autocmd FileType go nmap <leader>r  <Plug>(go-run)


"vim airline
set laststatus=2
let Tlist_Use_Right_Window=1
let Tlist_WinWidth = 16 

"NERDTree 
let g:NERDTreeWinSize = 18
let g:NERDTreeDirArrowExpandable = '▸'
let g:NERDTreeDirArrowCollapsible = '▾'
let g:nerdtree_tabs_open_on_console_startup=1
let g:nerdtree_tabs_focus_on_files = 1


map <C-g> :!python %<CR>
map <C-h> :!scalac % && scala %<CR>

map <C-b> :!go build -o a.out % <CR>
"map <C-r> :!go run % <CR>
map <C-r> :!open % <CR>


" Gif config
map  / <Plug>(easymotion-sn)
omap / <Plug>(easymotion-tn)
"
" " These `n` & `N` mappings are options. You do not have to map `n` & `N` to
" EasyMotion.
" " Without these mappings, `n` & `N` works fine. (These mappings just provide
" " different highlight method and have some other features )
map  n <Plug>(easymotion-next)
map  N <Plug>(easymotion-prev)

"emmet-vim config
"let g:user_emmet_mode='n'    "only enable normal mode functions.
"let g:user_emmet_mode='inv'  "enable all functions, which is equal to
"
let g:user_emmet_mode='a'    "enable all function in all mode.
autocmd FileType html,css EmmetInstall


"jhint validation
nnoremap <silent><F1> :JSHint<CR>
inoremap <silent><F1> <C-O>:JSHint<CR>
vnoremap <silent><F1> :JSHint<CR>


"Skammer/vim-css-color config
"let g:cssColorVimDoNotMessMyUpdatetime = 1


"filetype on 
"au BufRead,BufNewFile *.go set filetype=go

au Filetype go set makeprg=go\ build\ ./...
nmap <F5> :make<CR>:copen<CR>

let g:pymode = 1 
let g:pymode_indent = 1 
let g:pymode_rope = 1 
let g:pymode_rope_completion = 1 
let g:pymode_rope_complete_on_dot = 1 



set statusline+=%#warningmsg#
set statusline+=%{SyntasticStatuslineFlag()}
set statusline+=%*

let g:syntastic_always_populate_loc_list = 0 
let g:syntastic_auto_loc_list = 0 
let g:syntastic_check_on_open = 0 
let g:syntastic_check_on_wq = 0


" Vim
let g:indentLine_enabled =  0 
let g:indentLine_color_term = 200 


"tagbar
 let g:tagbar_width = 14


" Trigger configuration. Do not use <tab> if you use https://github.com/Valloric/YouCompleteMe.
let g:UltiSnipsExpandTrigger="<tab>"
let g:UltiSnipsJumpForwardTrigger="<c-b>"
let g:UltiSnipsJumpBackwardTrigger="<c-z>"

" If you want :UltiSnipsEdit to split your window.
let g:UltiSnipsEditSplit="vertical"

