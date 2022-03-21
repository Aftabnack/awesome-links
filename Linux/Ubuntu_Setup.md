## Initial Cleanup

* Removing useless software: `sudo apt remove thunderbird rhythmbox shotwell aisleriot totem`
* Update apt sources: `sudo apt update`
* Update already installed packages: `sudo apt upgrade`
* Reboot maybe required since kernel would have also updated
* Restore backup

## Installing softwares

* Direct install `sudo apt install git vlc gimp curl build-essential libssl-dev gnome-tweak-tool htop fonts-inconsolata`
* [Chrome](https://www.ubuntuupdates.org/ppa/google_chrome?dist=stable)
* [NVM](https://github.com/creationix/nvm#installation)
* [VS Code](https://github.com/Aftabnack/awesome-links/blob/master/WebDev/CodeEditor.md#visual-studio-code)

> Npm global installs: `yarn`
> Npx commands: `npx npm-check-updates`, `npx create-react-app <proj>`, `npx react-native init <proj>`


## Other global settings

* Install the gnome extensions client: `sudo apt install chrome-gnome-shell`
* [Gnome shell integration](https://wiki.gnome.org/Projects/GnomeShellIntegrationForChrome/Installation)
* [Workspace extension](https://extensions.gnome.org/extension/484/workspace-grid/)
* [Netspeed](https://extensions.gnome.org/extension/104/netspeed/)
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

## Android tools setup required for React Native

* Install some pre requisites: `sudo apt-get install libc6-dev-i386 lib32z1 openjdk-8-jdk`
* Download CLI tools from SDK tools only section of [this page](http://developer.android.com/sdk/index.html)
* Create a root folder `~/android`, extract the contents of downloaded zip above into this folder
* The above folder will have tools folder by default with `sdkmanager` (`~/android/tools/bin/sdkmanager`), `avdmanager` etc
* List all available packages with `sdkmanager --list --sdk_root=/home/aftab/android`
* Run the sdkmanager to download what's necessary (Refer RN page below for latest versions)
  - A target SDK version `"platforms;android-28"`
  - Latest platform tools `"platform-tools"`
  - Build tools `"build-tools;28.0.3"`
  - And an emulator image - Same image as target version with 64bit + GApps + Playstore
* Run `sdkmanager "platform-tools" "platforms;android-28" "build-tools;28.0.3" --sdk_root=/home/aftab/android`
* Run `sdkmanager "system-images;android-28;google_apis_playstore;x86_64" --sdk_root=/home/aftab/android`
* Setup bash entries for all of these

```
export ANDROID_HOME=$HOME/android
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

* Create AVD `avdmanager create avd -n <name> -k "system-images;android-28;google_apis_playstore;x86_64"`
* Edit the config file of AVD to have proper filepath for system image
  - Look for `~/.android/avd/<name>.avd/` folder
  - Edit the `config.ini` file in that folder
  - Find the entry of `image.sysdir.1` key
  - Update its value to be the fully qualified path for the image (prepend `/home/aftab/` to path)
* Start the emulator `emulator -avd <name>`

> * [React native latest android deps](https://reactnative.dev/docs/getting-started)
> * [sdkmanager docs](https://developer.android.com/studio/command-line/sdkmanager)
> * [avdmanager docs](https://developer.android.com/studio/command-line/avdmanager)
> * [Running on actual device](https://reactnative.dev/docs/running-on-device)

## Starting counter-strike

* Install wine `sudo apt install wine-stable`
* Install the game by exe `wine Counter-Strike.exe`
* Go into the counter-strike folder `cd ~/.wine/drive_c/Games/Counter-Strike`
* Configure the display settings `winecfg`
  * Go to `Graphics` -> select `Emulate a virtual desktop` -> Set resolution to something like 1024X768
  * Close the config
* Start the game with the following flags `wine hl.exe -steam\ -game\ cstrike\ -noipx\ -nojoy\ -noforcemparms\ -noforcemaccel\`
* Set the video options to `OpenGL` and select the above set resultion, make the display `normal`. Apply and restart.
* Options -> Advanced -> Weapon Alignments or `cl_righthand 1` in the command terminal
