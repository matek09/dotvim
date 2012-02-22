
These are my VIM settings, mostly targeting development with C/C++, Python and Lisp.

Here is a [video showing what I can do with these](http://www.wupload.com/file/2665561027/Vim.flv) when I code in C++.

Use [MPlayer](http://www.mplayerhq.hu) or [VideoLAN](http://www.videolan.org/) to play it.
I also tried [uploading it to Youtube](http://www.youtube.com/watch?v=5f5MN8dZDtk), but quality is really low, even in HD setting.

I use a small number of plugins, and did some minor customization for shortcuts:

General stuff
-------------

- I maintain my plugins with pathogen, and use Git submodules to always
  have the latest versions. 

- In any new machine/account I need to work on, I clone::

    cd 
    git clone https://github.com/ttsiodras/dotvim .vim
    cd .vim
    git submodule init
    git submodule update
    cd ..
    ln -s .vim/.vimrc

  And therefore use the same environment in all machines I work on.

For C/C++ development
---------------------

- I create /usr/include/tags::

    (become root via su/sudo)
    cd /usr/include
    ctags -R --c++-kinds=+p --fields=+iaS --extra=+q .

  ... and my .vimrc is set to use these, as well as any local tags I build
  in my project-specific Makefiles::

    set tags+=/usr/include/tags

- I use clang complete ( http://www.vim.org/scripts/script.php?script_id=3302 )
  to get Intellisense-like autocompletion (see the video above)

- I use the 'A' plugin to quickly switch between .h/c{c,pp} with ':A'

- 'K' to show manpages on current symbol under cursor in "inner window" (allows me to copy/paste)

For Python development
----------------------

I've mapped F7 to invoke flake8 (install it with: "easy_install flake8") to get 
static analysis error reports from pyflakes and style mishaps from pep8, navigating
from error to error in the usual way (:cn, :cp)

Generic stuff
-------------

- I've mapped:
    NERDTreeToggle to F10, for direct access to "file manager" interface :-)
    Ctrl-cursors to navigate windows (under both XTerms and GVim)
    Ctrl-L to clear search results (hate seeing yellow stuff after search)
    Ctrl-End to quickly close "window" (buffer)
    F8 to show taglists (macros/types/variables/functions/classes)
    
- I also have easy motion in, so I can navigate to any place in the screen
  with a simple \\w followed by a character. Amazing plugin.

Am I insane to use VIM?
-----------------------
(No, I am not)[http://www.viemu.com/a-why-vi-vim.html]