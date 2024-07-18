# Mac Setup

This repository contains my dotfiles, Brewfile, and terminal config managed by [chezmoi](https://www.chezmoi.io/). The following steps are for setting up a new computer with my configuration.

1. Install [Homebrew](https://brew.sh/), paste in the default terminal:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

2. Install [chezmoi](https://www.chezmoi.io/), paste in the default terminal:

```bash
brew install chezmoi
```

3. Grab my dotfiles and apply them:

```bash
chezmoi init --apply ethanbonsignori
```

4. Install all apps from Brewfile:

```bash
brew bundle install
```

5. Open the following apps:

   - **Google Chrome**: sign in to sync bookmarks, extensions, and settings.
   - **Visual Studio Code**: sign in to sync settings and extensions.
   - **iTerm2**: set as default terminal. Open settings, General->Preferences and load preferences from custom folder or URL,
     paste: `/Users/ethan/.local/share/chezmoi/dot_config/iterm`
   - **Parsec**: sign in to sync settings and setup hosting permissions.
   - **Google Remote Desktop Host**: setup hosting permissions.
   - **Logi Options+**: setup mouse settings.
   - **Maccy**: run at startup.
   - **AltTab**: run at startup.
   - **Stretchly**: start stretchly automatically at startup.
   - **Microsoft Word**: sign into windows account.

6. Setup nvm/Node.js:

```bash
nvm install node
nvm use node
```

7. Setup Python

```bash
brew install pyenv # should be installed already with Brewfile
pyenv --version
pyenv install 3.12 # or whatever version you want
pyenv global 3.12
```

8. Setup poetry for Python package management:

```bash
brew install pipx # should be installed already with Brewfile
pipx install poetry
```

for poetry shell completions, verify poetry is listed under `plugins` in `~/.zshrc` and run the following commands in the terminal:

```bash
mkdir $ZSH_CUSTOM/plugins/poetry
poetry completions zsh > $ZSH_CUSTOM/plugins/poetry/_poetry
```
 

## System Settings

#### Appearance

- Dark mode
- Allow wallpaper tinting in windows: off
- Show scroll bars: Always
- Click in the scroll bar to: Jump to the spot that's clicked

#### Desktop & Dock

- Size: 60%
- Magnification: off
- Automatically hide and show the Dock: on
- Show suggested and recent apps in Dock: off
- Default web browser: Google Chrome

#### Displays

- Arrange external displays if using
- Select "Night Shift..."
  - Schedule: Sunset to Sunrise
  - Color Temperature: More Warm (all the way ->)

#### Notifications

- Turn off notifications for: [Game Center, Home, Google Chrome, Mail, Tips, Wallet] and any other apps that are not necessary

#### Focus

- Share across devices (default)

#### Siri & Spotlight

- Ask Siri: off

#### Keyboard
- Click "Keyboard Shortcuts..." -> Services -> Expand "Files and Folders"
  - Unselect both New Terminal options
  - Select New iTerm2 options
- Text Input -> Input Sources -> "Edit..."
  - Correct spelling automatically: off
  - Capitalize words automatically: off
  - Add period with double-space: off
  - For double quotes: "abc"
  - For single quotes: 'abc'
 
## Finder

#### Open Finder
- Press hotkey CMD+Shift+. to toggle hidden files
- Select "View"
  - Show Status Bar
  - Show Path Bar
- Right Click->"Show View Options"
  - Text Size: 14pt
  - Select "Show Item Info" and "Show icon Preview"
---

# Inspiration

<u>[Automating the Setup of a New Mac With All Your Apps, Preferences, and Development Tools - Moncef Belyamani](https://www.moncefbelyamani.com/automating-the-setup-of-a-new-mac-with-all-your-apps-preferences-and-development-tools/)

[Automate Mac OS X Configuration by using Brewfile - Satoru Sasozaki](https://medium.com/@satorusasozaki/automate-mac-os-x-configuration-by-using-brewfile-58a78ce5cc53)

[Sync iTerm2 Profile with Dotfiles Repository - Stratus3D](http://stratus3d.com/blog/2015/02/28/sync-iterm2-profile-with-dotfiles-repository/)

[renemar's dotfiles](https://github.com/renemarc/dotfiles/)
</u>
