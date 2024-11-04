# External Keyboart Mouse Configuration
1. For Changing windows button to option and alt button to command
   System Preference -> Search Keyboard And Select -> After that select keyboard tab -> Modify keys Button -> Select your keyboard -> Change Option to command & Command to Option
2. Mouse Scroll
   System Preference -> Un tick scroll direction : Natural
3. For enabling zooming from keyboard
   System Preference -> Accessibility -> Zoom -> Tick Use scroll gesture with modifier keys to zoom -> Select Control key for this action	

# How to enable fingerprint in mac in iterm / terminal
```
>sudo cp /etc/pam.d/sudo_local.template /etc/pam.d/sudo_local
>Uncomment link
>#auth       sufficient     pam_tid.so
>to
>auth       sufficient     pam_tid.so
>Force write
>Esc + : + wq!
>Exit
>Open new terminal
>sudo ls -> You should see fingerprint auth now
```
# Show Hide hidden files
1. defaults write com.apple.finder AppleShowAllFiles YES
2. Press Option and right click on finder and click relaunch

# To add directory location to path
1. Go to /etc/paths
2. Add the path in file and press enter

# Chrome Inspector
Cmd + Option +J

# Parmenantly Export Path - 
1. Open file in submile /private/etc/paths
2. Added Path which you want and press enter

# Zsh Learnings
```
In ~/.zshrc
export ZSH="$HOME/.oh-my-zsh" #To export var
ZSH_THEME="powerlevel10k/powerlevel10k" # To change the theme
source ~/.p10k.zsh # Add this to the last line of ~/.zshrc

~/.p10k.zsh - has all the code
Search $#branch > 32 -> comment the line to show full branch name in terminal
```

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
- xcode-select --install
- Brew gets install in `/usr/local` if folder is empty then brew is not installed for m1/m2 `ls /opt/homebrew`
- ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
- Update brew with `brew update`
- Health check with `brew doctor`
- brew install zsh

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

Go to android studio and set terminal
/bin/zsh

Note : Zsh themes are present here /Users/username/.oh-my-zsh/themes
```

References :

https://github.com/robbyrussell/oh-my-zsh

https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md

https://github.com/bhilburn/powerlevel9k

https://github.com/powerline/fonts
