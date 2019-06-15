# To add directory location to path
1. Go to /etc/paths
2. Add the path in file and press enter

# Chrome Inspector
Cmd + Option +J

# Parmenantly Export Path - 
1. Open file in submile /private/etc/paths
2. Added Path which you want and press enter

# Git Configure Terminal
Just to display git branch in terminal
```
Add to .bash_profile file
parse_git_branch() {
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u@\h \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "


Auto Completion
curl https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash -o ~/.git-completion.bash
Add to .bash_profile file
if [ -f ~/.git-completion.bash ]; then
  . ~/.git-completion.bash
fi
```

Or

Oh My Zsh Installation
```
Basic Setup
1. xcode-select --install
2. ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
3. brew doctor
4. brew install zsh

Oh My Zsh Basic Installation
Link : https://github.com/robbyrussell/oh-my-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

Auto Completion
https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md

Power Level 9k
brew tap sambadevi/powerlevel9k
brew install powerlevel9k
echo "source /usr/local/opt/powerlevel9k@0.6.3/powerlevel9k.zsh-theme" >> ~/.zshrc

Oh My Zsh Fonts
git clone https://github.com/powerline/fonts.git
$ cd fonts
$ ./install.sh

Change the Theme to “agnoster”

open ~/.zshrc
Set ZSH_THEME="agnoster" and save the file

```
