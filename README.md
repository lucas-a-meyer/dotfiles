# dotfiles

I'm writing these instructions mostly for my own use. These are based mainly on this 2014 [article](https://www.anishathalye.com/2014/08/03/managing-your-dotfiles/), and use the [DotBot](https://github.com/anishathalye/dotbot) scripts to sync my dotfiles to GitHub and install them on different environments.


## Installing dotfiles in a new environment

The command to install my dotfiles on a new environment is:

`git clone $repo --recursive && cd dotfiles && ./install`

Unless you're me, your `$repo` variable should point to your own repository. My repository can be set with:

 `export repo=git@github.com:lucas-a-meyer/dotfiles.git`

## Configuration

The configuration file is `install.config.yaml`. For documentation on the configuration options, there's a [Quick Guide](https://www.elliotdenolf.com/posts/bootstrap-your-dotfiles-with-dotbot). More detailed configuration instructions can be found in the [DotBot Wiki](https://github.com/anishathalye/dotbot/wiki).

## Normal use

Once installed, DotBot will add the dotfiles in your GitHub repository to your computer, and create links to them to your home directory. For example, my `~/dotfiles/bashrc` file will be linked to `~/.bashrc`. The configuration file `install.config.yaml` describes the links.

Since the files are linked, edits on either file are propagated to the other. 

If you edit the file on the local environment, remember to sync your edits to GitHub by doing a `git add .; git commit -m "describe changes"; git push`.

If you edited the files on another environment and want to bring the changes to this environment, just log into your local dotfiles repository, `git pull`, and `./install`. 