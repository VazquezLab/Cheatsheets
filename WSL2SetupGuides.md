Windows Subsystem for Linux (WSL) set-up guide
==============================================

Learning to navigate *nix (Linux, Unix, Mac command line) is a core skillset for all biologists. 
Due to software requirements (and bias at Penn State), we use Windows as our default operating system for lab PCs.
As such, if you want to do any serious bioinformatics, and have it be reproducible outside of your own computer, you'll need to set up and configure the Windows Subsystem for Linux.
Once configured, you will be able to run Ubuntu\* on your Windows PC without needed to have two operating systems installed! 
*(\* I'm assuming folks will use Ubuntu here, since its the most mainstream Linux distro out there. If you want to get fancy, you probably dont need this guide!)*

**Guide 1 - Official Ubuntu guide for WSL:** [https://documentation.ubuntu.com/wsl/stable/howto/install-ubuntu-wsl2/](https://documentation.ubuntu.com/wsl/stable/howto/install-ubuntu-wsl2/) 
*(Most guides have you run some code beforehand on PowerShell before jumping into `wsl --install` - if you're having any issues with the first step in this guide, try the next guide)*

**Guide 2 - Unofficial guide available via WindowsForum:** [https://windowsforum.com/threads/complete-guide-to-setting-up-wsl-2-on-windows-11.361491/](https://windowsforum.com/threads/complete-guide-to-setting-up-wsl-2-on-windows-11.361491/)
*(This is the guide I used to set up Linux on my desktop, with some consulting of the official Ubuntu guide on the side)*

**Guide 3 - Running Guppy on WSL to analyze Nanopore data:** [https://hackmd.io/@Miles/rkYKDHPsO](https://hackmd.io/@Miles/rkYKDHPsO)
*(Technically not a guide for WSL on its own, but has links to many other resources)*

Additional config options for Ubuntu on WSL2
--------------------------------------------

1. Make sure that Windows Terminal from the Microsoft Store is already installed - it should be by default, however.
2. Open up Terminal, click on the small down arrow on the tab bar on the window, and select "Settings" - you can also use the shortcut `CTRL+ ,`.
3. Under "Startup", select "Ubuntu" from the "Default profile" menu; this ensures you'll never have to look at PowerShell ever again unless you have to. **Hit "Save" at the bottom to save changes.**
4. Under "Interaction", change the following settings:
    - Set "Automatically copy selection to clipboard" to "ON"
    - Set "Default URL to use for the "Search Web" action" to "https://www.google.com/search?%22%s%22". Alternatively, you can change the search engine to whatever else you want - just not Bing, for the love of all that's holy.
    - **Hit "Save" at the bottom to save changes.**
6. Under "Color schemes", you can customize the color palette of the console window - I like to use "Ubuntu" or "Solarized Dark". **Hit "Save" at the bottom to save changes.**
7. Open up your terminal, and do the following:
    1. Create dedicated project and data directories in your home directory: `mkdir ~/{data,projects}`. If you learn nothing else in my lab, at least let this be the start of a good data hygine habit.
    2. Create an SSH key: `ssh-keygen -t ed25519 -C "<your psu.edu email here>"`. **It is EXTREMELY important to GitHub to make sure that your SSH key has a passphrase!** Just note that this shouldn't be a super-intense password - but also don't make it "P455W0RD" or something else that's trivial.
8. If you're like me and you're easily bored and need *\*shiny\** to code:
    1. Install [OhMyZSH](https://github.com/ohmyzsh/ohmyzsh)
    2. Install either [Powerline10K](https://github.com/romkatv/powerlevel10k) or [Starship](https://starship.rs/guide/).
    3. These tools work best if you also install a [NerdFont](https://www.nerdfonts.com/font-downloads) such as FiraCode. Install the font by downloading the zip file, opening up the zip archive, opening up one of the styles (e.g. `FiraCodeNerdFont-Retina.ttf`), and selecting "Install" from the window that pops up.
    4. Change the default fault for the Ubuntu Terminal by going to "Settings (`CTRL+ ,`)" > "Defaults" (under "Profile"), "Appearance" (under "Additional settings"), and then selecting your NerdFont from the "Font face" dropdown menu (Note: if you don't see the font there after installing it, you may need to close and re-open Windows Terminal first).

Setting up RStudio Server for reproducible product management
-------------------------

1. Install all dependencies needed for R, RStudio Server, Tidyverse, and WorkflowR:
```
# Source: https://medium.com/@jamie84mclaughlin/installing-r-and-the-tidyverse-on-ubuntu-20-04-60170020649b
# Source: https://kalonjilabs.com/posts/Installing-Tidyverse-on-Ubuntu/
sudo apt update
sudo apt install -y software-properties-common ca-certificates apt-transport-https gnupg dirmngr libharfbuzz-dev libfribidi-dev libgit2-dev gdebi-core pandoc texlive
```
2. While you're on the command line, make sure that you have dedicated project and data directories in your home directory: `mkdir ~/{data,projects}`.
3. Also while you're on the command line, ensure you have an SSH key generated by running: `ssh-keygen -t ed25519 -C "<your psu.edu email here>"`. **It is EXTREMELY important to GitHub to make sure that your SSH key has a passphrase!** Just note that this shouldn't be a super-intense password - but also don't make it "P455W0RD" or something else that's trivial.
4. Install R by following the instructions here: [https://lib.stat.cmu.edu/R/CRAN/](https://lib.stat.cmu.edu/R/CRAN/).
5. Install RStudio Server by following the instructions here: [https://posit.co/download/rstudio-server/](https://posit.co/download/rstudio-server/).
6. Ensure RStudio Server always runs when opening the terminal by running `sudo systemctl enable rstudio-server.service`.
7. You should now be able to access RStudio Server via your web browser at: "localhost:8787" - note that your username and password are the same as whatever you set for you username and password during the Ubuntu setup screen.
8. Once in, go to `Tools > Global Options`:
    1. Under "General", and under the "Advanced" tab, set the default project location to "~/projects" using the "Browse..." button. **Hit "Apply" at the bottom.**
    2. Under "Code", in the "Display" tab, check the "Use rainbow parentheses" box in the "Syntax" section. **Hit "Apply" at the bottom.**
    3. Under "Formatting", check the box for "Use Air for code formatting". **Hit "Apply" at the bottom.**
    4. Under "Saving" check the 4 boxes in the "General" section:
      - "Ensure that source files end with newline";
      - "Strip trailing horizontal whitespace when saving";
      - "Restore last cursor position when opening file";
      - "Reformat documents on save".
      - **Hit "Apply" at the bottom.**
    5. Under "Appearance" change the "Editor theme" to literally anything that's not white to spare your eyes - I use "Cobalt". **Hit "Apply" at the bottom.**
    6. Under "Git/SVN", check the box for "Sign git commits". **Hit "Apply" at the bottom.**
    7. If you followed my instructions to use OhMyZSH+P10k/Starship, under "Terminal" change "New terminals open with:" to "Zsh". **Hit "Apply" at the bottom.**
    8. **Hit "Apply" at the bottom and then hit "OK"**
9. In the R console window, run: `install.packages(c(("renv", "workflowr"))` to install the two most important packages in your scientific career: [`renv`](https://rstudio.github.io/renv/articles/renv.html) and [`workflowr`](https://workflowr.github.io/workflowr/).

Other useful tutorials:
-----------------------

**How to back-up your WSL instance:** [https://scottspence.com/posts/backup-ubuntu-wsl-instances](https://scottspence.com/posts/backup-ubuntu-wsl-instances)
