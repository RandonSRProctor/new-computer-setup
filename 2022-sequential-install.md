This is an in-order list of installations that I used to set up my M1 2021 Macbook Air

1. **Chrome**
    - Via download on website.  Did not need to choose M1 option. Easy squeezy.
2. **VS Code**
    - Via download on website.  Chose M1 download option.
3. **Xcode**
    - with command: `xcode-select --install`
    - This is nice because **git** installs automatically with this.  (Hence why is not on this list)
4. **Homebrew**
    - Some old instructions online have ruby based commandt, I found out because I ran the ruby command and then got a warning saying to use the shell script instead.  Then the dang Ruby script just rolls away.  I had to hit control+C to stop the ruby script installation.  When I went install from the shell script there was an error.  I assumed it was from the half-run ruby script.  I found homebrew's uninstall command, ran the uninstall, and then was able to install with the shell script without an issue.
    - *incorrect install command* 😢 : ~~``/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"``~~
    - uninstall script: ```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/uninstall.sh)"```
    - correct install command 😁 : ```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"```
5. 