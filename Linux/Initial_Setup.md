## Initial Cleanup

* Removing useless software: `sudo apt-get remove thunderbird rhythmbox shotwell aisleriot totem`
* Update apt sources: `sudo apt-get update`
* Update already installed packages: `sudo apt-get upgrade`
* Reboot maybe required since kernel would have also updated
* Restore backup

## Installing softwares

* Direct install `sudo apt-get install git vlc gimp curl build-essential libssl-dev gnome-tweak-tool htop fonts-inconsolata default-jdk`
* [Chrome](https://www.ubuntuupdates.org/ppa/google_chrome?dist=stable)
* [NVM](https://github.com/creationix/nvm#installation)
* [VS Code](https://github.com/Aftabnack/awesome-links/blob/master/WebDev/CodeEditor.md#visual-studio-code)

> Npm global installs: `yarn` `npm-check-updates`

## Other global settings

* [Gnome shell integration](https://wiki.gnome.org/Projects/GnomeShellIntegrationForChrome/Installation)
* [Workspace extension](https://extensions.gnome.org/extension/484/workspace-grid/)
* Run this to [increase the limit](http://stackoverflow.com/questions/16748737/grunt-watch-error-waiting-fatal-error-watch-enospc) on the number of files Linux will watch. [Here's why](https://github.com/coryhouse/react-slingshot/issues/6).

    ```
    echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
    ```

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

## Starting counter-strike

* Install wine `sudo apt-get install wine-stable`
* Install the game by exe `wine Counter-Strike.exe`
* Go into the counter-strike folder `cd ~/.wine/drive_c/Games/Counter-Strike`
* Configure the display settings `winecfg`
  * Go to `Graphics` -> select `Emulate a virtual desktop` -> Set resolution to something like 1024X768
  * Close the config
* Start the game with the following flags `wine hl.exe -steam\ -game\ cstrike\ -noipx\ -nojoy\ -noforcemparms\ -noforcemaccel\`
* Set the video options to `OpenGL` and select the above set resultion, make the display `normal`. Apply and restart.
* Options -> Advanced -> Weapon Alignments or `cl_righthand 1` in the command terminal
