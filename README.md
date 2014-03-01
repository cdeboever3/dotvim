This repository holds my vim packages and configuration packages. This set up
relies on the vim pathogen plugin. If you are interested in using this set up,
see the original blog post (References below) for help with first-time 
configuration.

# Install Vim environment on another machine

Clone repository:

    git clone https://github.com/cdeboever3/dotvim.git ~/.vim

Create symlinks:

	ln -s ~/.vim/vimrc ~/.vimrc
	ln -s ~/.vim/gvimrc ~/.gvimrc

Switch to the `~/.vim` directory, and fetch submodules:

	cd ~/.vim
	git submodule init
	git submodule update

# Install new submodules into environment

Here is an example installing the Fugitive vim package:

	cd ~/.vim
	mkdir ~/.vim/bundle
	git submodule add http://github.com/tpope/vim-fugitive.git bundle/fugitive
	git add .
	git commit -m "Install Fugitive.vim bundle as a submodule."

# Upgrading a plugin bundle

Example updating Fugitive vim package:

	cd ~/.vim/bundle/fugitive
	git pull origin master

# Upgrading all bundled plugins

	git submodule foreach git pull origin master

# References
This set up came from this post:

http://vimcasts.org/episodes/synchronizing-plugins-with-git-submodules-and-pathogen/
