# Setting Cmder as the default shell in VS Code

!!! warning "Windows only"

    This is for Windows users only! All credit goes to [Kelly Kiki](https://twitter.com/kellykiki_) for the walkthrough.

First, open up VS Code. Then click File (first tab on the top menu) > Preferences > Settings.

Using the search bar up at the top, search for `terminal.integrated.profiles.windows`, and click **Edit in settings.json**.

Now we'll define a new Cmder terminal profile and set Cmder as the default profile. First, add the line of code below to **the second-to-last line**. It tells VS Code to use Cmder as the default:

```json
    "terminal.integrated.defaultProfile.windows": "Cmder",
```

Then we need to describe how Cmder works. **On line 4**, paste the following code:

```json
        "Cmder": {
            "path": [
                "${env:windir}\\Sysnative\\cmd.exe",
                "${env:windir}\\System32\\cmd.exe"
            ],
            "env": {"CMDER_ROOT": "${env:USERPROFILE}\\Desktop\\cmder"},
            "args": [
                "/K",
                "%CMDER_ROOT%\\vendor\\bin\\vscode_init.cmd"
            ],
            "icon": "cmder",
        },
```

Change the `"CMDER_ROOT": "%userprofile%\\Desktop\\cmder"` section to point to where your Cmder actually lives. In this example, mine lives on the **Desktop**. If instead yours lived in the Documents folder, it would instead be `"CMDER_ROOT": "%userprofile%\\Documents\\cmder"`.

Overall, your settings.json should look something like the code below.

```json
{
    "terminal.integrated.profiles.windows": {
        "Cmder": {
            "path": [
                "${env:windir}\\Sysnative\\cmd.exe",
                "${env:windir}\\System32\\cmd.exe"
            ],
            "env": {"CMDER_ROOT": "${env:USERPROFILE}\\Desktop\\cmder"},
            "args": [
                "/K",
                "%CMDER_ROOT%\\vendor\\bin\\vscode_init.cmd"
            ],
            "icon": "cmder",
        },
        "PowerShell": {
            "source": "PowerShell",
            "icon": "terminal-powershell"
        },
        "Command Prompt": {
            "path": [
                "${env:windir}\\Sysnative\\cmd.exe",
                "${env:windir}\\System32\\cmd.exe"
            ],
            "args": [],
            "icon": "terminal-cmd"
        }
    },
    "terminal.integrated.defaultProfile.windows": "Cmder",
}
```

If yours is giving you squiggly lines under the text, something's probably wrong! You can probably just cut and paste what's above and replace the whole `settings.json`.

Save `settings.json` by selecting **File > Save**, then restart VS Code.