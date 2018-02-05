## Visual Studio Code (Current Fav)

> Installation: https://code.visualstudio.com/docs/setup/linux#_installation <br>
> http://vscodecandothat.com/

> Recommended Packages

* `Atom Keymap`
* `Auto Import`
* `Code Runner`
* `Debugger for Chrome`
* `Guides`
* `npm`
* `Open in browser`
* `Path intellisense`
* `Prettier` -> Also set `editor.formatOnSave: true`
* `Settings sync`
* `vscode-icons`

> Custom Syntax higlighting

```
"files.associations": {
        "*.phnx": "javascript",
        "*.phnxapp": "javascript"
    }
```

## Atom editor

> Install Atom

* sudo add-apt-repository ppa:webupd8team/atom
* sudo apt-get update
* sudo apt-get install atom

> Install packages

**Note: For any description, open same named package on `atom.io`**

* `language-babel`
* `emmet`
* `atom-beautify`
* `docblockr`
* `highlight-selected`
* `minimap`
* `minimap-highlight-selected`
* `linter` (Disabled for now)
  * `linter-eslint` (Disabled for now)
  * `linter-csslint` (Disabled for now)
* `git-blame`
* `seti-ui`
* `monokai-seti`
* `open-recent`
* `rest-client`
* `color-picker`
* `atom-comb-css`
* `merge-conflicts`
* `file-icons`
* `fonts`
* `autocomplete-paths`
* `terminal-plus`
* `atom-ide-ui`
* `ide-typescript`

> Syntax highlighting custom

```
"*":
  core:
    customFileTypes:
      "source.js.jsx": [
        "phnx"
        "phnxapp"
        "phnxdef"
      ]
```

## Sublime Text

> Following are the plugins that makes the life easier for development

#### Package Control [Link](https://sublime.wbond.net/installation)

* Easily manage adding and removing packages from Sublime

#### Babel [Link](https://github.com/babel/babel-sublime)

* Syntax highlighting for es6 codes
* Adds on top of the default JS highlighting

#### SideBar Enchancements [Link](https://github.com/titoBouzout/SideBarEnhancements/tree/st3)

* Adds lots of extra functionality to the default sidebar like - open in terminal, browser, Add folder to project

#### Emmet [Link](http://emmet.io/)

* It allows you to write html n css faster with short abbrevations
* Tab/Ctrl + E to expand abbrev

#### Git [Link](https://github.com/kemayo/sublime-text-git)

* Adds a bunch of Git commands to the command palette (Ctrl + Shift + P)

#### GitGutter [Link](https://github.com/jisaacks/GitGutter)

* Shows git diffs on the left side behind the line numbers

#### All Autocomplete [Link](https://github.com/alienhard/SublimeAllAutocomplete)

* This plugin adds auto completing ability from across all open files

#### DocBlockr [Link](https://github.com/spadgos/sublime-jsdocs)

* Helps you easily write comments by auto collecting all the params
* Trigger is /\*\* and enter

#### Javascript Beautify [Link]()

* Javascript auto format using Ctrl + Alt + F
