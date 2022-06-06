# Installing Cmder

!!! warning

    Cmder is for *Windows users only*.

## Installing

You'll want to download Cmder from [cmder.net](https://cmder.net/). **Be sure to download the Full Version**.

Once you've downloaded Cmder, **right-click Cmder.zip and click Extract All** to extract all of the files. When the extract menu comes up, check the box that says **Show extracted files when complete**. This saves us from having to double-click the folder it makes (I’m lazy, you're lazy, we're all lazy!)

![Use the extract all menu option](cmder-03-extract-all.png)

![Select the show extracted files option](cmder-04-extract-options.png)

When extraction is complete, you can run the `Cmder` file by double-clicking it.

![Double-click Cmder to run it](cmder-05-run.png)

Now that we have it open, we're going to change some settings to make it perfect and nice and useful.

## Setting up Cmder

Click the top-left corner of the Cmdr window, and select **Settings**.

![Open the settings menu](cmder-07-open-settings.png)

Now jump through a few steps:

1. On the left-hand side, look under **Startup** and click **Tasks**
2. Select `{cmd::Cmder}` on the left hand side
3. Check the box for **Default task for new console**
4. Click **Startup dir…**

![Find the Startup dir folder](cmder-09-set-settings.png)

We’re going to find our "home directory," which is the directory with our name on it. Mine is in `C:\Users\soma\`, yours is probably somewhere similar. After you’ve clicked it, select OK and then Save settings.

![Browse to your home directory](cmder-11-browse-home-dir.png)

**Now close Cmder, and open it again.**

If everything went well, you’ll see your home directory listed. See how mine is `C:\Users\soma`? And if you type `ls` and press enter, you’ll see a list of files and folders, including `Downloads` and `Documents`. If it doesn’t work, make sure you closed Cmder and opened it again.

![When you type ls, your Cmder window will show a list of files](cmder-13-test-configuration.png)

## Installing Cmder somewhere nice

Keeping Cmder in our Downloads folder seems kind of weird, so let’s move it somewhere more convenient. I’m moving it to the **Desktop**, but you can put it anywhere you think is good. Just don't put it in **Program Files**, because Cmder hates spaces!

> Make sure you are using the cmder directory. Do not move the Cmder application or `cmder.zip`.

![Drag the Cmder folder to your desktop](cmder-15-drag-to-desktop.png)


