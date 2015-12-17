---
layout: post
title: "Salesforce CRM Cheatsheet"
category: "blog"
---

#### Introduction
I should first point out that 8 months ago from when I started writing this, I didn't know what Salesforce was or what a pain it would be to configure and fiddle with.

With that said, I'm writing this guide as a service to anyone else using Salesforce, so they don't have to go through the same things I did.

The instructions in this guide detail exactly what needs to be done to get files from folders to a location on Salesforce, in various means and methods of doing so.

#### Requirements
 1. PC running Windows. If you're using a Mac computer or Linux, you'll be fresh out of luck, unless you have a dual boot machine. Additionally, you will need to have more than 2GB of RAM to be able to process uploads quickly.
 2. The current Salesforce Data Loader for Windows. This is found in your Salesforce organization. After logging in, click Setup, then along the left menu, click Data Management, and click Data Loader. There should be a link for downloading the program so you can install it from there.
  3. A decent programming editor, and some knowledge of its shortcuts and functionality. Notepad will not help you, nor will Notepad++. You need a text editor that allows for visual block editing. I personally use either SublimeText or MacVim / Vim for this, as both have this functionality, and you'll need it to quickly create the CSV files for you to upload. Additionally, Vim is capable of advanced regular expression substitutions, allowing for contextual searching / matching (there *is* a difference), line based substitutions (`:g/match for line/s/match for substitute/replacement/c`), and more.
   4. Some knowledge of using the command prompt in Windows, or PowerShell, if you prefer. Anything that you can easily list files using command line, since you need to be able to generate text output of the list of files you wish to upload. A good alternate setup could be to install MsysGit, which now provides a terminal emulator that defaults to using bash, but on Windows. This gives you programmatic access to how files can be listed, using the `ls` command. 
   5. You will need to have the current JRE (or JDK) installed, as the Salesforce Data Loader requires Java to run. While the default installation does provide the JRE when installed, this is not 
   6. [Optional] I'd also highly advise installing the Heroku [`force`](http://github.com/heroku/force) tool. This is useful for bulk uploads of other records, and is especially useful for anyone adding Attachment files to records. Not only is this tool more reliable, it's is a great deal more friendly to users, and also can maintain a login for a given time.

#### First Steps
Install the data loader to your PC. Once it's installed, you need to change the shortcut properties that opens it. This is needed because on its default settings, **the Dataloader GUI will not have the needed heap space to upload files at all.** This is a glaring oversight in the Data Loader's configuration. Within the properties of the shortcut, you need to add ` -Xms1024m -Xmx1596m`  after`javaw.exe"`. This forces the Java Virtual Machine running the data loader to allocate a gigabyte of RAM and 1.5 GB of heap space. The heap space is the important part, as it sets how much virtual memory Java will use, and thus how many files the Dataloader can process at once.

Now for the tricky part. You have to generate a listing of all the upload files with their absolute paths to a text file. For either Attachments or Content Version uploads, both objects have fields that require you list the path location of every file being uploaded.