# Tildes, pipes and redirects

## The home directory

The symbol `~` stands for your **home directory**. This is usually `/Users/username` on a Mac and something like `c:\Users\username` on a PC. You can use this to always make sure you're talking about the right place without typing too much.

* `cd ~/Desktop` will always take you right to your desktop
* `cd ~/Downloads` will always take you right to your downloads folder
* `code ~/.bash_profile` will maybe use Visual Studio Code to open the file named `.bash_profile` that is sitting in your home directory.

So: when I say "home" you think "`~`"

## Redirecting output with >

You can use`>` to take the output of a command (or a list of commands) and save it to a file. It's called **redirecting output**. It's nice.

Let's say we want to find all of the lines in animals.txt that mention "camel" and save it to camels.txt. First we grep to display the lines, then we use > to redirect the output to a file.

```bash
grep camel animals.txt > camel.txt
```

Let's say our p key was broken, so we unfortunately could not use the `cp` (copy) command. Because we're practically geniuses, we could use `cat` and `>` instead. `cat` will display the entire file, then `>` will save that output into your file (a.k.a. redirect it to the file).

```bash
cat animals.txt > animals2.txt
```

Maybe a cunning yet overly nosy professor wants to know everything you've been typing on the command line. The `history` command displays your last however-many commands you've typed. Maybe he asks you to save your history to a file called `history.txt` on your Desktop.

```bash
history > ~/Desktop/history.txt
```

## Piping between commands with |

**Piping** - using a `|` - is taking the output from one command and sending it to another. On my keyboard, the pipe is the character you get when you hold shift and press `\`.

### Example 1

Things we know:

* We can use `grep dog animals.txt` to see all of the lines inside of `animals.txt` that contain the text dog.
* We can use `wc -l animals.txt` to count the lines inside of `animals.txt`

But what if we want to find the lines that contain `dog`, and then count those lines? Piping, obviously!

```bash
grep dog animals.txt | wc -l
```

### Example 2

Things we know:

* We can use `cat names.txt` to view a list of names in the `names.txt` file
* We can use `uniq names.txt` to get rid of adjacent lines that are the same
* We can use `sort names.txt` to put the names in alphabetical order

Maybe we want to see a list of every name in names.txt, but no repeats. We can't just use uniq, because it only removes repeats next to each other. We need to sort the list of names and then get rid of repeats.

```bash
cat names.txt | sort | uniq
```

You could also just do

```bash
sort names.txt | uniq
```

And if you wanted to see how many times each name appears? You could add the `-c` (count) flag to uniq.

```bash
sort names.txt | uniq -c
```
