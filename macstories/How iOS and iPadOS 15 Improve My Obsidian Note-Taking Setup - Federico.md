---
share: true
dg-publish: true
---
# "How iOS and iPadOS 15 Improve My Obsidian Note-Taking Setup"

*26-04-2022 07:41* 

> Exploring topics beyond our day-to-day coverage.
Exploring topics beyond our day-to-day coverage.

## [How iOS and iPadOS 15 Improve My Obsidian Note-Taking Setup](https://club.macstories.net/posts/how-ios-and-ipados-15-improve-my-obsidian-note-taking-setup)

It’s been [a busy week at MacStories](https://www.macstories.net/tag/wwdc-2021/), and, like every year, I’ve spent the past few days editing stories by John and Alex (after all, isn’t this what an Editor in Chief is supposed to do?) and collecting my first notes, thoughts, and tidbits about [iOS and iPadOS 15](https://www.macstories.net/stories/ios-and-ipados-15-the-macstories-overview/). I’ve been doing all this research in [Obsidian](https://obsidian.md/) (I set it up for WWDC beforehand with a dedicated workspace and sub-folders for sessions and screenshots), which I’ve been running for the entire week on the first developer betas of iOS and iPadOS 15 on my primary devices. Much to my surprise, rather than causing unexpected issues or slowdowns in my note-taking setup, both betas have actually *improved* my Obsidian workflow in a couple notable ways.

I haven’t “officially” written about Obsidian yet because the mobile app for iPhone and iPad isn’t out of beta yet. Obsidian supporters [can install it via TestFlight](https://help.obsidian.md/Mobile+app+beta), but it’s not available on the App Store yet. However, as [I previously shared on Connected](https://www.relay.fm/connected/344), I’ve decided to go all-in with Obsidian for 2021: all my note-taking, research, and writing is happening in Obsidian, which I’ve been able to tweak to my specific needs thanks to a suite of custom plugins I’ve commissioned over the past few months. Obsidian can be an intimidating beast (particularly if you start spending too much time fiddling around with settings and custom appearance options), but it unlocks an incredible amount of power thanks to its support for Markdown and third-party plugins; I plan to write about this, and my custom setup in the app, extensively over the coming months, which will include a few special perks for Club MacStories members too.

In the meantime, what you should know is that I’m glad I chose to embrace Obsidian ahead of WWDC and the iOS review this summer because two Files-related changes in iOS and iPadOS 15 are going to considerably improve how I save and retrieve data in the app.

If you’re not aware of what Obsidian is or does (I recommend listening to [this episode of Mac Power Users](https://www.relay.fm/mpu/583) to get an idea), a good way to think about it is the following: it’s a note-taking app based on Markdown files; unlike similar alternatives, however, an Obsidian vault (the “database” of the app) is merely a front-end interface for a folder containing text files on your local filesystem.

Obsidian is, effectively, a UI for Markdown files you store in the Finder or Files app, which means that, in addition to its own scripting [features](https://help.obsidian.md/Plugins/List+of+plugins) and proprietary commands, you can indirectly enhance your workflow in the app by processing documents via your OS’ default file manager and its built-in file automation features. Changes you make to the folder containing your Markdown files will be instantly reflected in Obsidian, and vice versa. This open approach is, among other things, what makes Obsidian stand out from other note-taking apps and why I didn’t have to wait for an iOS 15-specific update to Obsidian to improve how I work with the app on my iPhone and iPad today.

The first change I want to mention is the improved Files widget. In iOS and iPadOS 15, you can configure the widget by pointing it at a specific folder of the Files app, regardless of whether it’s stored in iCloud Drive, local storage, or a compatible third-party file provider. With this new option, I was able to create a widget that displays recently edited documents in my WWDC 2021 folder in Obsidian, which I can reopen with one tap from the Home Screen.

![](https://cdn.macstories.net/8a6fd6d6-ff55-4a72-aeff-5abf0229a958-1623460075145.png)

Configuring the Files widget in iPadOS 15.

Even better, however, is the fact that the Files widget now supports drag and drop on the Home Screen. So if I ever want to quickly share a draft of an article I’m working on with someone or commit it as a new file in my GitHub repo using [Working Copy](https://apps.apple.com/us/app/working-copy-git-client/id896694807), I can just pick it up from the widget and drag it where needed. I didn’t have to wait for the Obsidian developers to design their own ‘Recent Files’ widget: because Obsidian stores everything in the Files app, I could just take advantage of what Apple prepared for iOS 15 and start using the new widget right away.

![](https://cdn.macstories.net/c0867a82-6a90-4bd7-96f2-4b9f2c128f12-1623460076782.png)

The new Files widget showing a specific folder and drag and drop on the Home Screen.

Additionally, as [I mentioned on AppStories earlier this week](https://appstories.net/episodes/224/), the new Files actions in Shortcuts have already allowed me to fundamentally rethink how I can capture text and save it in Obsidian or fetch documents from my vault and connect them with other actions in Shortcuts. In iOS and iPadOS 15, you no longer have to use a third-party utility such as [Toolbox Pro](https://appstories.net/episodes/224/) to save documents into or fetch them from arbitrary locations on the filesystem: now, you can use actions such as ‘Get Contents of Folder’ to list the contents of *any* folder from the Files app, even if it’s located outside of iCloud Drive/Shortcuts, which was a limitation of the app for a long time. Similarly, you can save new or existing files into any folder you want – just pick a destination in the ‘Save File’ action in the Shortcuts app, and you’re good to go.

![](https://cdn.macstories.net/b0fdc0e4-c26d-418c-b894-e51d0691562e-1623460533882.png)

Getting the contents of a specific folder with the updated Shortcuts app.

I’m still in the process of replacing old Toolbox Pro actions for file management with their new native iOS 15 counterparts, but I’ve already seen some initial benefits this week. As [I showed on Twitter](https://twitter.com/viticci/status/1402584511406391303?s=21), I created a shortcut that lets me quickly save slides from WWDC sessions thanks to Shortcuts’ new support for saving documents into any folder. As the video I shared on Twitter demonstrates, not only are screenshots saved into a specific /Assets/ sub-folder in my Obsidian vault (which is itself located in my iPad’s local storage and synced with [Obsidian Sync](https://obsidian.md/sync)), but an Obsidian-specific internal link to each image is also generated, allowing me to instantly drop a reference to a new image in the document I’m working on. Similarly, I also created a shortcut based on the ‘Get Contents of Folder’ action that lists all session slides I’ve saved in Obsidian and lets me pick one from the Home Screen so it gets copied to the clipboard and I can share it on Twitter.

![](https://cdn.macstories.net/16e9ce9f-2b2f-41f8-947e-7ca2bbfada6c-1623460789221.png)

Picking session slides from my Obsidian vault on the Home Screen thanks to Shortcuts.

Looking ahead at the rest of my summer and working on the iOS review, I can think of dozens of shortcuts that will help speed up my research and editing by, say, saving images into specific folders or processing chapters of the review as Markdown files. I’m going to share more details about my setup (including custom Obsidian plugins) in the near future, but the past few days with iOS and iPadOS 15 have confirmed my suspicion: rather than wreak havoc on my text editor, which usually happens with the first developer beta released at WWDC, both releases have already meaningfully improved how I work with images and Markdown in Obsidian. Ultimately, that’s why I love the app’s approach to data ownership and plain text, and I look forward to the shortcuts I’m going to build next.
***

==**6998**== Words

- **[How iOS and iPadOS 15 Improve My Obsidian Note-Taking Setup](https://club.macstories.net/posts/how-ios-and-ipados-15-improve-my-obsidian-note-taking-setup)**