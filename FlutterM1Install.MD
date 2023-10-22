# Setting up Cocoapods on MacOS w/ M1 or M2 using ZSH

## _Homebrew_

### 1.) Install Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### 2.) Add Homebrew to PATH

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

## _Ruby On Rails_

### 1.) Install rbenv (Ruby Environment Manager)

```
brew install rbenv
```

### 2.) Add rbenv to PATH

- Add following to ~/.zshenv

```
export PATH="$HOME/.rbenv/bin:$PATH"
```

- Add the following to ~/.zshrc

```
source $HOME/.zshenv
eval "$(rbenv init - zsh)"
```

### 3.) Install new version of Ruby

```
rbenv install 2.7.2
```

### 4.) Update Global environment to newly downloaded version

```
rbenv global 2.7.2
```

### 5.) Restart Terminal and check Ruby Version

```
ruby -v
```

## _Cocoapods_

### 1.) Install Cocoapods

```
sudo gem install cocoapods

```

### 2.) Fix ActiveSupport issue with Cocoapods

```
sudo gem uninstall activesupport
sudo gem install activesupport -v 7.0.8
```

### 3.) Fix ffi for M1 or M2

```
sudo gem uninstall ffi && sudo gem install ffi -- --enable-libffi-alloc

```
