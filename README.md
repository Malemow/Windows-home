# Windows-home

---

## 先前條件

- 去 `Microsoft Store` 下載 **Powershell**
- 去 `Microsoft Store` 下載 **Windows Terminal**
- 下載字型 [Nerd-fonts](https://github.com/ryanoasis/nerd-fonts) - **Hack font**

## Windows Terminal 設定

- 啟動 -> 開啟 **Powershell**
- 外觀 -> 在索引標籤列中啟用克力材料
- 預設值 -> 外觀 -> 色彩配置 `Dark+`
- 預設值 -> 外觀 -> 字體 `Hack Nerd Font Mono`
- 預設值 -> 透明度 -> 背景不透明度 50%
- 預設值 -> 透明度 -> 啟用壓克力材料

## Install Scoop (Windows Packge Manager)

```powershell
iwr -useb get.scoop.sh | iex
```

## Install git

```powershell
winget install -e --id Git.Git
```

## Clone Project

```powershell
git clone https://github.com/Malemow/Windows-home.git ~/windows-home
```

## Move git config

```powershell
mv ~/windows-home/.gitconfig ~/
mv ~/windows-home/.gitmessage.template ~/
```

## Install base packge `Curl` `sudo` `jq` `neovim` `gcc`

```powershell
scoop install curl sudo jq
scoop install neovim gcc

```

## Set Profile

```powershell
mkdir ~/.config/powershell/
mv ~/windows-home/.config ~/

echo '. \$env:USERPROFILE\.config\powershell\user_profile.ps1' >> $PROFILE.CurrentUserCurrentHost
```

## Install Oh my Posh

```powershell
Install-Module posh-git -Scope CurrentUser -Force
scoop install oh-my-posh
```

## Install and use Node18 (nvm)

```powershell
scoop install nvm
nvm install 18
nvm use 18
```

## Install terminal icons

```powershell
Install-Module -Name Terminal-Icons -Repository PSGallery -Force
```

## Install [z `Folder Jump Packge`](https://github.com/rupa/z)

```powershell
Install-Module -Name z -Force
```

## Install PSReadLine - Autocompletion

```powershell
Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck
Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView
```

## Install fzf

```powershell
scoop install fzf ripgrep peco mingw make
Install-Module -Name PSFzf -Scope CurrentUser -Force
Set-PSFzfOption -PSReadlineChordProvider 'Ctrl+f' -PSReadlineCHordReverseHistory 'Ctrl+r'
```

## Setting Lazyvim

```powershell
scoop install ripgrep peco mingw make # lazyvim setting require packge
git clone https://github.com/Malemow/nvim-lazyvim.git $env:LOCALAPPDATA\nvim
```

## Install [fastfetch](https://github.com/fastfetch-cli/fastfetch)

```powershell
scoop install fastfetch
```

## Other setting

### [git-cz](https://github.com/streamich/git-cz)

```powershell
npm install -g git-cz # 然後新增 ~/changelog.config.js
```

## Rust

```powreshell
scoop install rustup
rustup component add rust-analyzer
```

## GO

```powershell
scoop install go
go install golang.org/x/tools/gopls@latest
```
