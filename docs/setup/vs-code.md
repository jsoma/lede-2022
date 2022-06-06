# Setting up Visual Studio Code

## Installing recommended software

Any time VS Code helpfully suggests that it can install something, **just say yes!** Python support, a linter, extensions to help you with such-and-such filetype, you don't need to know what it's for, just trust that VS Code is probably giving you good advice.

## The `code` command

!!! warning

    This is for OS X only! The `code` command comes preinstalled on Windows, so you don't need to run a command.

There's a magic command called `code` that you can install through VS Code.

1. Open the **Command Palette** by pressing `Cmd+Shift+P` and type `shell command` to filter the big long list of commands.
2. Click **Shell Command: Install 'code' command in PATH** to... install the `code` command!

That's it, you're done! If you have a command line open you'll need to restart it, though.

## The settings menu

The settings menu allows you to adjust how VS Code works. There are a lot of them, so it's a great place to become acquainted with.

=== "OS X"

    You can get to the settings menu by going to the top menu and selecting **Code > Preferences > Settings**.

=== "Windows"

    You can get to the settings menu by going to the top menu and selecting **File > Preferences > Settings**.

To search, you just type in the search bar at the top and the list of settings is filtered.

### Disable autocomplete on enter

Sometimes VS Code tries to be a little too helpful in suggesting code to you. This turns that off.

1. Search in settings for `enter`.
2. Set **Editor: Accept Suggestions on Enter** to **off**.

### Set tabs as spaces

This one should already be set up, but we can make sure.

1. Search for `tab space`.
2. Make sure **Editor: Insert Spaces** is checked.

### CAN YOU TRUST THIS FOLDER?

VS Code likes to ask if you can trust the files you're opening. Yes, you can!

If you get irritated that it keeps asking again and again and again, we can completely disable the prompt:

1. Search in settings for `trust`.
2. Under **Security > Workspace > Trust**, make sure "Controls whether or not workspace trust is enabled within VS Code" is **unchecked**.

## What else?

You might find these links useful:

* [Getting Started with the VS Code visual interface](https://code.visualstudio.com/docs/getstarted/userinterface)
* [More user/workspace settings](https://code.visualstudio.com/docs/getstarted/settings)