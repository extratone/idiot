---
share: true
dg-publish: true
---
# 30 things you can do in Mac Terminal
![](30%20things%20you%20can%20do%20in%20Mac%20Terminal/terminal-on-the-mac_thumb800.jpg)
When launched Terminal provides a line interface that you can use to control parts of the macOS interface - essentially it gives you access to the UNIX features that lie beyond the macOS skin. Here we will be looking at some projects that you can try out in Terminal, using your new-found skills.

If you're new to Terminal, or need to brush up on your commands, the best place to start is our introductory feature which you can read here: [How to use Terminal on a Mac](https://www.macworld.co.uk/how-to/how-use-terminal-on-mac-3608274/).

Note that where you see square brackets, you need to add your own input, usually a file path or URL, without the square brackets.

## 1. Show hidden files and folders

macOs creates hidden files and folders for a variety of reasons. Most of the time, there's no reason for us to know about them or even know they exist, but if you need to track one down, you can do it with Terminal. Type:

`defaults write com.apple.finder AppleShowAllFiles -bool TRUE`

`killall Finder`

Change TRUE to FALSE when you want to hide the files again.

## 2. Copy files from one folder to another

Option dragging and dropping files to copy them from one place to another is so passe. Try Terminal's Ditto command instead.

Type: `Ditto [original folder] [new folder]`

Where 'original folder' and 'new folder' are the file paths of the source and destination of the files. To see each file's name in the Terminal window as it's copied, type '-v' after Ditto. This is the command for verbose mode.

![](30%20things%20you%20can%20do%20in%20Mac%20Terminal/image.png)
## 3. Download files without your browser

If you've got the URL of a file you need to download, but don't want to download it in Safari, Chrome, or Firefox, Terminal can help. It needs just two commands - one to set Terminal's location to your Downloads folder (or anywhere else you want to put the downloaded file) and one to download the file. To set the location, use the command below. Change 'Downloads' to a different folder if you want to, remembering that if it's not in the first level of your user directory, you'll have to type the full path - or drag the folder on to the Terminal window.

`cd ~/Downloads/`

To download the file:

`curl -O [the URL of the file]`

## 4. Disable drop shadows on a screenshot

When you use Command-Shift-4 the spacebar to take a screen grab of a window on your Mac, a drop shadow is added to the window. If you'd rather not have it, use this command to take a screen grab without drop shadow.

`$ defaults write com.apple.screencapture disable-shadow -bool TRUE`

`killall SystemUIServer`

## 5. Keep your Mac awake

Over-riding the sleep settings in Energy preferences takes just one command.

`caffeinate`

Type Ctrl-C to end the command or time limit like this

`caffeinate -u -t [number of seconds]`

## 6. Make your Mac automatically restart after a crash

When your Mac freezes or crashes, often the only resolution is to hold down the power button and wait for it to restart. Use this command to make it restart automatically when it senses a crash.

`sudo systemsetup -setrestartfreeze on`

## 7. Hide non-active apps in your Dock

Dock too crowded, use this to make it show only active apps.

`defaults write com.apple.dock static-only -bool TRUE`

`killall Dock`

## 8. Dull hidden apps in the Dock

You can go even further and make the Dock dim apps that aren't visible on screen.

`defaults write com.apple.Dock showhidden -bool TRUE`

`killall Dock`

## 9. Make holding down a key repeat characters

Here's one we really like. When you hold down a key on your Mac's keyboard, it either displays a pop up of additional characters or does nothing. Here's how to make it repeat the character you tapped, just like it used to do.

`defaults write -g ApplePressAndHoldEnabled -bool FALSE`

To undo the command, use the same command but replace 'FALSE' with 'TRUE'

## 10. Hide files and folders from view in the Finder

`chflags hidden [path of folder you want to hide]`

## 11. Play Tetris, Pong, Snake and other games

Emacs, the text editor that comes pre-installed with macOS and that can be run from terminal, has a number of Easter eggs in the form of games.

To display them, type `Emacs` then hit enter, then  `Fn` and `F10` then `t` then `g`

You'll see the available games listed and can now use the cursor keys to select them.

![](30%20things%20you%20can%20do%20in%20Mac%20Terminal/_image.png)
## 12. Write ASCII art banners

Type: `banner -w [the width of the banner in pixels] [your message]`

## 13. Enable an iOS-like power chime when connected to power

Use this to make your Mac chime like an iPhone when you plug in the charger.

`defaults write com.apple.PowerChime ChimeOnAllHardware -bool true; open /System/Library/CoreServices/PowerChime.app`

## 14. Check for macOS updates more often

To change the frequency with which your Mac checks for macOS updates from weekly to daily, type:

`defaults write com.apple.SoftwareUpdate ScheduleFrequency -int 1`

## 15. Download files without your browser

If you've got the URL of a file you need to download, but don't want to download it in Safari, Chrome, or Firefox, Terminal can help. It needs just two commands - one to set Terminal's location to your Downloads folder (or anywhere else you want to put the downloaded file) and one to download the file. To set the location, use the command below. Change 'Downloads' to a different folder if you want to, remembering that if it's not in the first level of your user directory, you'll have to type the full path - or drag the folder on to the Terminal window.

`cd ~/Downloads/`

To download the file:

`curl -O [the URL of the file]`

## 16. List the Contents of a folder

The 'ls' command displays the contents of a directory By adding '-R' it expands sub-folders. So to see all the contents of a folder, type:

`ls -R [the path of the directory]`

 
![](30%20things%20you%20can%20do%20in%20Mac%20Terminal/___image.png)
 

## 17. Restore a disk image to a volume connected to your Mac

If you have a disk image that you need to create a an actual volume from, use this command:

`$ sudo asr -restore -noverify -source /[path to diskimage] -target /[Volume you want to restore to]`

## 18. View any file's contents

If you're ever sent a file that won't open on your Mac, perhaps because you don't have an app capable of opening it, or because it's corrupt, you can view its contents in Terminal. For lots of files, like audio and video, the text you see won't mean much. For others, there may be just enough for you to parse what you need.

Type: `cat [file path]`

Tip: instead of manually typing the path to the file, you can drag it on to the Terminal window and drop it after the command.

## 19. Change the default screenshot location

You can change the place where screengrabs are saved by typing:

`defaults write com.apple.screencapture location [place where you want screen grabs saved]`

Then hit Enter and then:

`killall SystemUIServer`

And hit Enter again.

## 20. Stop apps from saving to iCloud by default

Some macOS apps like TextEdit and iWork apps save to iCloud by default. You can change that by using:

`defaults write NSGlobalDomain NSDocumentSaveNewDocumentsToCloud -bool false`

To revert to iCloud, use the same command with the flag set to 'true'

## 21. How to alter file permissions using Terminal

![](30%20things%20you%20can%20do%20in%20Mac%20Terminal/____image.png)
File permissions control which users can access and modify files and folders on your Mac. Mostly they work very well, but occasionally things go awry, like when you copy a file from one user account to another and discover you can't open in it in your account.

There are two commands we can use to change permissions; chmod, which modifies permissions for all users except the file's owner, and chown which assigns ownership to a specific user.

So, to change permissions on a file to allow anyone to access, read, and modify the file, we'd use:

`sudo chmod 777 path-to-file`

Where path-to-file is the path of the file whose permissions you want to modify. Remember, rather than type the file path, you can drag the file onto the Terminal window. To modify the permissions to allow access and reading, but prohibit changing the file, swap 777 for 644.

If you want to change permissions on all the files in a folder, drag the folder onto the Terminal window instead of a file, and type -R after the command name.

To change ownership of a file to your account, use:

`sudo chown your-short-user-name path-to-file`

## 22. Change the default for screen shots on the Mac

By default, screenshots in OS X are saved as .png files. That's usually fine, but you can change it if you need to. For example, to change the default to jpeg, type:

`defaults write com.apple.screencapture type JPG`

You can also change to PDF or TIFF using the same command and swapping your chosen format for JPG.

To change the default name for screenshots, use:

`defaults write com.apple.screencapture name "the-name-you've-chosen"; killall SystemUIServer`

Replace the-name-you've-chosen with whatever you like and screenshots will now be given that name followed by the date and time.

## 23. Watch an ASCII version of Star Wars

![](30%20things%20you%20can%20do%20in%20Mac%20Terminal/_____image.png)
This one's just for fun, but what fun! There's an ASCII version of Star Wars running on a Telnet server in The Netherlands. To watch it, use:

`telnet towel.blinkenlights.nl`

To stop it, type Ctrl-] and then 'quit'

## 24. Enable text selection in Quick Look

Quick Look is an incredibly useful tool for quickly examining the contents of a file. And while it's primarily intended for images, it can also be used to read text documents. Sadly, reading is as far as it goes. You can't select text to copy it, for example. At least, not without the help of a Terminal command. Type this to allow you to select text in Quick Look:

`defaults write com.apple.finder QLEnableTextSelection -bool TRUE; killall Finder`

We have a [complete tutorial for how to select and copy text from Quick Look previews in OS X here.](https://www.macworld.co.uk/how-to/select-copy-text-from-quick-look-previews-on-os-x-3538951/)

## 25. Disable Auto-restore in Preview using Terminal on the Mac

![](30%20things%20you%20can%20do%20in%20Mac%20Terminal/______image.png)
Do you ever open [Preview](https://www.macworld.co.uk/how-to/get-most-out-of-mac-os-x-preview-3544393/) and find that it spews open document windows all over your screen? That's the fault of Auto-restore, a feature in OS X since Lion, which saves the state Preview is in when you quit it and then reverts to that state when you open it again. So, unless you close all open documents before quitting, they'll re-open next time you launch Preview.

To prevent that, and launch Preview without any documents, use this Terminal command:

`defaults write com.apple.Preview NSQuitAlwaysKeepsWindows -bool FALSE`

To change back to the default, re-type the command, replacing FALSE with TRUE. To do the same thing in QuickTime X, replace com.apple.Preview with com.apple.QuickTimePlayerX

## 26. Make the Dock slide more quickly using Terminal on the Mac

If you use Show and Hide Dock, you'll notice that when you drag the mouse pointer onto the bottom of the screen, or whichever edge you keep the Dock, there's a delay before the Dock slides into view. You can eliminate that delay with these commands:

`defaults write com.apple.dock autohide-delay -float 0`

`killall Dock`

The '0' represents the delay before the Dock slides into view, so if you want to reduce it, but not eliminate it altogether, replace the '0' with another value, measured in seconds.

To revert to the default, type:

`defaults delete com.apple.dock autohide-delay`

`killall Dock`

You can also change the speed at which the Dock slides. Again, it's done by modifying a delay. So, to make it instant, type:

`defaults write com.apple.dock autohide-time-modifier -float 0`

`killall Dock`

To double the speed, replace the '0' with '0.5' and to keep it the way it was, use '1.'

## 27. Add a message to the login window

![](30%20things%20you%20can%20do%20in%20Mac%20Terminal/_______image.png)
Whether it's to prank other users, provide daily affirmations or inspiration to yourself, or for any other reason, there may be occasions when you want to put a message in the login window in OS X. With the help of Terminal, it's very easy. Type:

`$ sudo defaults write /Library/Preferences/com.apple.loginwindow LoginwindowText "Your message here"`

The next time you log out or restart, the message will appear in the log in window. To remove it, use:

`$ sudo defaults delete /Library/Preferences/com.apple.loginwindow`

## 28. Make your Mac speak

You can make your Mac say anything you want in the currently selected voice. To do that, use the 'Say' command, like this:

`Say "whatever you want your Mac to say"`

As soon as you hit Return, your Mac will speak the words you typed.

## 29. Get rid of Dashboard

![](30%20things%20you%20can%20do%20in%20Mac%20Terminal/________image.png)
Let's face it, who uses [Dashboard](https://www.macworld.co.uk/how-to/use-widgets-mac-3794391/) anymore? For most of us, the only clue to its continued existence is its appearance in Mission Control. If you'd like it gone completely, use this command:

`defaults write com.apple.dashboard mcx-disabled -boolean TRUE`

`killall Dock`

To bring it back, use the same command, but replace TRUE with FALSE.

## 30. Rebuild Spotlight

[Spotlight](https://www.macworld.co.uk/how-to/spotlight-search-tips-os-x-el-capitan-yosemite-3531280/) is OS X's search tool and one which is incredibly useful. Occasionally, however, it can become corrupt or stop working properly. The solution is to rebuild it. Guess what? Yes, theres a Terminal command for that too. Use:

`sudo mdutil -E /Volumes/DriveName`

Where 'DriveName' is the name of the volume whose index you want to rebuild. In most cases, this will be your startup volume, and unless you've changed it, it will be called 'Macintosh HD.' Alternatively, if you have volumes mounted on your Mac's Desktop, you can drag the one you want onto the Terminal window, and ignore '_Volumes_DriveName.'

#documentation