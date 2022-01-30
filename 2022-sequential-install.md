# Sequential Installation and Setup - 2022

*This is an in-order list of installations, configurations, and setup steps that I used to set up my M1 2021 Macbook Air.*

*You don't *have* to set things up in this order, but your life will be a lot easier if you do.*

<br/>

## Development Essentials
---

1. **Chrome**

    - Via download on website.  Did not need to choose M1 option, the installer can figure it out. Easy squeezy.

<br/>

2. **VS Code**

    - Via download on website.  Chose M1 download option.

    - Note: As of writing this, VS Code's installer still doesn't prompt you to move the application file to your Applications folder.
    
        - This means that you might launch the app from your Downloads folder, then right click the active icon and add it to your dock, and never realize that you're always launching from your Downloads folder.  
        
        - Hilariously, you might go a while without realizing a problem, and then one day clear out your Downloads folder, and all of a sudden you don't have VS Code anymore.  (Another problem with this is that if you install PATH with VS Code and it lives in the Downloads folder, the PATH will not work after you close VS Code)

        - So the moral of this story is: upon downloading VS Code, drag the app from your downloads folder into your Applications folder.

    - After you've opened VS Code, be sure to hit `cmd+shift+P` and then type "path".  Then choose: `Shell Command: install 'code' command in PATH`



<br/>

3. **Xcode**

    - with command: `xcode-select --install`
    
    - This is nice because **git** installs automatically with this.  (Hence why **git** is not on this list)

<br/>

4. **Homebrew**

    - Install with command: ```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"```
    - At the end of installation be sure to keep an eye out for instructions to set up your PATH.  There will be a commmand that you can copy and use.
    - Unhappy path warning:

        - Some old instructions online have ruby based commandt, I found out because I ran the ruby command and then got a warning saying to use the shell script instead.  Then the dang Ruby script just rolls away.  I had to hit control+C to stop the ruby script installation.  When I went install from the shell script there was an error.  I assumed it was from the half-run ruby script.  I found homebrew's uninstall command, ran the uninstall, and then was able to install with the shell script without an issue.

        - *incorrect install command* 😢 : ~~``/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"``~~
        - uninstall script: ```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/uninstall.sh)"```

<br/>

5. **nvm (node version manager)**

    - This is particularly important (and why I made this list), there are a lot of quirks about **nvm**

    - You should install **nvm** *before* installing **node**.  If you have already installed **node**, then uninstall **node**, install **nvm**.
    - Do not use **homebrew** to install **nvm**, there are specific ways to install noted in the official nvm docs: [nvm install readme](https://github.com/nvm-sh/nvm/blob/master/README.md#install--update-script)
    - **Xcode** command line tools should be installed (as well as git, which comes with **Xcode**) before installing **nvm**.
    - Since macOS 10.15, the default shell is **zsh** and **nvm** will look for `.zshrc` to update, none is installed by default. Create one with `touch ~/.zshrc` if you have not already.
    - Used this command to install: curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

<br/>

6. **node**

    - Now that you have **nvm** installed, you can use it to install **node**: ``nvm install node``

    - To clarify, you could have installed **node** independantly of **nvm**, but nvm creates an environment in which you can easily switch between various versions of node.  For that reason, it is best to install **nvm** first, and let it handle **node** in its own way.

    - So far I have not installed **Rosetta 2**, I want to see how far I can get.  Older versions of **node** might not be compatable with M1, so for now I'm just gonna stick with modern **node** versions and leave emulation out of the picture.  (We'll see how long that lasts!)

7. **Set Up git**

    - Even though **git** is installed via **Xcode**, you still need to get your **git** account set up with your preffered remote repository hosting service- most likely GitHub.

    - The directions are thorough enough that I will not put them here, rather 


8.  **Rosetta 2**

    - I made it so far!!!  I want to try a new application called **Macdown** (next in line), and also will need to use **Discord** (in next section), and both do not currently have native M1 support.  Hopefully in the near future this entry and all **Rosetta 2** references will be completely unneessesary.

    - Via command: `softwareupdate --install-rosetta`



9. **Macdown**

    - Via homebrew command: `brew install --cask macdown`

    - As I was making this list, my wife (Helen) asked me if I could give her an app that I wrote for her that translates her excel-format medical notes into nicely presentable **markdown** files.  She doesn't have a **markdown** reader/editor, so I'm looking for one that she can use that doesn't have too many bells and whistles.

    - I've been looking for a new **markdown** editor outside of VS Code anyway, so this may or may not be considered an developer essential in the future.  I think that anyone who is reading this should already know how they like to write **markdown**, so either use this app or choose this step to install the editer of your choice.

10. **Oh My ZSH**

<br/>

11. **yarn**



## Extra-Development Essentials
---

1. **Disord**

    - Discord needs **Rosetta 2** as of writing this (Jan 30, 2022).  The good news is that there is already an Alpha that works with M1.  A little too early for me to want to use it, so I'm going to break and use **Rosetta 2**

    -

2. **Slack**

    - I am actually not installing this, I kind of hate Slack.  Putting on the list for others in case they use it.

3. **Zoom**

    - I wonder if Zoom will still be necessary in the future?  It sure seems like it won't last long.
