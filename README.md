# FarkleProject

The code that goes with the tutorial on [jimhomme.com](https://www.jimhomme.com/)

## How to Work with the Example Code

The code examples presented in the Python tutorial on [jimhomme.com](https://www.jimhomme.com/) are available for download at 
https://github.com/jhomme/FarkleProject.

If you decide to use Git to work with the source code, then you need to install 
Git, which you can download from http://git-scm.com. The following 
command downloads the example code using Git:

```
$ git clone https://github.com/jhomme/FarkleProject.git
```

The `git clone` command creates a folder called "FarkleProject" and installs the source code from GitHub into the  FarkleProject folder 
in the current directory. This folder does not contain just 
source code. It also contains a copy of the Git repository with the entire history of changes 
made to the application.

The commit history in this repository was carefully created to match the order 
in which the tutorial presents concepts. The recommended way to work with 
the code is to check out the commits starting from the oldest, then move forward 
through the commit list as you make progress with the tutorial. As an alternative, 
GitHub will also let you download each commit as a ZIP or TAR file. I strongly recommend that you install and use Git, because if you go on and work on projects with open source and corporate developers, you will already be familiar with the world's most popular source control system. Plus, if you put your own projects on Github, they will be backed up every time you make changes to them.

Inn the first post, you will be asked to check out the initial release of the 
application, and then, at the proper places, you will be instructed to move 
forward in the history. The Git command that lets you move through the change 
history is `git checkout`. Here is an example:

```
$ git checkout 001a
```

The 001A  referenced in the command is a tag: a named point in the commit history 
of the project. All of the tags are in lower case. This repository is tagged according to the posts of the tutorial, 
so the 001a  tag used in the example sets the application files to the initial 
version used in post 001. Most posts have more than one tag associated with 
them, so, for example, tags  in the 002 post are presented in this order: 002a, 002b, 002c, and so on. 

Each new point in the tag history shows you a more complex version of the code. If you do not understand that version of the code, you may get a new understanding by downloading the previous version of the code by typing in the command that downloads that version.

When you run a `git checkout` command as just shown, Git will display a warning 
message that informs you that you are in a “detached HEAD” state. This means 
that you are not in any specific code branch that can accept new commits, but 
instead are looking at a particular commit in the middle of the change history 
of the project. There is no reason to be alarmed by this message, but you should 
keep in mind that if you make modifications to any files while in this state, 
issuing another git checkout is going to fail, because Git will not know what to 
do with the changes you’ve made. So, to be able to continue working with the 
project, you will need to revert the files that you changed back to their 
original state. The easiest way to do this is with the git reset command:

```
$ git reset --hard
```

This command will destroy any local changes you have made, so you should save 
anything you don’t want to lose before you use this command.

Besides checking out the source files for a version of the application, at 
certain points, you will need to perform additional setup tasks. For example, in 
some cases you will need to install new Python packages, or apply updates to the 
database. You will be told when these are necessary.

From time to time, you may want to refresh your local repository from the one on 
GitHub, where bug fixes and improvements may have been applied. The commands 
that achieve this are:

```
$ git fetch --all
$ git fetch --tags
$ git reset --hard origin/master
```

The git fetch commands update the commit history and the tags in 
your local repository from the remote one on GitHub. The git reset command  updates the source files on your local computer.

Be aware that any time git reset is used you will lose any 
local changes you have made.

Another useful operation is to view all the differences between two versions of 
the application. This can be very useful to understand a change in detail. From 
the command line, the `git diff` command can do this. For example, to see the 
difference between revisions 002a and 002b, use:

```
$ git diff 002a 002b
```

## Learning Git

To learn everything about Git that you could ever hope to know, check out the wonderful book at https://git-scm.com/book/en/v2/.