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



### tree

Display directories as trees (with optional color/HTML output)

```
brew install tree
```

http://mama.indstate.edu/users/ice/tree/



### ascii

List ASCII idiomatic names and octal/decimal code-point forms

```
brew install ascii
```

http://www.catb.org/~esr/ascii/

Example:

```bash
$ ascii -d
```

```
    0 NUL    16 DLE    32      48 0    64 @    80 P    96 `   112 p
    1 SOH    17 DC1    33 !    49 1    65 A    81 Q    97 a   113 q
    2 STX    18 DC2    34 "    50 2    66 B    82 R    98 b   114 r
    3 ETX    19 DC3    35 #    51 3    67 C    83 S    99 c   115 s
    4 EOT    20 DC4    36 $    52 4    68 D    84 T   100 d   116 t
    5 ENQ    21 NAK    37 %    53 5    69 E    85 U   101 e   117 u
    6 ACK    22 SYN    38 &    54 6    70 F    86 V   102 f   118 v
    7 BEL    23 ETB    39 '    55 7    71 G    87 W   103 g   119 w
    8 BS     24 CAN    40 (    56 8    72 H    88 X   104 h   120 x
    9 HT     25 EM     41 )    57 9    73 I    89 Y   105 i   121 y
   10 LF     26 SUB    42 *    58 :    74 J    90 Z   106 j   122 z
   11 VT     27 ESC    43 +    59 ;    75 K    91 [   107 k   123 {
   12 FF     28 FS     44 ,    60 <    76 L    92 \   108 l   124 |
   13 CR     29 GS     45 -    61 =    77 M    93 ]   109 m   125 }
   14 SO     30 RS     46 .    62 >    78 N    94 ^   110 n   126 ~
   15 SI     31 US     47 /    63 ?    79 O    95 _   111 o   127 DEL
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





# OhMyPosh

info



## Themes

Themes location:

```
 C:\Users\Baus\AppData\Local\Programs\oh-my-posh\themes
```

change:

```
C:\Users\Baus\Documents\PowerShell\Microsoft.PowerShell_profile.ps1.
```

init system env:

```
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\hul10.omp.json" | Invoke-Expression
```

init default:

```
'C:\Users\Baus\AppData\Local\Programs\oh-my-posh\themes\jandedobbeleer.omp.json' | Invoke-Expression
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



## Ed25519



## RSA



# -End-

