# Sequential Installation 2022

This is an in-order list of installations that I used to set up my M1 2021 Macbook Air.

You don't *have* to install in this order, but your life will be a lot easier if you do.

1. **Chrome**

    - Via download on website.  Did not need to choose M1 option, the installer can figure it out. Easy squeezy.

<br/>

2. **VS Code**

    - Via download on website.  Chose M1 download option.

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



**Rosetta 2**

    -

**Macdown**

    - I actually downloaded this to test something for Helen
    