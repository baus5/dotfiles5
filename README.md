# dotfiles

My development environment settings, configurations and customizations for - macOS, Linux, Windows and all OS




## Context

* HomeBrew



# HomeBrew



## Formulae

[Homebrew Formulae](https://formulae.brew.sh/) is an online package browser for [Homebrew](https://brew.sh/) – the macOS (and Linux) package manager.

- https://formulae.brew.sh



## My Formulas



### wget

Internet file retriever

install:

```
brew install wget
```

Examples:

```
wget <file/url>
wget --mirror <url>
wget --mirror --page-requisites --convert-link --no-clobber --no-parent --domains <website>
```



# iTerm2

https://iterm2.com

iTerm2 is a replacement for Terminal and the successor to iTerm. It works on Macs with macOS 10.14 or newer. iTerm2 brings the terminal into the modern age with features you never knew you always wanted.



## install

```bash
brew install --cask iterm2
```



## uninstall

```
brew uninstall --cask iterm2
```

remove all settings:

```
defaults delete com.googlecode.iterm2
```



# oh-my-zsh

Oh My Zsh is a delightful, open source, community-driven framework for managing your Zsh configuration. It comes bundled with thousands of helpful functions, helpers, plugins, themes, and a few things that make you shout...

https://ohmyz.sh/

code:

https://github.com/ohmyzsh/ohmyzsh

https://github.com/ohmyzsh/ohmyzsh/wiki

Themes:

https://github.com/ohmyzsh/ohmyzsh/wiki/Themes



## install

**curl**:

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

wget:

```bash
sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
```



## themes

https://github.com/ohmyzsh/ohmyzsh/wiki/Themes

Local:

```
/Users/bausxm/.oh-my-zsh/themes
```



### external themes

https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes



## uninstall

It will remove itself and revert your previous `bash` or `zsh`configuration.

```
uninstall_oh_my_zsh
```



# Git



## install

### mac

### win

### linux





## Use SSH on WSL

How to Use SSH with GitHub (Instead of HTTPS) on Windows WSL

https://logfetch.com/git-ssh-keys/



### Obtain SSH key

To see if there is an existing `SSH` key that we can use:

```
ls -al ~/.ssh
```

If an `SSH` key already exists:

```
id_rsa.pub
id_ecdsa.pub
id_ed25519.pub
```

* If these files don’t exist, we’ll generate a new key.
* we can directly add the key to `ssh-agent`
* add to our GitHub account



### Generate a new key

replacing `some_email@gmail.com` with your GitHub account email:

```
ssh-keygen -t ed25519 -C "some_email@gmail.com"
```

* press `Enter` to use the default file location.
* type in a secure passphrase to add an extra layer of security to this process.



### Add key to ssh-agent

*info*

```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

* start the `ssh-agent` in the background
* add our private key to the `ssh-agent`



### Add key to GitHub account

we need to copy the public key to our clipboard.

```
cat ~/.ssh/id_ed25519.pub
cat ~/.ssh/id_ed25519.pub | clip  # on Windows
```

* Settings > SSH and GPG keys.
* New SSH key
* Title (Personal Pcname  WSL)
* Key > paste



### Test SSH connection

Let’s verify our setup.

```
ssh -T git@github.com
```

* type yes







# -End-

