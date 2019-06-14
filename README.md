# Mac

# To add directory location to path
1. Go to /etc/paths
2. Add the path in file and press enter

# Chrome Inspector
Cmd + Option +J

# Parmenantly Export Path - 
1. Open file in submile /private/etc/paths
2. Added Path which you want and press enter

# Display git branch in terminal

Procedure 1
```
if [ -f ~/.git-completion.bash ]; then
  . ~/.git-completion.bash
fi


parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

export PS1="\u@\h \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "
```

Procedure 2
```
xcode-select --install
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew doctor
brew install zsh

https://github.com/robbyrussell/oh-my-zsh
Basic Installation
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

git clone https://github.com/powerline/fonts.git
$ cd fonts
$ ./install.sh

Change the Theme to “agnoster”

$ open ~/.zshrc
Set ZSH_THEME="agnoster" and save the file
```
