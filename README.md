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

## 下載 Scoop (Windows 套件管理器)

```powershell
iwr -useb get.scoop.sh | iex
```

## 安裝 Git

```powershell
winget install -e --id Git.Git
```

## Scoop 下載套件

```powershell
scoop install curl sudo jq
scoop install neovim gcc
scoop install oh-my-posh
scoop install nvm
scoop install fzf ripgrep peco mingw make # lazyvim 設定
# scoop install go
```

## 設定 Profile

```powershell
mkdir ~/.config/powershell/
# nvim ~/.config/powershell/user_profile.ps1
nvim $PROFILE.CurrentUserCurrentHost
```

- **$PROFILE.CurrentUserCurrentHost**

```powershell
. $env:USERPROFILE\.config\powershell\user_profile.ps1
```

## 下載 Oh my Posh

```powershell
Install-Module posh-git -Scope CurrentUser -Force
```

## 安裝 Node (nvm)

```powershell
nvm install 18
nvm use 18
```

## 安裝 Terminal Icons

```powershell
Install-Module -Name Terminal-Icons -Repository PSGallery -Force
Import-Module Terminal-Icons
```

## 安裝 [z 資料夾跳轉套件](https://github.com/rupa/z)

```powershell
Install-Module -Name z -Force
```

## 安裝 PSReadLine - Auutocompletion

```powershell
Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck
Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView
```

## 設定 fzf

```powershell
Install-Module -Name PSFzf -Scope CurrentUser -Force
Set-PSFzfOption -PSReadlineChordProvider 'Ctrl+f' -PSReadlineCHordReverseHistory 'Ctrl+r'
```

## 設定 Lazyvim

### 下載

```powershell
git clone https://github.com/Malemow/nvim-lazyvim.git $env:LOCALAPPDATA\nvim
```

## 下載 Rust

```powreshell
scoop install rustup
rustup component add rust-analyzer
```

## 下載 [git-cz](https://github.com/streamich/git-cz)

```powershell
npm install -g git-cz # 然後新增 ~/changelog.config.js
```

