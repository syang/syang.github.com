---
layout: post
title: "vim setup for ansible"
date: 2014-03-11 16:27:55 -0700
comments: true
categories: ansible
---


### Prerequisite: Install Vundle

[Vundle](https://github.com/gmarik/Vundle.vim) is short for _Vim Bundle_, which is a plug-in manager for vim. If you want to use it for plug-in management, and read on.

Suppose you have already installed [Git](http://git-scm.com/book/en/Getting-Started-Installing-Git), set up Vundle from the source

```sh
$ git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle
```

### Configure the Ansible Bundle in your personal .vimrc 

Put the following at the top of your ~/.vimrc

```sh
set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/vundle/
call vundle#rc()
" alternatively, pass a path where Vundle should install bundles
"let path = '~/some/path/here'
"call vundle#rc(path)

" let Vundle manage Vundle, required
Bundle 'gmarik/vundle'

" Keep bundle commands between here and filetype plugin indent on.
" For Ansible formatting
Bundle 'chase/vim-ansible-yaml'
" For Go Language formatting
Bundle 'jnwhiteh/vim-golang'
" For HTML/CSS formatting
Bundle 'mattn/emmet-vim'
" For Chef script formatting
Bundle 't9md/vim-chef'

filetype plugin indent on     " required

" To ignore plugin indent changes, instead use:
"filetype plugin on
"
" Brief help
" :BundleList          - list configured bundles
" :BundleInstall(!)    - install (update) bundles
" :BundleSearch(!) foo - search (or refresh cache first) for foo
" :BundleClean(!)      - confirm (or auto-approve) removal of unused bundles
"
" see :h vundle for more details or wiki for FAQ
" NOTE: comments after Bundle commands are not allowed.
" Put your stuff after this line

```


### Install Bundles:

Lauch `vim` and run `:BundleInstall` OR install directly from command line: `vim +BundleInstall +qall`



