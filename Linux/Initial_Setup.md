## Installing R:
* Add the cran url to the /etc/apt/sources.list 
	"      http://cloud.r-project.org/bin/linux/ubuntu trusty/"
	Note: "trusty" is the identifier for Ubuntu 14.04 LTS
* Add secure keys
	`$sudo apt-key --keyserver keyserver.ubuntu.com --recv-keys E084DAB9`
* `$sudo apt-get update`
* `$sudo apt-get install r-base`

> Note: It will automatically add it to the path via this method <br>
> Note: Default location of installed R libraries are<br>
"/usr/local/lib/R/site-library"<br>
"/usr/lib/R/site-library"<br>
"/usr/lib/R/library"<br>

## Installing Java-8:
```
$sudo add-apt-repository ppa:webupd8team/java
$sudo apt-get update
$sudo apt-get install oracle-java8-installer
```

* Install other softwares via deb: Google-Chrome, Rstudio, Sublime text
* Install other softwares via tar.gz: eclipse, NodeJS, MongoDB
* Softwares that need the path to be added: NodeJS, MongoDB


## Sublime text
* `sudo add-apt-repository ppa:webupd8team/sublime-text-3`
* `sudo apt-get update`
* `sudo apt-get install sublime-text-installer`

## NVM (to manage nodejs installations)
* `sudo apt-get update`
* `sudo apt-get install build-essential libssl-dev`
* `curl -sL https://raw.githubusercontent.com/creationix/nvm/v0.31.0/install.sh -o install_nvm.sh`
* `bash install_nvm.sh`
* `nvm install 8` (This will install node)

## Eclipse - latest version
* `wget http://artfiles.org/eclipse.org//oomph/epp/neon/R2a/eclipse-inst-linux64.tar.gz`
* `tar xf eclipse-inst-linux64.tar.gz`
* `cd eclipse-installer`
* `sudo ./eclipse-inst`

    > Note: Change the installation flder to '/opt/eclipse' for the installation to be accessible by all users.<br>
    > Note: Do not install in /root folder. You will need sudo permissions to run it<br>
    > Note: VERY IMPORTANT Change the bundle pool during installation <br>
    "change the bundle pool from the hamburger menu to something like /opt/eclipse/.p2/pool. This can be done by creating a new agent in the 'Bundle pool' pop-up. This is because when installing it with sudo, the installer chooses /root/.p2/pool by default for the bundle pool location, which can't be opened by your user. After that you should be able to open eclipse from your regular user"

## Rstudio
* `sudo apt-get install gdebi-core`
* `wget https://download1.rstudio.org/rstudio-1.0.44-amd64.deb`
* `sudo gdebi rstudio-1.0.44-amd64.deb`
    
    > Note: If it asks for libgstreamer0.10-0, follow this link: https://stackoverflow.com/a/38646838/5189158
    
## Chrome
* `wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add - `
* `sudo sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'`
* `sudo apt-get update`
* `sudo apt-get install google-chrome-stable`
