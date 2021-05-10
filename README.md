# Terminal and Git

![Image Header](https://res.cloudinary.com/ahonore42/image/upload/v1611081040/logos/cc51dfbbbc2ce9a76773196bea0126a8_a5fcbq.jpg)

## Overview
In this lesson we will be covering how to use the MacOS Terminal. If you prefer using iTerm or the VS Code Terminal, those will work as well

As a developer, you will likely be using your terminal every day to manage your workflow or execute commands to install and maintain necessary packages for applications you will be building. At the end of this lesson, we will use our terminal knowledge to build a file structure that will be used throughout the cohort.


## Objectives
*After this lesson, students will be able to:*
- Understand what the MacOS Terminal is
- Navigate MacOS using Terminal commands
- Manipulate files and folder on their machine using Terminal commands
- Use a structured file system for future repositories

## Getting Started

### What is the Terminal?

### Let's open it:
- Hit <kbd>⌘</kbd> + <kbd>Space</kbd> (Command + spacebar)
- Type "Terminal"
- Hit <kbd>return</kbd>

The terminal is a tool developers use to execute instructions to the computer. It's the developer's best friend! Through the terminal, one can navigate through files and folders with speed. We can write scripts to automate common tasks and run them in the terminal.

## Modifier keys?
- Modifier keys can be used with MacOS to execute commands directly from your keyboard. Below is a list of all keyboard shortcuts.
- MacOS Shortcut Keys: https://support.apple.com/en-us/HT201236

![Mac Keyboard Modifier Keys](https://cdn.osxdaily.com/wp-content/uploads/2018/01/apple-keyboard-modifier-keys.jpg)

## Paths

Every file or folder in a file system can be read, written, and deleted by referencing its position inside the file system. When we talk about the position of a file or a folder in a file system, we refer to its "path". There are a couple of different kinds of paths we can use to refer to a file – **absolute paths** and **relative paths**.

**Directory** is an important term that's used interchangeably with *folder*. Though they are not exactly the same thing, when we say "navigate to your project directory", think of this as "navigate to your project folder".  Here's a little more information:

_Strictly speaking, there is a difference between a directory which is a file system concept, and the graphical user interface metaphor that is used to represent it (a folder)...If one is referring to a container of documents, the term folder is more appropriate. The term directory refers to the way a structured list of document files and folders is stored on the computer. It is comparable to a telephone directory that contains lists of names, numbers and addresses and does not contain the actual documents themselves._

*Taken from [Close-To-Open Cache Consistency in the Linux NFS Client](http://www.citi.umich.edu/projects/nfs-perf/results/cel/dnlc.html)*

## What is an Absolute Path?

An absolute path is defined as the specific location of a file or folder *from the root directory*, typically shown as `/`. The root directory is the starting point from which all other folders are defined and is not normally the same as your **Home** directory, which is normally found at `/Users/[Your Username]`.

## Working with Unix Commands and File Paths

Typing `cd` - a command for "change directory" with no parameters takes us to our home directory.

```bash
cd
```

If we type in `pwd` - a command for "print working directory" from that folder, we can see where we are in relation to the root directory.

Some examples of absolute path:

```bash
/usr/local/bin/git
/etc/example.ext
/var/data/database.db

```

Notice, all these paths started from `/` directory which is a root directory for every Linux/Unix machines.

## What is a Relative Path?

A relative path is a reference to a file or folder **relative** to the current position, or the present working directory(pwd). If we are in the folder `/a/b/` and we want to open the file that has the absolute path `/a/b/c/file.txt`, we can just type:

```bash
open c/file.txt
```

or

```bash
open ./c/file.txt
```

At any time, we can also use the absolute path, by adding a slash to the beginning of the path. The absolute path is the same for a file or a folder regardless of the current working directory, but relative paths are different, depending on what directory we are in.  Directory structures are laid out like `directory/subdirectory/subsubdirectory`.

Below are some examples of using relative and absolute path for the same action:


1. My present location is `/Users/username/ga/lessons` and now I want to change directory to `/Users/username/ga`.

  * Using relative path: `cd ..`
  * Using absolute path: `cd /Users/username/ga`

2. My present location is `/Users/username/ga/lessons` and I want to change the location to `/Users/username/ga/labs`

  * Using relative path: `cd ../labs`
  * Using absolute path: `cd /Users/username/ga/labs`

## More Commands

| Command   | Explanation                                                                     |
|-----------|---------------------------------------------------------------------------------|
| `pwd`     | shows in which directory you're currently in                                    |
| `mkdir`   | creates a new directory                                                         |
| `ls`      | lists the contents of the current directory you're in                           |
| `cd`      | moves you to the specified directory*                                           |
| `cd ..`   | goes back one directory                                                         |
| `cd ~`    | takes you to your home directory                                                |
| `touch`   | creates an empty file                                                           |
| `cp`      | copies an existing specified file and pastes it with whatever name you give it  |
| `mv old/path new/path`      | moves an existing specified file to a specified destination   |
| `mv path/filename path/newname` | if paths are the same with a differeent file name, the file's name will be changed                   |
| `rm`      | deletes the specified file                                                      |
| `rm -rf`  | deletes all of the files within a directory along with the directory itself     |
| `man`     | open a help manual for a particular command                                     |
| `history` | shows the history of the commands you've typed in your terminal                 |
| `ctrl + r`| search through history of your commands (press enter to execute it)             |
| `ctrl + u`| delete command line                                                             |
| `df -h`   | displays free disk space                                                        |


*Note: If you are using Zsh, you can leave out the `cd` entirely; the directly name itself will move you into it.  

## Examples
- Copy command - `cp`
```
cp hello.txt bye.txt
```

- Move command - `mv`

moves an existing specified file to a specified destination

```
mv bye.txt ga/
```

- Manual - `man`
open a help manual for a particular command
```
man ls
```

## Group Practice
Let's put our terminal skills to the test and build a few important directories

- First, we'll `cd ~` to change directories to the root directory of our machines
- Next, let's create a new directory called `ga_seir` (or something similar) 
```
mkdir ga_seir
```
- We'll be using this as the main directory to house all of our future repositories throughout the course
- Now we'll need a directory for each unit in our cohort, why don't we try creating them all in one command? 
- `cd` into `ga_seir` first
```
mkdir unit1 unit2 unit3 unit4
```
- Let's take a look and see if all of our folders were created within the `ga_seir` directory with `ls`
- One more folder, since this might be a helpful place to have it
```
mkdir projects
```
- Perfect, why don't we add a few more directories within each unit folder to keep our work organized?
- From the root `ga_seir` folder, we can make these directories using relative path
```
mkdir unit1/lessons unit1/labs unit1/homework
```
- Let's check inside of our unit1 folder to see if the new directories were created in the right place
- `cd` into `unit1`, then use the `ls` command to see if the `lessons`, `labs`, and `homework` directories were created
- Now let's make some directories for `unit2`. We'll have to get there first, so we'll change folders with `cd ../unit2`
- Since we're now in the `unit2` directory, we can make the sub directories we need without any additional paths
```
mkdir lessons labs homework
```
- For `unit3` let's move back to the root `ga_seir` folder with a quick `cd ..` and run the same command
```
mkdir lessons labs homework
```
- Check with the `ls` command to see if they have been created
- Oh no! They're in the wrong folder! Not good, we'll have to fix that right away using the `mv` command
```
mv lessons labs homework unit3
```
- Check inside your `unit3` folder to see if they've been moved properly
- Finally, let's create the last 3 directories we need for `unit4` from the root `ga_seir` folder
```
mkdir unit4/lessons unit4/labs unit4/homework
```
- And with that, we've created an organized file structure that will allow us to keep our work organized throughout the cohort!

## A Few More Commands
- Let's create a text file with your name in the `projects` directory
```
cd projects
touch name.txt
```
- Now, we'll use a special command `echo` to add some text to our name file
- The `echo` command repeats whatever follows the command, but it can also be used to add characters to a file
```
echo "Hi, my name is <your_name>" >> name.txt
```
- What if we wanted to read that .txt file from our terminal? There's a command for that! 
- Use the `cat` command to read the .txt file we've just added characters to
```
cat name.txt
```
- Pretty cool, right? No? Well, let's remove the file we just made if it's taking up too much space on your machine
- To do this we'll be using the `rm` command
- Be VERY careful when using this command, as it will *permanently erase* whatever file follows the command, trigger safety is advised
- First, let's `ls` to be sure our `name.txt` file is in our `projects` folder. Now, we'll remove it
```
rm name.txt
```
- And it's gone forever!
- A more common use of the `rm` command is for removing entire directories at a time. To delete all of the files in a directory along with the directory itself you can use the `rm` command along with the `-rf` (recursive force) flag followed by the name of the directory where you want to delete all files.
- Always be careful when using the `rm` command
```
rm -rf directory_name
```

## Recap
In this lesson we learned about using MacOS terminal commands, which can be very powerful. Commands you'll be using most frequently include:
- `cd` change directory
- `ls` list files in a directory
- `mkdir` make a directory
- `touch` create a file within a directory
- `mv` move a file or directory to a new location
- `rm` permanently remove a file within a directory
- `rm -rf` permanently deletes all of the files within a directory along with the directory itself 

## Resources
[MacOS Terminal Commands](https://www.makeuseof.com/tag/mac-terminal-commands-cheat-sheet/)


___

# Git
Distributed Version Control using Git

## Objectives
*After this lesson, students will be able to:*
- Understand what Git is and why we need it
- Use Git to save our code

## What is Git?

![XKCD - Git, How do we use it?](https://imgs.xkcd.com/comics/git.png)

Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency. Git is easy to learn and has a tiny footprint with lightning fast performance.

Git keeps track of all your code and saves your code **locally**. *GitHub* is a service where you save your code **online**. We'll cover that later. 

Each time you save to Git, you save a version of your code. It's kind of like a video game where you can save as many times as you want. Git stores a safe version of your code that you can come back to in case something goes wrong.

## Why is Git important?

Git handles versioning our code. In simple terms, if we make a mistake, we can always revert back to the old codebase. 

Git makes it easy to share your code with other developers.

Git is a version control system (VCS), more specifically, a distributed version control system (DVCS)

## The Git Lifecycle

To understand how Git works, we need to talk about the lifecycle of a Git-tracked file.

### Staging and Commiting

There are 3 states that your file can reside in `modified`, 
`staged`, and `committed`. These states map to the different sections of a Git project.

A) `modified` means that you have changed the file in your working directory, but that's it (ie you have not committed it to
your repository yet).

B) `staged` means that you have marked a modified file in its current version
to go into your next commit snapshot. Use `git add <file name>` to `stage` files.

C) `committed` means that the data is safely stored in your local repository. Use `git commit -m 'Your message here'`.


When we add a file we are moving it from the working directory to the staging area. Commiting it means we've moved it from our staging area to our local repository.

![lifecycle](https://camo.githubusercontent.com/bd20ca544ee4372810d5de7821e23e9bed4ce7ea/68747470733a2f2f7261772e6769746875622e636f6d2f4361726c65746f6e534c414d2f6769742d776f726b73686f702f6d61737465722f2e6769746875622f72656361705f6769745f6469616772616d2e706e67)

[Image Credit](https://github.com/CarletonSLAM/git-workshop)

### First we need to initialize our Git Repository: 

1. **Initialization** — First, you need to initialize a local Git repository. This will track any changes that have been made since the creation of your *present working directory*.

You only need to initialize a directory once. You can use the following command:
```bash
git init
```

### Next there are 3 main stages of a Git-tracked file after the repository has been initialized:

1. **Add to Staging** — Once the files in your working directory are being tracked by Git, you can now add any changes to the staging area with the `git add` command.

You can use a period to add all changes in the present working directory:
```bash
git add .
```

You can also add only the changes from a specific file in your directory by writing the filename instead of a period, for example:

```bash
git add index.html
```

2. **Commit to Local Repo** - Once you're all set adding files to staging, you can commit them to your local repository with the `git commit` command. This command will commit ALL files that have been staged.

>Note: Whenever you do `git commit` you MUST add a brief message describing the commit with `-m "message text"`. So a full git commit command should look something like this:

```bash
git commit -m "Created login form frontend"
```

### Now we need to sync our local repository to our Remote/Github.

3. **Create and Add a Remote Repo** — Once you have successfully committed files to our local repository, you should push it to a remote repository (e.g. GitHub), so that you can share your code with other people and/or so that you can access your own code from other computers. 

To do this, you'll first need to set up a remote repository on GitHub. To do this, first set up an account on GitHub, then click on "create new repository." 

Once you've finished creating You can then connect your local repository to that remote repository with the `git remote add` command.

The `git remote add` command takes two arguments:
- A remote name, for example, **origin** (this is the default name. just use it)
- A remote URL, for example, https://github.com/user-name/repository-name

A real `git remote add` command might look like this:

```bash
git remote add origin https://git.generalassemb.ly/SteveVW/repo-name
```
Note the example is using **origin** which is the default. Use a different shortname when adding a remote.

4. Use `git push` to push your commits from your local branch to your remote repository.

The `git push` command takes two arguments:
- A remote name, for example, **origin**
- A branch name, for example, **master**

These are both the default names. We'll get into adding additional branches right now. In the mean time, just stick with this format. Your full command should look like this:

```bash
git push origin master
```
5. To list out the available remotes including the name and URL that Git has stored for the short name.

```bash
git remote -v
```

6. To edit an existing remote **name**, such as **origin** to a new URL.

```bash
git remote set-url origin <URL>
```

## More Git Commands

#### Git Pull

```bash
git pull origin master
```

The git pull command is used to fetch and download content from your connected remote repository and immediately update your local repository to match that content.


#### Git Clone
```bash
git clone https://github.com/user-name/repository-name.git
```
The `git clone` command allows you to copy an online repository from GitHub down to your local computer.


#### Git Status
```bash
git status
```

The `git status` command displays the state of the present working directory and the staging area. It lets you see which changes have been staged, which haven’t, and which files aren’t being tracked by Git. Status output does not show you any information regarding the committed project history. For this, you need to use `git log`.


#### Git Log
```bash
git log
```

After you have created several commits, or if you have cloned a repository with an existing commit history, you’ll probably want to look back to see what has happened. The most basic and powerful tool to do this is the `git log` command.



When you run git log in this project, you should get output that looks something like this:
```bash
$ git log
commit ca82a6dff817ec66f44342007202690a93763949
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Mon Mar 17 21:52:11 2008 -0700

    changed the version number

commit 085bb3bcb608e1e8451d4b2432f8ecbe6306e7e7
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sat Mar 15 16:40:33 2008 -0700

    removed unnecessary test

commit a11bef06a3f659402fe7563abf99ad00de2209e6
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sat Mar 15 10:31:28 2008 -0700

    first commit
```

#### Git Help
```bash
$ git help -a -g
```
This command displays help information about Git. If the option --all or -a is given, all available commands are printed. If the option --guide or -g is given, a list of the useful Git guides is also printed.

# Writing Good Git Commit Messages

![Git Commit](https://imgs.xkcd.com/comics/git_commit.png)

5 minute reading: [Writing Good Commit Messages](https://chris.beams.io/posts/git-commit/)


# Resources

- [Atlassian Learn Git](https://www.atlassian.com/git/tutorials/what-is-version-control)
- [Try Git](https://try.github.io/levels/1/challenges/1)
- [Git - the Simple Guide](http://rogerdudler.github.io/git-guide/)
- [The git book](https://git-scm.com/book/en/v2) Read chapters 1-3
