# TODO

## SSH

- Encrypt ssh keys and add them to the repo
- Configure

Generate a new SSH key:
```bash
mkdir -p ~/.ssh
echo "Generating SSH key"
ssh-keygen -t rsa -b 4096 -C "nikitakurpas@gmail.com"
eval "$(ssh-agent -s)"
echo "run 'pbcopy < ~/.ssh/id_rsa.pub' and paste that into GitHub"
```

## GPG

- Do I need it?

Generate a new GPG key:
```bash
echo "Generating GPG key"
gpg --full-generate-key
local gpg_key="$(gpg --list-secret-keys --keyid-format=long | grep sec | cut -d'/' -f 2 | cut -d' ' -f 1)"
echo "run 'gpg --armor --export $gpg_key | pbcopy' and paste that into GitHub"
```

## git

- Configure git user props

```bash
git config --global user.name "..."
git config --global user.email "..."
```

## iTerm 2

- Do I still need it?

```bash
echo "configuring iTerm"
# iTerm config
# Specify the preferences directory
defaults write com.googlecode.iterm2.plist PrefsCustomFolder -string "~/dotfiles/iterm2"
# Tell iTerm2 to use the custom preferences in the directory
defaults write com.googlecode.iterm2.plist LoadPrefsFromCustomFolder -bool true
# Add shell integration
curl -L https://iterm2.com/shell_integration/zsh -o ~/.iterm2_shell_integration.zsh
```

## Shell

- Sometimes `chsh` didn't work properly, snippet below

```bash
echo "setting zsh as default"
sudo sh -c "echo $(which zsh) >> /etc/shells"
chsh -s $(which zsh)
```

## System mods

```bash
# Make Chrome Two finger swipe for back and forward
defaults write com.google.Chrome AppleEnableSwipeNavigateWithScrolls -bool TRUE

# Automatically quit printer app once the print jobs complete
defaults write com.apple.print.PrintingPrefs "Quit When Finished" -bool true

# Enable the WebKit Developer Tools in the Mac App Store
defaults write com.apple.appstore WebKitDeveloperExtras -bool true

# Enable the automatic update check
defaults write com.apple.SoftwareUpdate AutomaticCheckEnabled -bool true

# Download newly available updates in background
defaults write com.apple.SoftwareUpdate AutomaticDownload -int 1

# Install System data files & security updates
defaults write com.apple.SoftwareUpdate CriticalUpdateInstall -int 1

# Turn on app auto-update
defaults write com.apple.commerce AutoUpdate -bool true
```

## Mac App Store

```bash
mas install 1278508951 # Trello
mas install 1091189122 # Bear
mas install 1289197285 # MindNode
mas install 904280696 # Things
# mas install 824171161 # Affinity Designer
mas install 1081413713 # Gif Brewery
mas install 747648890 # Telegram
mas install 539883307 # LINE
mas install 1333542190 # 1Password
mas install 1569813296 # 1Password for Safari
# mas install 1370791134 # DigiDoc 4 client
# mas install 497799835 # Xcode
# mas install 424389933 # Final Cut Pro
```