# Command reference

These commands will work on both OS X and Windows, as long as Windows folks are using [Cmder](../setup/cmder.md).

## Quick Tips for Being Lazy

* **Press ↑ and ↓ to scroll through previous commands.** It can save you a lot of typing.
* Instead of typing out a long file/directory name, type the first few letters and **then press tab.** It will automatically fill in the rest of the filename. **Use this every time you’re typing *anything* on the command line.**
* On a Mac, you can drag a file or folder from Finder onto the Terminal and it will *automatically type the full path*

## Navigating directories and folders

!!! warning

    Don’t type the `[]` brackets when using the command - `cd [dirname]` means you’ll type `cd Documents`.


| Command                                                        | Description                                                                                                                                                                                                                                                |                                                                                                                              
| ------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `pwd`                                                               | "Print working directory." Prints the directory you're in. Use this to check that you’re in the directory you want                                                                                                                                                                         |                                                                                                                                      
| `cd [dirname]`                                                      | Changes directory, moves you into the folder named `dirname`                                                                                                                                                                                               |                                                                                                                                         
| `cd ..`                                                             | Moves you up one directory, e.g. from `Desktop/foundations/class-1` to `Desktop/foundations`.                                                                                                                                                              |                                                                                                                                         
| `ls`                                                                | lists subdirectories (and files). `ls -lah` is nicer, though. | 
| `find`                                                              | Tries to find a file without waiting for the database to update - can search by name, size, date modified, etc. [This is a good reference](https://www.digitalocean.com/community/tutorials/how-to-use-find-and-locate-to-search-for-files-on-a-linux-vps) | 

## Moving/editing/downloading files

!!! warning

    Don’t type the `[]` brackets when using the command - `cd [dirname]` means you’ll type `cd Documents`.


| Command                                      | Description                                                                                    |
| ------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `mv [source] [destination]`                     | Moves a file from one place to another                                                         |
| `cp [source] [destination]`                     | Copies a file from one place to another (so now you have two)                                  |
| `rm [file]`                                       | Deletes (removes) a file                                                                       |
| `mkdir [directoryname]`                           | Creates a directory                                                                            |
| `rmdir [directoryname]`                           | Deletes (removes) a directory                                                                  |
| `tar cvf [filename] [filename] [filename]...` | Compresses (zips) files up into a .tar.gz file                                                 |
| `tar xvf [filename]`                              | Extracts (unzips) a .tar.gz file                                                               |
| `curl [url]`                                      | Downloads a file, but streams it into your terminal window                                     |
| `curl -O [url]`                                   | Downloads a file, saving it                                                                    |
| `wget [url]`                                      | Downloads a file, saving it (yes, `curl` and `wget` are pretty similar) same (need to instal `wget`) |

## Looking at individual files

!!! warning

    Don’t type the `[]` brackets when using the command - `cd [dirname]` means you’ll type `cd Documents`.

| Command               | Description                                                                 |
| -------------------------- | --------------------------------------------------------------------------- |
| `cat [filename]`           | Displays the contents of a file                                             |
| `wc [filename]`            | Displays the word count of a file                                    |
| `wc -l [filename]`         | Displays the line count of a file                                    |
| `head -n 10 [filename]`    | Displays the first 10 lines of a file                                |
| `tail -n 20 [filename]`    | Displays the last 20 lines of a file                                 |
| `more [filename]`          | Displays the contents of a file one screen at a time (spacebar to continue) |
| `grep [text] [filename]` | Show all of the lines in filename that contain text                  |
| `sort`                       | Sorts the lines of a file                                                   |
| `uniq`                       | Removes duplicate adjacent lines of a file                                  |
