macOS setup
===========

# Install Brew
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

# Switch to Brew-provided ZSH
```sh
brew install zsh zsh-syntax-highlighting
echo /usr/local/bin/zsh | sudo tee -a /etc/shells
wget -O ~/.zshrc https://git.grml.org/f/grml-etc-core/etc/zsh/zshrc
git clone https://github.com/sindresorhus/pure.git /tmp/pure
cp /tmp/pure/async.zsh /usr/local/share/zsh/site-functions/async
cp /tmp/pure/pure.zsh /usr/local/share/zsh/site-functions/prompt_pure_setup
for f in .zshrc .zshrc.local .profile ; do cp $f ~/$f ; done
chsh -s /usr/local/bin/zsh
```

# Set up Git
```sh
for f in .gitconfig .gitignore ; do cp $f ~/$f ; done
```
