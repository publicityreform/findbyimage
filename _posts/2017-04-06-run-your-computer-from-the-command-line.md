---
layout: post
title:  "run your computer from the command line"
date:   2017-04-06 21:52:15 -0700
tags: [Terminal]
categories: [howto]
---

# Running Your Computer From the Command Line
=============================================

Note: *This tutorial was developed by [Lee](http://github.com/lee2sman) in 2015.*

### What is the command line?

The **command-line interface**, sometimes referred to as the CLI, is a tool into which you can type text commands to perform specific tasks—in contrast to the mouse's pointing and clicking on menus and buttons. Since you can directly control the computer by typing, many tasks can be performed more quickly, and some tasks can be automated with special commands that loop through and perform the same action on many files—saving you, potentially, loads of time in the process.

The application or user interface that accepts your typed responses and displays the data on the screen is called a **shell**, and there are many different varieties that you can choose from, but the most common these days is the **Bash** shell, which is the default on Linux and Mac systems in the **Terminal** application.

### The philosophy behind Linux and the command line

The OSX command prompt is the place where you type commands to manipulate files on your computer or launch programs that perform tasks. In some ways the command prompt is the _simplest_ kind of computer interface possible. It is likely that you are more familiar with interfaces that have windows and buttons, but the command prompt is an interface entirely driven by text input. 

You enter a command, execute it, and the command is performed. Then you can enter another command that builds off this, or does something entirely different. Writing a program for the command prompt is easier than writing a program with a graphical interface (for example windows and buttons). It is so much easier, in fact, that the majority of programs written today are written for the command line. Many of the programs written this way are customized, personal programs. This is why learning to use the command prompt will open up new worlds for you. You will have access to a wide variety of programs and technologies, many that may have been off-limit or hidden before.

### Why it's important to learn the command line

It is simple and minimalist. It is ubiquitous. Nearly every computer from OS X, Raspberry Pi to web servers, internet devices, routers and robots can be controlled through the command line, and even more devices are being created that can be interacted with that are online (through the so-called "Internet Of Things", which is a nebulous term but is driven on the back of the command line). The commandline is present on devices that don't even have a screen, mouse, internet, et cetera. Some tasks are lightyears faster (or instant) when calling the command from the command line instead of using a specific application or having to find a specific program to download from the internet. If you're working on an old or underpowered computer, this could be a gamechanger that allows you to keep and use your computer rather than letting it become garbage. 

### How to Access the Command Line on a Mac

On a Mac you acces the "Terminal" application, located inside the Utilities folder inside the Applications folder on your hard drive. You can also access the terminal from Spotlight, which looks like a magnifying glass in the top right of your menu bar. Another way to access Spotlight is through the default key macro *Command-Space.*

### How do I use the Command Line?

The terminal is ideal when you want to do things super quickly without taking minutes or sometimes hours to do the same thing inside a traditional program on your computer. Instead of opening a program, clicking around, trying to find what you need, or maybe it not having what you need, you can type a few words and in seconds be finished. 

Consider one simple example. Imagine you have a folder of images of various sizes that need to be resized in order to be compressed and placed online. Instead of going in individually and opening and closing menus and choose export and resize options for each photo in photoshop, imagine you type just 5 words in the terminal and all your photos in a single folder are resized instantly.

In addition to running programs and scripts on the command line many people use the terminal to jump between folders and move files quickly on their computer. The rest of this chapter will demonstrate how to do this. But beyond moving around on your computer without a graphical interface, the command line is also ideal for taking the output of one program and then sending it as input to another program . This is known as piping and lets you build up complex programs easily.

# Moving around in your file system

Understanding what folder you are located in is important when working on the command line. The *path* refers to the file system and series of directories (aka folders) that indicate where you are currently located in the file system. 

Your Mac's top level directory is called Macintosh HD. That's the parent or grandparent folder, if you will. It's not located inside a directory. It IS the highest level directory that everything else on your computer is located inside. In the Macintosh HD you will find the folders *Applications*, *Library*, *System* and *Users*. The *Users* folder will contain a home folder for all of the users of your system. If you don't have multiple people that use your computer each with their own logon account then you likely only have one user (for example, I have a home folder named *Lee*) in addition to a *Shared* folder.

# Your PATH

The home folder is the default location that you start in when you open the terminal. You can also test this under the finder. When you are in the finder, go to the Go Menu and choose Home and it will open that folder. 

When you are moving around the computer in your file system with the Terminal, you specify the name of the folder you want to move into or work in. Underneath the hood of your Mac is Linux buzzing away. Linux allows you to specify a **full path** or a relative location. Think of the full path as a specific address, like *500 Main Street, New York, NY 11101*. A **relative** path is exactly what it sounds like. To use our street metaphor, a relative path would sound something like *2 blocks west and 1 block north of where you're currently located*. In other words, the location specified by the relative path changes based on where you are currently located. If you're at your house and follow the directions specified by the relative path, you'll wind up in a very different location than if you were at your work address and then followed the directoions of the relative path. 

This is an important concept because you always have a choice of what path you write when working on the command line. You can specify an exact location or a relative location. **When you don't specify a path, the terminal assumes the location is the directory you are currently inside.**

Sometimes in online tutorials you'll see something that looks like this: ```path/to/file```. You will never actually type ```path/to```. It simply is trying to indicate that you'll need to replace it with the proper location on your own computer. The Mac Terminal has a cool feature to make this easier for beginners. You can drag a file or folder onto the terminal and it will fill out the exact path. Try dragging a file or folder into your terminal now and you'll see this in action.

# Your basic terminal commands

The following commands are your standard everyday workaday Bash commands for checking what folder you are located in on the computer, changing folders, listing the files in a folder, moving and copying files, and editing text files. All of the commands listed here are basic built-in programs. If you'd like to read more about any of them, remember that most Bash commands and programs have a built-in manual page. You can access it by typing ```man``` before the program you want to run. There's even a manual for the manual. You can access it by running ```man man```.

### Print Working Directory, ```pwd```

This may sound a little obtuse, but it makes sense when you learn what it does. You use this command to remind you what folder you're currently located in. As you move around files or move between directories it's easy to get lost. pwd will remind you exactly where you are.

##### Example

```pwd```

### List Files, ```ls```

I use this everyday. ```ls``` is the list function. It lists all of the files in a directory, including text files, images, audio and sub-folders, among other files. It is common to run ```ls``` with one or two flags (or options). 

##### Examples

```ls``` just outputs the content of your folder in a mass. 

```ls -1``` lists them alphabetically, each file or folder on its own line to make it easier to read. 

```ls -a``` will list all files including hidden files in the folder.

### Change Directory, ```cd```

```cd``` stands for change directory and is the workhouse function to let you navigate around the computer. Let's say you've run the ```ls``` command and you see your current directory has a directory inside it called Funnn then you would run ```cd Funnn``` to move into that directory. By the way, this is as good a place as any to let you know about two special commands. A period is a type of wildcard function in the Shell. Every directory has at least two hidden files, ```.``` and ```..``` at the very least. If you type ```cd .``` then you are not really doing anything since you're saying you want to change to the current directory you are in. ```..``` stands for the larger umbrella directory that holds the directory you are currently inside of. If you type ```cd ..``` it will take you back to one directory broader than the one you are currently located in. The tilde character ```~``` stands for your home directory. Typing ```-``` will stand in for the *previous directory* you were in prior to this.

##### Examples

```cd directoryName``` to move into the directory titled directoryName currently sitting inside the directory you are presently located in. If you type the folderName incorrectly or it doesn't exist then you'll get an error message telling you that the folder doesn't exist.

```cd ..``` will take you to the larger directory that holds the directory you are currently located in. If you were in the directory ```refrigerator``` and then you made a folder inside that called ```drawer```, maybe you have gone into that drawer with ```cd drawer``` to see its contents. If you ```cd ..``` then you will leave and go back into the directory called ```refrigerator``` from before.

```cd``` will take you to your home folder, no matter where you were before.

```cd ~	``` does the same as above, taking you to your home folder.

```cd ~/Desktop/junk``` will take you to a folder called junk located on the Desktop folder, which is sitting inside your home folder on your hard drive. Remember that the tilde means your home folder. ```junk``` is a directory I made on my computer but ```Desktop``` is already a directory built-in to OS X.

```cd -``` will take you to whatever folder you were last located in

### Copy a file, ```cp```

The command ```cp``` is used to duplicate a file, in whatever format it's already in. You specify the file you want to copy, and then give a name for what you want your copy to be called.

##### Example

```cp fileYouWantToDuplicate nameForTheDuplicateFile```

### Move a file (and/or rename a file), ```mv```

The command ```mv``` works almost exactly the same as ```cp``` but instead of copying it moves the location of a file. You specify the file you want to move, and then give the path where you want to move it. If you specify a different name, the file's contents will remain the same but the filename will change. You could even use this, for example, to just change the filename but keep it in the same folder it's located in. *Note: It's important to be mindful of what folder you are located in.*

##### Example

```mv fileYouWantToMove path/to/directoryWhereYouWantToMoveIt``` will move a file inside your current directory to a different specified folder.

```mv fileName newFileName``` will keep the file inside your folder but rename it.

### Remove a file or directory, ```rm``` and ```rmdir```

Want to get rid of a file? You could drag it to the trash, or you could use the remove command. One thing to note is that by default, using ```rm``` does not check in with you to confirm you really do want to eliminate the file. It will instantly delete it and you can't get it back. It's safer to use ```rm -i```, which will ask you to confirm each file before it's deleted. To remove a directory, you must use ```rm -d``` or ```rmdir```. **By default, you cannot delete a directory if it is not empty. You must first delete the individual files inside that directory. To force the deletion of a directory even if it has files inside it, use the option ```-f```. To recursively delete a directory as well as all of the files and directories inside it, use ```-r or -R``` but beware as this could cause you to be very unhappy if you lose files you were unexpecting. The option ```-v``` stands for verbose and indicates that more detailed information will be given about the files that were deleted.**

##### Examples

```rm filename``` to delete a file in your current directory.

```rmdir folderName``` to delete a specified directory inside your current directory.

```rm -drf folderName``` will force delete a folder as well as all of the folders and files inside of it. **Use this function with extreme care**.

### Clear your screen, ```clear```

When you need a refresh and want to clear all of your previous commands and output from your field of view, run ```clear```. It doesn't delete your history (see ```history``` below for more info on this), but it does help declutter your screen.

##### Example

```clear```

### Read a file, ```cat``` and ```less```

There are a variety of ways to access and read text in a file on the command line. The simplest is to use ```cat``` which stands for concatenate. You specify the file and it dumps the text onto the command line and exits. If you're trying to read a text file and it's too large to fit in a single screen of the terminal you will probably prefer to use ```less```. ```less``` is a reader program that lets you move back and forth in a text file. You can move forward a screen at a time by hitting the space bar or scroll down or up with the arrow keys. There are a variety of other options that you can read about if you run ```man less```. When you get to the end of the file, press *q* to exit back onto the command line.

##### Example

```cat filename.txt```

```less fileName.txt```

### History and Command Completion, ```↑``` and ```Tab ↹```

To repeat a terminal command you typed previously press the up key and it will recall the last command you typed in. If you press up again, it will recall the line you typed prior to that. And repeatedly pressing up will move further back in time. You can move back and forth in your history with the up and down arrow keys.

Another timesaver is using the tab key. If you type the first few letters of a filename or directory and press tab the command line will attempt to fill out the rest of the file or directory name. If there are multiple files with the same root, it will complete the part of the name that they share. You can then add more letters and try hitting tab to see if it will complete the file name. 

### Cancelling

There is an additional important and often-used command: Cancel. Cancel is ```Control-C```. It is a programming text convention to write Control commands with the letter capitalized even though you do not actually type a Shift-Capital Letter when you type them on the computer. So when you see ```Control-C``` or ```CTRL-C``` or ```X-C``` you should actually press the Control key, hold it down, and press the *c* key and then let go of both. 

If you are typing a command and realize you don't want it anymore, type ```Control-C``` and it will be deleted.

Similarly, if you are running a program and want to quit out of it, you can usually do so with ```Control-C``` once or several times. For example, you can exit out of the jukebox program ```play``` by typing ```Control-C``` several times in a row.

**Additional tutorials, books and information**

[An Introduction To The Command Line](http://en.flossmanuals.net/command-line/index/) - _a more extensive online open-source manual_
