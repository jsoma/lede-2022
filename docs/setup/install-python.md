# Installing and setting up Python

## Prerequisites

### Open the command line

First, you'll want to open up the command line.

=== ":fontawesome-brands-apple: OS X"

    Click the magnifying glass to open up Spotlight, then search for **Terminal**. Run it.

=== ":fontawesome-brands-windows: Windows"

    Find **Cmder**, which we [set up before](cmder.md), and run it.

### Previously installed Pythons

You can run the following command *exactly as it is written below* to list all of the Pythons your command line can see.

```bash
which -a python
```

> If it says something like `python not found`, congratulations! You have zero Pythons installed!

The first one in the list is the one that's used when `python` is typed.

This is just for reference: copy and paste the results somewhere. If we run into problems later, it might help us figure out what's going on.

=== ":fontawesome-brands-apple: OS X"

    That's it, you're good to go!

=== ":fontawesome-brands-windows: Windows"

    Another option is to use the Start Menu to open up **Add and Remove Programs**. Scroll down to find anything starting with **Python**.

    If you find any, it might make sense to uninstall them now. I've especially had issues with old Python versions fighting new Python versions on Windows.

### Package manager

One way to install software on your computer is to download software. Another way is to run commands on the command line, which uses a tool called a **package manager**.

Since we think the command line is cool, we're going to use that technique. To do that we need to install some software that allows us to install software from the command line

=== ":fontawesome-brands-apple: OS X"

    We'll be installing Homebrew from [https://brew.sh/](https://brew.sh/). They have a long line of text on their homepage that you cut and paste into Terminal, but to make your life easy I've reproduced it here:

    ```bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

    It might ask for your password by saying something like `Password: []`. Type your computer password and press enter.
    
    If you type and type and nothing shows up... **I promise, just type your password and hit enter!** The command line is hiding your typing from anyone who might be looking at your screen.

=== ":fontawesome-brands-windows: Windows"

    We'll be installing Scoop from [https://scoop.sh/](https://scoop.sh/). The front page isn't perfect, so I'll just copy the directions here:

    1. Use the Start Menu to open up Windows PowerShell. It's another command line! Windows is crazy!
    2. Copy and paste `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser` into PowerShell and press enter.
    3. It will ask you if you want to change the "Execution policy." Type `Y` and hit enter.
    4. Copy and paste `irm get.scoop.sh | iex` into PowerShell and press enter.

!!! info "Confirm it worked"

    === ":fontawesome-brands-apple: OS X"

        To confirm Homebrew was installed, type the following command to check the documentation for the `brew` command.
        
        ```bash
        brew help
        ```
        
        Did it work? Great, you're good to go.

    === ":fontawesome-brands-windows: Windows"

        To confirm Scoop was installed, type the following command to check the documentation for the `scoop` command.
        
        ```bash
        scoop help
        ```
        
        Did it work? Great, you're good to go.

### Additional software

For Homebrew (OS X) or Scoop (Windows) to work at their best, we need to install a couple other pieces of software with them.

=== ":fontawesome-brands-apple: OS X"

    ```bash
    brew install readline xz
    ```

=== ":fontawesome-brands-windows: Windows"

    ```bash
    scoop install 7zip innounp dark
    ```

What do they do? Why do we ned them? Who knows, not me! It's just ✨magic✨.

!!! info "Confirm it worked"

    Skim over what's written in the last twenty or so lines of the command line. Do you see any errors? Any "command not found?" If not, you're probably okay.

### Installing a Python installer

Now we're going to install the command `pyenv`. Pyenv allows us to juggle different Python versions easily.

For example, maybe you normally use the newest version of Python because it has great features. But then one day your colleague sends you some awful code that only works on old old old Python! Pyenv makes that process simple.

=== ":fontawesome-brands-apple: OS X"

    The traditional pyenv is [for OS X only](https://github.com/pyenv/pyenv). Install by running the command below.

    ```bash
    brew install pyenv
    ```

    **This step is only for people on OS X.** Windows folks can skip ahead.

    Now we need to make sure pyenv sets itself up every single time we open up a command line. To do this, you need to figure out what *specific* kind of command line you're using. Run the following command to find out:

    ```bash
    echo $SHELL
    ```

    What did it print out?

    === "/bin/zsh"

        Copy and paste the following command to add setup instructions to `~/.zshrc`, the setup file for the Z shell.

        ```bash
        echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
        echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
        echo 'eval "$(pyenv init -)"' >> ~/.zshrc
        source ~/.zshrc
        ```

        Be sure to hit enter after the last one!

    === "/bin/bash"

        Copy and paste the following command to add setup instructions to `~/.bash_profile`, the setup file for the Bash shell.

        ```bash
        echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
        echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile
        echo 'eval "$(pyenv init -)"' >> ~/.bash_profile
        source ~/.bash_profile
        ```

        Be sure to hit enter after the last one!

=== ":fontawesome-brands-windows: Windows"

    [pyenv for Windows](https://github.com/pyenv-win/pyenv-win) is less popular than pyenv for OS X, but it works the same way. Install by running the command below.

    ```bash
    scoop install pyenv
    ```

!!! info "Confirm it worked"

    To confirm pyenv was installed correctly, run the following command to ask for its documentation.
    
    ```
    pyenv help
    ```
    
    If it prints anything other than "command not found" you're good to go.

## Installing Python

### Installing Python 3.10.3

Python 3.10.4 is out now, **but not everything seems to work with it**. Instead we'll be going with 3.10.3.

=== ":fontawesome-brands-apple: OS X"

    The command below will install Python 3.10.3.

    ```
    pyenv install 3.10.3
    ```

=== ":fontawesome-brands-windows: Windows"

    First, we'll update pyenv to know about all of the newer versions of Python. This might take a couple minutes – don't worry, it's working! Then we'll install the Python version we're looking for.

    ```
    pyenv update
    pyenv install 3.10.3
    ```

    When you run the second command, it will pop open a Window about installing Python. Just agree to whatever it says!

    !!! info
    
        At the end of the installation there might be a button that says "Disable PATH length limit." Click it and agree to the prompt.

!!! info "Confirm it worked"

    Run the following command to see a list of versions installed by pyenv.
    
    ```bash
    pyenv versions
    ```

    You should see `3.10.3`.

### Setting 3.10.3 as the default Python

Run the following command to use pyenv to set 3.10.3 as the default Python:

```bash
pyenv global 3.10.3
```

Now you should be all set!

!!! info "Confirm it worked"

    First, run the following command to see a list of versions installed by pyenv.
    
    ```bash
    pyenv versions
    ``` 
    
    You should see `3.10.3` again, but this time it should have an asterisk next to it.

    To double check, next **close your command line and open up a new one command line.** Run the following command in the new terminal to check the version of the default Python:

    ```
    python --version
    ``` 

    It should print out **Python 3.10.3**. Note that the command is `python`, space, hyphen, hyphen, `version` (it gets mistyped a lot!).

## You're all set!

Congrats! :tada: