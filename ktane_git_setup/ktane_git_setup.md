
# How to setup git for the KTANE modkit

There are only a few steps to get your mod set up on Github. This process will change slightly depending on your operating system, but I will try my best to outline the differences when needed.

### Directory

 1. [Downloading and Installing git](#download_and_install_git)
 2. [Basic Setup](#basic_setup)
 3. [Set up the modkit with git](#set_up_the_modkit_with_git)
 4. [Updating the Repository](#updating_the_repository)

<a name="download_and_install_git"/>

## 1. Downloading and Installing git
_**You can skip this step if you already have git installed.**_
### _Debian_-based Linux (e.g., Ubuntu)
Open a new terminal window. Copy and paste the following commands into the terminal and hit <kbd>Enter</kbd>/<kbd>Return</kbd>:

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install git
    
### _Red Hat_-based linux (e.g., CentOS)
Open a new terminal window. Copy and paste the following commands into the terminal and hit <kbd>Enter</kbd>/<kbd>Return</kbd>:

    sudo yum upgrade
    sudo yum install git

### OSX (Mac)
Open a new terminal window. Copy and paste the following commands into the terminal and hit <kbd>Enter</kbd>/<kbd>Return</kbd>:

    ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    brew doctor
    
You will be offered to install the _Command Line Developer Tools_ from _Apple_. **Confirm by clicking  _Install_**. After the installation finished, continue installing _Homebrew_ by **hitting  <kbd>Enter</kbd>/<kbd>Return</kbd>** again.

Then, copy and paste the following command into the terminal and hit <kbd>Enter</kbd>/<kbd>Return</kbd>:

    brew install git

### Windows
Download _Git for Windows_ [here](https://gitforwindows.org/) and install. When installing make sure to choose a different text editor (I would recommend either nano (if possible) or [Notepad++](https://notepad-plus-plus.org/download/v7.5.6.html) (otherwise) if you have it installed). 

![Installer Screen](https://raw.githubusercontent.com/GamrCorps/KTANE-Tutorials/master/ktane_git_setup/images/1-windows-installer.png)
Also, make sure to choose `Use git from Git Bash` instead of `Use git from Windows Command Prompt` when you have the option to.

<a name="basic_setup"/>

## 2. Basic Setup
_**You can skip this step if you already have git set up and you have a GitHub account.**_
### Create a GitHub account
Go to this link and create a free GitHub account: https://github.com/join.
Make sure to keep your username and password on hand for later.
### Set up git
Open a terminal window (Linux or OSX) or Git Bash (Windows). Type the following commands into the terminal and hit <kbd>Enter</kbd>/<kbd>Return</kbd>:

    git config --global user.name "[Your Name]"
    git config --global user.email "[Your Email]"
Make sure to replace `[Your Name]` and `[Your Email]` with your name and the email address _linked to your GitHub account_, respectively.

<a name="set_up_the_modkit_with_git"/>

## 3. Set up the modkit with git
### GitHub setup
Go to https://github.com/ and log in. Now, look for the `+` icon in the top-right of the screen and click `New repository`.

![GitHub Repo Setup](https://github.com/GamrCorps/KTANE-Tutorials/raw/master/ktane_git_setup/images/3-github-repo-setup.png)
Then, give the repository a name and click `Create Repository`. Make sure to make this name meaningful, like `KTANE_[ModuleName]`, for example.

Now you should be at a screen with the phrase "Quick Setup" at the top. Copy the text in the text box for later.

![GitHub Repo link](https://github.com/GamrCorps/KTANE-Tutorials/raw/master/ktane_git_setup/images/3-github-repo-link.png)

### Modkit setup
If you don't have the modkit installed yet, navigate to the folder you want to put it in. 
 - **Linux/OSX:** Open a terminal. Type `cd [path/to/modkit/folder]`, substituting in the path to the modkit folder on your computer.
 - **Windows:** Navigate to the modkit folder. Right-click and select `Git Bash here`.
 
Then, copy and paste the following commands into the terminal and hit <kbd>Enter</kbd>/<kbd>Return</kbd>:

    git clone https://github.com/keeptalkinggame/ktanemodkit.git
    cd ktanemodkit

If you already have the modkit installed, navigate to its folder. Right-click and select `Git Bash here`.

Copy and paste the following commands into the terminal and hit <kbd>Enter</kbd>/<kbd>Return</kbd>:

    cd ktanemodkit
    rm -rf .git
    git init
    git add .
    git commit -m "Initial Commit"

Now, using the link from GitHub you found earlier (looks something like `https://github.com/GamrCorps/ktane_modkit_git_tutorial.git`), type the following commands into the terminal and hit <kbd>Enter</kbd>/<kbd>Return</kbd> after each one, replacing `[Repository Link]` with the link.

    git remote add origin [Repository Link]
    git push -u origin master
For example, mine would look like this:

    git remote add origin https://github.com/GamrCorps/ktane_modkit_git_tutorial.git
    git push -u origin master
_This will prompt you for your GitHub username and password, type those in and hit <kbd>Enter</kbd>/<kbd>Return</kbd> for each one. Note that the password you type will remain invisible while you type it._

Finally, go back to the GitHub page and refresh it. There should now be files there.

<a name="updating_the_repository"/>

## 4. Updating the repository
_**This is very important, you need to follow these steps EVERY TIME you work on your mod to make sure your mod still is uploaded correctly!**_
You don't need to do this _every_ time you change part of the module, but make sure to do it very often. In addition, you can do this either through the terminal (like the rest of the tutorial), or you can use the GUI version of git now if you are on Windows. Choose one before continuing:

### Via terminal (Linux, OSX, Windows (optionally))
#### Before you start working, make sure to _pull_ in changes from the remote repository (i.e., get latest changes).
 - **Linux/OSX:** Open a terminal. Type `cd [path/to/modkit/folder]`, substituting in the path to the modkit folder on your computer.
 - **Windows:** Navigate to the modkit folder. Right-click and select `Git Bash here`.  
 
Then, copy and paste the following command into the terminal and hit <kbd>Enter</kbd>/<kbd>Return</kbd>:

    git pull
    
You can then close the terminal.
#### After you are finished working, make sure _push_ changes to the remote repository (i.e., upload latest changes).
 - **Linux/OSX:** Open a terminal. Type `cd [path/to/modkit/folder]`, substituting in the path to the modkit folder on your computer.
 - **Windows:** Navigate to the modkit folder. Right-click and select `Git Bash here`. 

Then, copy and paste the following command into the terminal and hit <kbd>Enter</kbd>/<kbd>Return</kbd>:

    git add .

Then, type this command and hit <kbd>Enter</kbd>/<kbd>Return</kbd>, replacing `[Message]` with your _commit message_ (i.e., a short explanation of what you changed):

    git commit -m "[Message]"

Finally, copy and paste the following command into the terminal and hit <kbd>Enter</kbd>/<kbd>Return</kbd>:

    git push -u origin master
_This will prompt you for your GitHub username and password, type those in and hit <kbd>Enter</kbd>/<kbd>Return</kbd> for each one. Note that the password you type will remain invisible while you type it._

You can then close the terminal.
### Via Git GUI (Windows only)
#### Before you start working, make sure to _pull_ in changes from the remote repository (i.e., get latest changes).
Navigate to the modkit folder. Right-click and select `Git GUI here`. When it opens, go to the menu bar and click `Remote > Fetch from > origin`, then `Merge > Local merge...`:

![Fetch From Remote](https://github.com/GamrCorps/KTANE-Tutorials/raw/master/ktane_git_setup/images/4-fetch.png)

![Local Merge](https://github.com/GamrCorps/KTANE-Tutorials/raw/master/ktane_git_setup/images/4-local-merge.png)

You can then close the window.
#### After you are finished working, make sure _push_ changes to the remote repository (i.e., upload latest changes).
Navigate to the modkit folder. Right-click and select `Git GUI here`. Click the `Stage Changed` button in the bottom-left of the screen. Hit `Yes` and/or `Continue` if prompted.

Then, type your _commit message_ (i.e., a short explanation of what you changed) in the large text box.

Finally, click the `Push` button.
![Stage](https://raw.githubusercontent.com/GamrCorps/KTANE-Tutorials/master/ktane_git_setup/images/4-stage.png)

![Commit Message](https://github.com/GamrCorps/KTANE-Tutorials/raw/master/ktane_git_setup/images/4-message.png)

![Push](https://github.com/GamrCorps/KTANE-Tutorials/raw/master/ktane_git_setup/images/4-push.png)

_This may prompt you for your GitHub username and password. Enter them when prompted_

You can then close the window.


