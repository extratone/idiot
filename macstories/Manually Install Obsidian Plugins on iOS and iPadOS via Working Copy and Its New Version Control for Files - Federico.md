---
share: true
dg-publish: true
---
# "Manually Install Obsidian Plugins on iOS and iPadOS via Working Copy and Its New Version Control for Files"

*26-04-2022 07:41* 

> Get help and suggestions for your iOS shortcuts and productivity apps.
Get help and suggestions for your iOS shortcuts and productivity apps.

## [Manually Install Obsidian Plugins on iOS and iPadOS via Working Copy and Its New Version Control for Files](https://club.macstories.net/posts/manually-install-obsidian-plugins-on-ios-and-ipados-via-working-copy-and-its-new-version-control-for-files)

Earlier this week [Discord member OneMorningStar](https://discord.com/channels/836622115435184162/880549416765898772/892852330662346804) brought to my attention that the latest version of [Working Copy](https://apps.apple.com/us/app/working-copy-git-client/id896694807) – the excellent Git client for iPhone and iPad I’ve been using for years – can access hidden files and folders configured as linked repositories. Naturally, I immediately started thinking about how to take advantage of this feature to simplify the process of manually installing Obsidian plugins, such as the [ones](https://club.macstories.net/posts/export-markdown-with-embeds) we [released](https://club.macstories.net/posts/markdown-insert-an-obsidian-plugin-for-creating-markdown-formatted-web-and-image-links) last [month](https://club.macstories.net/posts/todoist-tasks-an-obsidian-plugin-to-create-tasks-in-todoist-with-two-way-linking), without having to use a Mac.

But first, some context. Linked repositories are [a new functionality in Working Copy](https://twitter.com/WorkingCopyApp/status/1442499883026419716) that let you add any folder from a compatible file provider (such as iCloud Drive and local storage) as a repository in Working Copy. Essentially, you can now enable Git-like version control for *any* folder on your iPad and iPhone and treat changes to documents inside it as “commits” (in classic Git parlance) with the ability to go back in time, revert changes, and roll back to an older version of a file if you need to.

Setting up a linked repository couldn’t be easier: in the latest version of Working Copy, tap the + button in the sidebar, then click ‘Link external directory’ and pick the folder you want. That’s all there is to enabling Git version control for any folder from the Files app using Working Copy.

![](https://cdn.macstories.net/image-1633100322865.png)

As soon as I saw this update pop up on the App Store and developer Anders Borum’s [explanation on Twitter](https://twitter.com/WorkingCopyApp/status/1442500309700460547), I knew I wanted to set up a linked repo for my Obsidian vault. As [I covered before](https://club.macstories.net/posts/my-obsidian-setup-part-1-sync-core-plugins-workspaces-and-other-settings), my entire Obsidian database is a plain folder full of Markdown files located in the ‘On My iPad’ local storage provider, which gets synced to other devices via the [Obsidian Sync service](https://help.obsidian.md/Licenses+%26+add-on+services/Obsidian+Sync). In my case, the app is Obsidian, but *any* app that integrates with Files can be added to Working Copy as a linked repository. Once I added the folder of my Obsidian vault to Working Copy, I started seeing changes appear in Working Copy every time I made an edit to a note in Obsidian. For example, here’s what I see in Working Copy for edits to my ‘Dashboard’ note:

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-w2luwhrytuw6y29tlmfkb2j-1633100545397.png)

Edits from Obsidian reflected in Working Copy.

As developer Anders Borum told me, one of the nice aspects of this integration between Working Copy and external folders is that all the Git housekeeping data (usually stored inside a .git folder) will be kept inside the original app if it’s already there; if it isn’t, however, Working Copy will keep the .git directory for itself, so it doesn’t “confuse” the linked app. Essentially: if you connect an app like Obsidian to Working Copy as a linked repo, don’t worry about any .git data being copied into your Obsidian vault.

Now, like I said above, you can test this integration with apps that integrate with the modern Files framework and the open-in-place mode for folders or with apps that store their documents in Apple’s default iCloud Drive and On My iPad/iPhone locations. I have a lot of ideas on how this setup could be extended for all kinds of version control in the future, going beyond the narrow scope of Obsidian and text editors.

But back to the reason I set this up in the first place: in Working Copy, you can see the hidden folders and files you can’t normally see for the same directory in the Files app. Here, for instance, is the hidden .obsidian folder, where the app keeps user data such as plugin files, themes, and CSS snippets:

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-w2luwhrytuw6y29tlmfkb2j-1633100894665.png)

The hidden .obsidian folder as viewed in Working Copy.

Thanks to this feature, you can manually install Obsidian plugins that aren’t part of Community Plugins – such as the [three ones we released for Club MacStories+ and Premier members](https://www.macstories.net/news/ios-and-ipados-15-review-extras-ebooks-shortcuts-making-of-obsidian-plugins-safari-extension-beta-and-appstories-live/) – by dragging them as folders into the .obsidian/plugins folder. In our case, all you need to do is [get the .zip file for a plugin from Memberful](https://macstories.memberful.com/account), save it to Files, uncompress it, then manually drag it inside Working Copy. Reload Obsidian, and the app will see the new plugin folder because Working Copy communicates directly with the vault in the Files app.

![](https://cdn.macstories.net/image-1633101057803.png)

Uncompress a plugin’s .zip file then drag it into Working Copy’s linked repo to install it in Obsidian’s vault.

To make this process a little bit faster and automated for Obsidian users, I created a shortcut that takes care of saving the folder into the proper directory in your vault and prepares the new files for commit in Working Copy so you don’t have to do it manually. The shortcut is based on the new ability to pick folders (instead of documents) in Shortcuts for iOS and iPadOS 15, which [I explained in this Automation Academy lesson](https://club.macstories.net/posts/automation-academy-diving-deeper-into-shortcuts-files-actions-for-ios-and-ipados-15). It’s very easy to understand what’s going on in this shortcut:

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-w2luwhrytuw6y29tlmfkb2j-1633101336960.png)

With this shortcut, all you have to do is enter the name of your Obsidian vault as configured in Working Copy upon installing the shortcut. Then, you can run it, pick a plugin folder, and it’ll be saved in the ‘plugins’ folder via Working Copy, which communicates with Files and Obsidian. That’s it.

![](https://cdn.macstories.net/image-1633101638093.png)

Installing plugins manually with Shortcuts and Working Copy.

To confirm that you manually installed a community plugin with this shortcut, you can open Obsidian settings, hit the Community Plugins section, reload, and you’ll see the new plugin, ready to be activated:

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-w2luwhrytuw6y29tlmfkb2j-1633101690016.png)

A newly-installed plugin.

Again, we have the perfect demo for this shortcut – the three plugins we released last month to [integrate Todoist with Obsidian](https://club.macstories.net/posts/todoist-tasks-an-obsidian-plugin-to-create-tasks-in-todoist-with-two-way-linking), quickly [enter Markdown links](https://club.macstories.net/posts/markdown-insert-an-obsidian-plugin-for-creating-markdown-formatted-web-and-image-links), and [compile long documents](https://club.macstories.net/posts/export-markdown-with-embeds) with support for embedded notes.

Thanks to [Working Copy](https://apps.apple.com/us/app/working-copy-git-client/id896694807)’s latest integration with Files, I’ve been able to fix one of my longstanding annoyances with Obsidian for iOS and iPadOS. I no longer need to manually install plugins on my Mac (or Samsung Z Fold 3, which is also something I’ve done), and I can use a shortcut to make the process even faster. Until Apple adds the ability to view hidden files and folders in the Files app, this will do. You can [download my shortcut here](https://www.icloud.com/shortcuts/570ea2a3047d4df19f52e392a5545389).

[Submit a Shortcut Request](https://docs.google.com/forms/d/e/1FAIpQLSeViYJRP69lNKgbmNWqxY1iEnz851gLE375swzC12Qarm-RxA/viewform?usp=sf_link)
***

==**5996**== Words

- **[Manually Install Obsidian Plugins on iOS and iPadOS via Working Copy and Its New Version Control for Files](https://club.macstories.net/posts/manually-install-obsidian-plugins-on-ios-and-ipados-via-working-copy-and-its-new-version-control-for-files)**