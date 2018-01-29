## Initial Cleanup

* Removing useless software: `sudo apt-get remove thunderbird rhythmbox shotwell aisleriot totem`
* Update apt sources: `sudo apt-get update`
* Update already installed packages: `sudo apt-get upgrade`
* Reboot maybe required since kernel would have also updated
* Restore backup

## Installing softwares

* Direct install `sudo apt-get install git vlc gimp curl build-essential libssl-dev gnome-tweak-tool htop fonts-inconsolata`
* [Chrome](https://www.ubuntuupdates.org/ppa/google_chrome?dist=stable)
* [NVM](https://github.com/creationix/nvm#installation)
* [VS Code](https://github.com/Aftabnack/awesome-links/blob/master/WebDev/CodeEditor.md#visual-studio-code)

> Npm global installs: `yarn` `npm-check-updates`

## Other global settings

* [Gnome shell integration](https://wiki.gnome.org/Projects/GnomeShellIntegrationForChrome/Installation)
* [Workspace extension](https://extensions.gnome.org/extension/484/workspace-grid/)

## Gnome Tweak tool

* Appearance > Themes > Applications = `Radiance`
* Top Bar > [Battery %age, Date, Seconds] = toggle to on
* Workspaces
  * Change to static workspaces
  * Change to "workspances span displays"
  * Set the number of workspaces to 4.
* Extensions
  * Workspace grid settings
    * Number of rows and columns to 2
    * All toggles to off


## Git global settings

```
git config --global user.name "Aftabnack"
git config --global user.email "aftabnack@gmail.com"
git config --global credential.helper store
```
