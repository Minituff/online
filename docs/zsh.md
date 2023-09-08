# Pimp my terminal

[Oh My Zsh](https://ohmyz.sh/) is an open source, community-driven framework for managing your `Zsh` configuration.

In simple terms, `Zsh` is an alternative to the `Bash` shell which implements a lot of nice features that boost your productivity and improve your workflow. To that end, [Oh My Zsh](https://ohmyz.sh/) is a lightweight, open-source framework for managing those nice `Zsh` features - themes, plugins, aliases...

![oh-my-zsh](images/oh-my-zsh.png)


## Install Requirements

```bash
apt install zsh -y
apt install curl -y
apt install git -y
```

Verify requirements
```bash
git --version
curl --version
zsh --version && cat /etc/shells | grep zsh #(1)!
```

1. These are just 2 commands that help verify `Zsh` is installed.

## Install oh-my-zsh
```bash
yes | sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" && zsh
```

!!! note "We use the `yes` command here to accept the defaults and make `Zsh` our net default shell"

### Enable plugins

```bash
#(1)!
git clone https://github.com/zsh-users/zsh-syntax-highlighting ${ZSH_CUSTOM:=~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting  ; \

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:=~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions ; \

git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:=~/.oh-my-zsh/custom}/plugins/zsh-completions

#(2)!
omz plugin enable \
copypath \
git \
dirhistory \
extract \
z \
colorize \
command-not-found \
colored-man-pages \
sudo \
zsh-syntax-highlighting \
zsh-autosuggestions \
zsh-completions
```

1. These plugins needed to be downloaded before enabling
1. Some plugins come pre-installed with `oh-my-zsh`, they just need to be enabled
1. Here we are enabling our custom plugins

## Useful commands
Add these to your _~/.zshrc_  by using these commands:
```bash
echo 'alias ll="ls -la"' >> ~/.zshrc
echo 'alias cls="clear"' >> ~/.zshrc
omz reload
```

