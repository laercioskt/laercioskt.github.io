---
layout: default
---

# ULaucher + KV

This is an article that shows a way of working productively on your desktop environment, describing some alternatives for each system operation but focused on Linux with [ULaucher](https://github.com/Ulauncher/Ulauncher) and the plugin [KV](https://github.com/laercioskt/ulauncher-kv).

## Problem
Sometimes you need to do a simple operation like a multiplication of 2 numbers and you decide to open a calculator and, if you are like me - a person who likes to use keyboard more than mouse - you try to configure a shortcut to open the calculator, but if you do that for all your apps or even just for the main ones you probably will not have shortcuts enough in your keyboard, right?

But all operating system come with a shortcut to open the menu and then we can just start typing some letters like ‘calc’ and the calculator appears, so what is the problem?

Generally, opening a new app requires some additional processing and memory besides a lot of clicks and that’s why I think you should consider doing some of your operations in one place and fast by one key shortcut.

## Productivity
We will approach a tool to help be productive, but have in mind that this topic - productivity - is broader than that. Maybe sometime we could discuss more about it.

But I can say that such tool could save you a lot of time during the day, for example, when you need to translate something, do a simple calc, generate a hash for some text, count words and letters in a text, open projects in your IDE, consult passwords in your wallet or like I will show in the KV (a key value plugin for Ulaucher) session, find anything that you decided to save in the past.


## Ulaucher
[ULaucher](https://github.com/Ulauncher/Ulauncher) is a fast application launcher for Linux. It is written in Python, using GTK+. 

It has a lot of plugins that you can easily install and start using, some of them require some additional configurations but this is no big deal.

There are some alternatives ([here](https://alternativeto.net/software/ulauncher/)) for Windows ([Wox](http://www.wox.one/)), for MacOS ([Alfred](https://www.alfredapp.com/)) and another that I like very much for Linux ([Albert](https://albertlauncher.github.io/)). Albert was my favorite for a long time but the indexing processing consumes a lot of CPU.

### How to Install 
On the github page of the project has instructions, but for ubuntu users the following steps could be executed:

1. Installing required libs (if not installed):
```
apt install gdebi autoconf automake autotools-dev gir1.2-javascriptcoregtk-4.0 gir1.2-keybinder-3.0 gir1.2-notify-0.7 gir1.2-soup-2.4 gir1.2-webkit2-4.0 intltool libkeybinder-3.0-0 libsigsegv2 m4 python3-distutils python3-distutils-extra python3-levenshtein python3-lib2to3 python3-pyinotify python3-websocket autoconf-archive gnu-standards autoconf-doc libtool m4-doc devscripts python-pyinotify-doc
```

2. Download the last version:
```
https://ulauncher.io/#Download
```
current version is: ulauncher_5.10.0_all.deb

3. Install ULauncher with command:
```
gdebi ~/Downloads/ulauncher_5.10.0_all.deb
```

4. Start ULauncher from the menu.

## KV for Ulaucher
When I moved from Albert to ULauncher, a plugin that I missed was KV, the one that, afterwards, was moved to Snippets plugin, where we can’t use the launcher box to insert a key value pair, and we should open another screen to do that.

With it you could easily add a key-value in a database and find values filtering by key, so imagine that you have a document that you frequently consult during your analysis and this document is on google drive, so you could type some commands in ULauncher with KV like ```kv set diagramforanalysis https://drive.com/linktodiagram``` and than on the next time you just open the ULauncher and type ```kv diagram``` to show all your keys with the string diagram, go to the item that you want on the ULauncher list and ENTER to copy the value, the link in this case, to open in the browser.

I used it so often that I decided to implement it to ULaucher, and after some time some improvements were released with help from the community. It is written in Python and uses SQLite to persist your data in a file on the home folder with name .kv.db.

### How to Install
Open ULauncher and the configuration window, go to extensions, scroll until the end where is the option Add extension, after click on Add extension a new popup will be open and you just need to put the path of github project:
```
https://github.com/laercioskt/ulauncher-kv
```

### Backup
I recommend maintaining a backup of the file .kv.db, in case you want to use it in another workstation.

There are a lot of approaches to do a backup of a file, but I like to use Insync integrated with Google Drive, the only problem is that the current version has not an option to change the .kv.db location and the Insync just sync folders. So, to not sync the whole home folder, I create a new folder inside the Insync main folder and symbolic links to the kv file in that folder.
