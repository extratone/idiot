---
share: true
dg-publish: true
---
# "Making Of: The iOS and iPadOS 15 Review"

*26-04-2022 07:41* 

> Exploring topics beyond our day-to-day coverage.
Exploring topics beyond our day-to-day coverage.

## [Making Of: The iOS and iPadOS 15 Review](https://club.macstories.net/posts/making-of-the-ios-and-ipados-15-review)

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-1632558855112.png)

As you may have guessed from my previous columns here on MacStories Weekly over the past few weeks, this year I completely changed my setup for researching, writing, and editing the iOS and iPadOS review. For the first time since I started doing these reviews with [iOS 9 in 2015](https://www.macstories.net/stories/ios-9-review/), I didn’t use a mind map. Instead, the entire review was researched, written, edited, and compiled for two different platforms (web and EPUB) using [Obsidian](https://obsidian.md/).

In this year’s Making Of story, I’ll be taking a look at the centralized setup I’ve built, plugins and shortcuts I’ve used along the way, and share some useful tips on how you can approach writing projects of similar scale with Obsidian. Let’s dive in.

### A Note on My Plugins

In this story, I’ll cover how I used three custom plugins created by [Finn Voorhees](https://twitter.com/finnvoorhees) for me to insert Markdown links, integrate Todoist with Obsidian, and compile a Markdown draft with support for notes embedded inside other notes.

You can use these plugins too. Earlier this week, we released them for [Club MacStories+ and Club Premier](https://club.macstories.net/plans) members, and they’re available for download in the [‘Downloads’ area of your Memberful dashboard](https://macstories.memberful.com/account/downloads). You can read in-depth explanations and installation instructions at the links below:

-   [Todoist Tasks: An Obsidian Plugin to Create Tasks in Todoist with Two-Way Linking](https://club.macstories.net/posts/todoist-tasks-an-obsidian-plugin-to-create-tasks-in-todoist-with-two-way-linking)
-   [Markdown Insert: An Obsidian Plugin for Creating Markdown-Formatted Web and Image Links](https://club.macstories.net/posts/markdown-insert-an-obsidian-plugin-for-creating-markdown-formatted-web-and-image-links)
-   [Export Markdown with Embeds: An Obsidian Plugin to Compile Documents with Embedded Notes](https://club.macstories.net/posts/export-markdown-with-embeds)

### Research and Notes

For the first time since I started writing annual iOS reviews, this year I didn’t split my research and note-taking workflow between multiple apps. As you may recall, in previous years I’d take initial notes in the Notes app, then I’d copy them over to a mind map in [MindNode](https://www.mindnode.com/), then I’d write the actual review in [iA Writer](https://ia.net/writer). This year, I did it all in Obsidian and took advantage of [backlinks](https://help.obsidian.md/How+to/Working+with+backlinks) and [workspaces](https://help.obsidian.md/Plugins/Workspaces) to navigate back and forth between notes and chapters.

This year, I studied my approach to WWDC notes and Obsidian beforehand, so that when the conference started, I knew how I was going to structure my research. This is something I’ve learned over the years: when you deal with massive writing projects and have a deadline, it’s better to be prepared and know how you’re going to organize your notes and research material so you can hit the ground running. My plan was simple: notes and chapters would be stored in separate folders in Obsidian; there would be [a ‘dashboard’ for my notes](https://club.macstories.net/posts/extension-284), and a main table of contents for each chapter of the review. Notes and chapters would be connected by backlinks, allowing me to seamlessly jump back and forth between research and writing for any particular feature of iOS and iPadOS.

First, I created a ‘Developer Frameworks and Sessions’ note in Obsidian. In this note, I started dropping all sorts of random technical details I discovered on Twitter and Apple’s developer website. Then, once WWDC was over, I sat down one day, opened the Apple Developer app, and marked as favorites all the sessions I found potentially interesting for the review. This allowed me to get a sense of the functionalities I needed to research more as well as the structure of the review before I even had a table of contents. I de-prioritized Safari right away because I was certain Apple wasn’t going to keep the design they initially showed off, and [I was right](https://www.macstories.net/stories/ios-and-ipados-15-the-macstories-review/15/#safari). For each of these sessions, I copied the title and pasted it as `[](title)` in Obsidian so that, when clicked, the app would create a separate, but backlinked, note for each session.

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-1632558997190.png)

My notes from WWDC sessions.

As you may have noticed from my review, this year I didn’t dwell on the technical nitty gritty of iOS and iPadOS too much, and that’s because I wanted the story to be more approachable by more people with a more conversational style. Still, despite the fewer technical parts in this year’s review, I had quite a few WWDC session notes to organize, study, and reference when writing. What I did here is, in my opinion, the most important change to my setup this year: technical notes were *completely separate* from chapters, so I could only use them as reference. In previous years with my MindNode-iA Writer setup, I’d paste the full contents of my technical notes into the mind map that also contained my personal notes and thoughts. That may seem like a subtle difference, but having technical notes intermixed with thoughts forced my brain to think those technical bits were equally important, which resulted in longer and more developer-oriented reviews. And that’s what I wanted to avoid this year.

Here’s how I “tricked” my brain into considering technical notes *research* material instead of core writing material: for each session, I created a standalone note and, at the top of it, added an internal link to the related chapter of the review. For instance, in the note for the ‘Adopt Quick Note’ session, here’s what I put at the top:

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-1632559105396.png)

With this approach, technical notes became backlinks for the main chapters. This way, when I started writing chapters and sections of the review, I could open the right sidebar, open the Backlinks section, and view all technical notes that were pointing to the section I was currently writing. For example, here’s the Notes section:

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-1632559118346.png)

In the review chapter for Notes, I could see backlinks from the developer sessions.

This may seem like a subtle change, but it signified an important shift in my approach to writing the review: rather than feeling the pressure to rewrite, in slightly more accessible prose, every technical bit of iOS and iPadOS, I could refer to those notes on the side as background information that would *inform* a different style of writing. Maybe I should have realized this years ago, but, as they say, you live and learn.

The ability to effortlessly create cross-reference links between notes in Obsidian – which is the one feature I miss most from Notes at this point, along with a ‘quick open’ command – also came in handy to create connections between notes and find common threads about overarching themes between them. For instance, when I was researching [design](https://www.macstories.net/stories/ios-and-ipados-15-the-macstories-review/3/#design) changes such as [native half-sheets](https://www.macstories.net/stories/ios-and-ipados-15-the-macstories-review/3/#more-design-changes) in apps, I could add a callback link to the technical note about Safari, which presents such sheets for bookmarks and Reading List on iPhone. When I was writing the actual review, these connections allowed me to mention apps and system features that implemented a specific functionality, which is why this year’s review is filled with links that point to other chapters and sections from the review itself (more on this later).

Of course, notes I take during the summer go beyond transcribing key details I discover during sessions. There are plenty of tidbits I discover from Twitter, Reddit, Apple’s documentation, and other places online. This is where my iOS Review Dashboard note comes in. Using the same approach I’ve already detailed in [Part 3 of the My Obsidian Setup series](https://club.macstories.net/posts/extension-284), I created a unified dashboard note for the review that acted as an inbox for my thoughts and interesting details. The structure mirrors the one I showed off last month:

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-1632559346340.png)

My iOS review dashboard.

As you can see in the screenshots, there are three main sections of the note called Tidbits Discovered, Tweets, and New Thoughts. Using a review-specific version of my [QuickAdd](https://github.com/chhoumann/quickadd) macro, I created a shortcut I could launch from the Home Screen that would trigger a macro in Obsidian.

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-1632559401570.png)

My QuickAdd macro for the iOS review note.

The macro allowed me to quickly paste a copied link or write a quick note, which I could then choose to append to a specific section of the dashboard for future processing. If I discovered an interesting detail about iOS 15, I would do this:

![](https://cdn.macstories.net/image-1632559527418.png)

Saving interesting details with QuickAdd.

Whereas if I found a tweet I wanted to save for later, I’d pick another section and the shortcut would assemble a Twitter iFrame I could paste into the ‘Tweets’ section:

![](https://cdn.macstories.net/image-1632559619956.png)

Appending tweets with QuickAdd.

Initially, I was saving all these notes with [native Files actions](https://club.macstories.net/posts/automation-academy-diving-deeper-into-shortcuts-files-actions-for-ios-and-ipados-15) by appending all of them to the bottom of my dashboard. After I discovered QuickAdd, however, I was able to build a visual menu that let me insert notes into *specific* sections of the note, which made it easier for me to see everything at a glance later.

![](https://cdn.macstories.net/image-1632559764676.png)

How I set up my QuickAdd macros.

In addition to sections for quickly appending text, the iOS review dashboard also contained a selection of ‘quick links’ at the top to easily navigate to different areas of the review. For instance, the main ‘Table of Contents’ note was the first link, followed by the ‘Developer Frameworks and Sessions’ one; then, I created and linked other notes for topics I wanted to cover separately in the ‘OS Preview’ [series on MacStories](https://www.macstories.net/tag/os-preview-2021/) and other ideas I was saving for the review. With Obsidian, all I had to do to open those notes was place the cursor inside the link and hit ⌘L to open them in a new panel (you can configure this hotkey to whatever you want).

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-1632559867602.png)

Looking back on those notes now, I’m happy we were able to execute on most of them despite how busy we got between July and August with the launch of the new Club MacStories.

During the research stage of my review, most of the research material amounts to written content in the form of technical notes, early thoughts and comments, and interesting details. There are, however, certain screenshots I want to save too since they may prove valuable down later in case I’m unable to capture them again. These usually include things like splash screens in apps, welcome messages after setup, and other messages or alerts you only see once. As in previous years, I’ve been saving these screenshots in folders categorized by beta build in the Files app; this year, I’ve also been able to reference these files in my Obsidian notes.

In Obsidian, you can reference files in your notes by using the `![](embed%20file)` syntax, in which all you have to do is reference a local file path inside square brackets – e.g. `![](Test.jpeg)` if you want to embed an image called ‘Test’. These references show up as links in editing mode, but they turn into full image previews when you switch to preview mode in Obsidian. To simplify the process of saving these screenshots and generating the proper syntax to embed them in my research notes, I created a shortcut, which [you can download here](https://www.icloud.com/shortcuts/547059ada06a4391a63572c143b680dc).

![](https://cdn.macstories.net/image-1632560000851.png)

Saving beta screenshots with Shortcuts.

The shortcut features a ‘Text’ action at the top with the number of the latest iOS 15 beta, which is used to create a sub-folder in the ‘Screenshots’ folder of my Obsidian vault. Every time Apple released a new beta, I had to update this action. Then, the shortcut would ask me for an image and give it a name. The shortcut would save the renamed image in the appropriate sub-folder, delete the original from Photos, and copy the Obsidian embed syntax to the clipboard, ready to be pasted in my research notes. I used this shortcut a lot until Apple broke the clipboard integration later on in the iOS 15 beta cycle.

### Writing, Compiling, and Saving Tasks

Writing the review, as in previous years, is mostly a matter of carving out enough time, focusing, and doing the actual work. As [I previously described here on MacStories Weekly](https://club.macstories.net/posts/using-focus-in-ipados-15-to-create-an-ios-review-home-screen), I set up a dedicated Focus and Home Screen on my iPad to help with blocking out distractions and writing as much as possible, as quickly as possible. The custom Focus really helped, but, ultimately, it’s the commitment and sense of responsibility that keeps me going. There’s no motivation like knowing that [half a million people](https://twitter.com/viticci/status/1441376845623005185) are waiting for the review. I wish I had better advice to give here, but it just comes down to this: people are expecting me to get this done, and I have to do it; the fact that I have fun doing it every year helps, too.

This year, I decided to take advantage of Obsidian’s capabilities to structure the review differently. In previous years when I was writing in iA Writer, I used to create individual files for each chapter and put everything together using a table of contents based on the app’s [content blocks](https://ia.net/writer/support/general/content-blocks). This year, I followed the same approach but took it one step further: **sections** of chapters were also standalone Markdown files. At a glance, it may look like a giant mess of text files:

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-1632560066179.png)

But it’s when you consider Obsidian’s excellent linking and [embedding capabilities](https://help.obsidian.md/How+to/Embed+files) that the structure makes a lot of sense for me. Here’s the main table of contents:

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-1632560115788.png)

And here’s a chapter:

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-1632560129435.png)

This structure is based on another trick that I used on myself: by splitting up chapters into smaller chunks, everything felt more bite-sized and manageable. When I was working on long chapters such as the [Apps](https://www.macstories.net/stories/ios-and-ipados-15-the-macstories-review/13/#apps) one (which alone clocks in at roughly 20,000 words), I didn’t have to scroll a huge document every time I was writing or editing it; instead, I could simply navigate to smaller files for specific sections and feel like I was making great progress when I completed one. I recognize how this is a silly thing that doesn’t really change the volume of the review, but – *hey* – human brains can be tricked with silly workarounds like that.

Perhaps you haven’t noticed this, but, for the first time since I started writing my annual iOS reviews, this year I was able to link to specific pages and sections of the review from other pages and sections. You may wonder – how could I create those `macstories.net` links if the review hadn’t been published yet? This is where Finn’s amazing [Export Markdown with Embeds plugin](https://club.macstories.net/posts/export-markdown-with-embeds) comes in.

When I was writing the review, if I wanted to link to another section or chapter, I just had to use Obsidian’s standard syntax for linking other `[](notes)`. However, because the Table of Contents featured a [YAML](https://help.obsidian.md/Advanced+topics/YAML+front+matter) block at the top with the base URL of the review (which I configured beforehand in our WordPress), when I ran the Export Markdown with Embeds command, the plugin was able to convert internal references into “real” URLs, including support for counting how deep into the review’s paginated structure a specific section would be. Finn has explained how all this works [in this post](https://club.macstories.net/posts/export-markdown-with-embeds). Effectively, thanks to Finn’s work, we have built backlinks for my iOS review, which is just incredible.

![](https://cdn.macstories.net/image-1632560252369.png)

The same internal references before and after.

As for backing up the review: I wrote the whole story in Obsidian, which comes with built-in versioning if you use the [Sync](https://obsidian.md/sync) service, and I do. Additionally, I regularly backed up individual chapters as well as the main ‘compiled’ copy of the review to a private repo in GitHub via [Working Copy](https://apps.apple.com/us/app/working-copy-git-client/id896694807), which is something I always do for all my stories. And, every few days, I also manually backed up my entire Obsidian folder to iCloud Drive as a .zip file.

Lastly, I want to mention how I kept track of all kinds of tasks while writing and editing the review. As you can guess, my system was entirely based on Finn’s other Obsidian plugin, [Todoist Tasks](https://club.macstories.net/posts/todoist-tasks-an-obsidian-plugin-to-create-tasks-in-todoist-with-two-way-linking). In every section of the review, I included a default YAML block at the top to define basic attributes for the Todoist integration, such as the project title (‘iOS Review’) and tags. Whenever I wanted to insert a particular task in a draft, I used Obsidian’s syntax for todos (`- [ ] Task title`) and ran the command to create a two-way link between Obsidian and Todoist. Again, Finn [wrote about how this all works here](https://club.macstories.net/posts/todoist-tasks-an-obsidian-plugin-to-create-tasks-in-todoist-with-two-way-linking), so if you’re interested in downloading the plugin and making it work for you, check out his post.

### Review Stats

It wouldn’t be the end of iOS review season without some stats. Here are some numbers from my iOS and iPadOS 15 review:

-   247 unique links
-   33 videos
-   298 images
-   Word counts
    -   Body text: 45,702
    -   Asides: 1,184
    -   Footnotes: 426
    -   Captions: 343
-   Total words: 47,655
-   860 paragraphs
-   1,918 sentences
-   278,421 characters
-   52.96 Flesch score
-   12.04 Flesch-Kincaid grade level
-   14.75 Fog Index
-   Time tracked
    -   Research: 22 hours
    -   Writing : 47 hours
    -   Editing: 52 hours
-   Total time tracked: 121 hours

([Compare these stats to last year](https://club.macstories.net/posts/ios-14-review-making-of) to see the difference.)

### Safari Speaker Pro and Shortcut Exporter Pro

As promised in the review, here are the two exclusive shortcuts that I created for Club MacStories members this year.

#### Safari Speaker Pro

Safari Speaker Pro is an advanced version [Safari Speaker](https://www.macstories.net/stories/ios-and-ipados-15-the-macstories-review/12/#safari-speaker), a shortcut I created that lets you convert articles from Safari into audio versions spoken by Siri.

With Safari Speaker Pro, you can save the spoken audio file anywhere in the Files app, open it in a specific app, and even embed it in Obsidian. To use the shortcut, all you have to do is run it from the share sheet in Safari when reading an article; you’ll be presented with a menu, and you can choose what you want to do with the file.

![](https://cdn.macstories.net/image-1632560733877.png)

Running Safari Speaker Pro in Safari.

The Obsidian integration is particularly interesting since it allows you to listen to an article in Obsidian while taking notes, as you can see in the screenshots below.

![](https://cdn.macstories.net/image-1632560777643.png)

Unfortunately, due to performance issues in the Shortcuts app, audio generation seems to be *extremely* slow right now. There’s nothing I can do about this, and I hope Apple will improve performance of the ‘Make Spoken Audio’ action soon.

You can [download the shortcut here](https://www.icloud.com/shortcuts/0e069868cc1044df8bf425eb8878937d).

(If you can’t select a folder during the shortcut’s setup process, skip the step and configure the folder later in the Shortcuts editor. Unfortunately, this is another bug in Shortcuts I cannot work around right now.)

#### Shortcut Exporter Pro

Shortcut Exporter Pro is a more advanced version of [Shortcut Exporter](https://www.macstories.net/stories/ios-and-ipados-15-the-macstories-review/12/#export-shortcut-as-file), the shortcut that lets you manually back up your shortcuts as files.

With Shortcut Exporter Pro, you can select an alternative location for your shortcut backups; additionally, you’ll have the option to export all shortcuts at once, back them up by folder, filter specific shortcuts by name, and even create backups for shortcuts that were recently modified.

Shortcut Exporter Pro is the ultimate Shortcuts backup utility, and it was made possible by the new Files actions in iOS and iPadOS 15.

![](https://cdn.macstories.net/image-1632560908701.png)

You can [download the shortcut here](https://www.icloud.com/shortcuts/6cc84ef0a9714dfa9a5a1c6258c6cfa9).

***

Ultimately, if I had to sum up how I approached the review this year, here’s how I’d put it:

I knew that I was going to have less time for the review because we needed to [launch Calliope](https://www.macstories.net/stories/introducing-the-all-new-club-macstories-new-tiers-for-more-original-content-discord-community-search-and-custom-rss-and-our-new-calliope-web-app/), but I *also* wanted to make it shorter and more approachable for people. So, instead of spending time rewriting developer documentation, I went for a more direct style that didn’t compromise on my personal thoughts and opinions. Additionally, instead of using a complex system of multiple note-taking apps and text editors for the review, I consolidated everything into Obsidian and commissioned custom plugins to make my life easier.

I’m happy with how everything turned out and how efficient I was with this system, and you can expect a similar – and perhaps even more compact – iOS and iPadOS review next year.

As always, I’m incredibly grateful to be able to write these iOS and iPadOS reviews every year. I wouldn’t be able to continue doing this without your support. Whether you read the review on the web or as an EPUB, I hope you’ll enjoy what I’ve worked on so hard for the past three months. Again, thank you, and let’s do this again next year.
***

==**19164**== Words

- **[Making Of: The iOS and iPadOS 15 Review](https://club.macstories.net/posts/making-of-the-ios-and-ipados-15-review)**