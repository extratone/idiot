---
share: true
dg-publish: true
---
# "My Obsidian Setup, Part 3: My 'Dashboard' Note for Quick Links, Todoist Tasks, Saving Ideas, and Keeping Track of Current Projects"

*26-04-2022 07:41* 

> Exploring topics beyond our day-to-day coverage.
Exploring topics beyond our day-to-day coverage.

## [My Obsidian Setup, Part 3: My 'Dashboard' Note for Quick Links, Todoist Tasks, Saving Ideas, and Keeping Track of Current Projects](https://club.macstories.net/posts/extension-284)

![](https://cdn.macstories.net/png-image-92755fd26628-1-1628262079226.png)

My Dashboard note.

In previous installments of my series about [Obsidian](https://obsidian.md/), I covered the basics of the app, its core plugins and options offered by third-party developers, plus advanced settings and my approach to sync and hotkeys. Today, I want to get into the juicy part of this series and explain in detail one of my favorite aspects of my Obsidian setup: my Dashboard note, which is rapidly becoming my second brain for everything that’s on my mind and has to be archived somewhere more reliable.

While I take plenty of notes in Obsidian and am also writing my iOS and iPadOS 15 review in it, the Dashboard is the single note I keep going back to the most; over the past few months, I’ve modified it to my needs and preferences, and now I think I have something that could potentially be useful to other people too.

Let’s dig in.

## An Inbox for My Thoughts

I don’t think I’m alone in this problem: I forget things on a daily basis. By this I don’t mean that I forget to check my task manager, or that I don’t feed my dogs or ignore the article drafts I’m writing in Obsidian. It’s the *little* things that get lost in the gray area in between tasks and longform notes I’m working on. I’ve talked about this problem before on [AppStories](https://appstories.net/) and [Connected](https://www.relay.fm/connected): I tend to forget about that link John sent me over iMessage that I meant to check out in 30 minutes after I was done with an article; or perhaps it’s an idea I just had that is neither a task nor a proper “note” yet; maybe it’s a reminder for myself to investigate something that may or may not be interesting for, say, Shortcuts or Obsidian. I understand that some people like to turn these kinds of items into tasks, but personally, when I don’t consider something actionable just yet, I prefer to keep it in my brain. The only issue is that, over time, I’ve stopped trusting it as a reliable repository for these transient thoughts and ideas.

I’m also the kind of person who needs structure in his daily life. This doesn’t mean *routine*: I very often change my plans at the very last minute (John can confirm this) and upend my working schedule without much warning. I like that flexibility about my life, and it’s part of the reason why I wouldn’t be able to work for anyone else at this point. What I need, however, is a tool that lets me see, at a glance, all the things I’m currently working on and stuff that’s on my mind, allowing me to quickly jump to those things and start processing them.

What I need is, effectively, a dashboard that allows me to easily see what’s on my mind and save ideas or random things as they come in, without having to decide where to put them in a task manager or turn them into full notes. A place where I can see a reflection of my thoughts, save new ones, and jump into work projects. And that’s exactly what I’ve been building and refining in Obsidian for the past few months.

## My Dashboard Note

At a high level, my Dashboard note is split into two distinct areas: at the top, there’s a variety of sections that **preview** or link to different things in Obsidian; at the bottom, there’s a more **creation**\-focused area that lets me save quick notes.

### Quick Links and Todoist Integration

Let’s start from the top. The first item is a section called ‘Quick Links’, which I filled with internal links to notes I find myself frequently opening in Obsidian. For instance, in this section I can find links to reopen my ‘Ideas for Stories’ or ‘Unwind Picks’ note; rather than manually searching for those notes, I can tap the links at the top of my dashboard, which in this case serves as a table of contents for my professional life.

![](https://cdn.macstories.net/7e247117-7c03-47d2-ae18-526e58ea8ffc-1628211293038.png)

Quick Links at the top of my dashboard.

You’ll notice that those internal links have emoji associated with them. The actual note titles don’t have emoji; what I leveraged here is the ability to assign ‘alt text’ to links in Obsidian by separating the linked item’s title and alternative title with a pipe (‘|’) character. This way, when I open the dashboard in preview mode, those links are prettier.

The second item in the upper section of my Dashboard note is a visualization of my tasks from Todoist. In edit mode, it looks like I have two embedded notes based on internal links; when I hit the preview button, those notes turn into *interactive* Todoist widgets that show me the tasks I want to see based on [Todoist’s native filters](https://todoist.com/help/articles/introduction-to-filters):

![](https://cdn.macstories.net/png-image-49964e01b468-1-1628262079163.png)

Todoist embeds in Obsidian.

This amazing Todoist embed functionality is based on the [Obsidian x Todoist plugin](https://github.com/jamiebrynes7/obsidian-todoist-plugin) created by Jamie Brynes. The idea is genius: after providing your Todoist API token in the plugin’s settings, you can drop a special code block in a note and edit it to display a subset of tasks from your Todoist account inside Obsidian’s preview mode. As detailed in the plugin’s documentation, there is a syntax you can use to configure these code blocks; the most important part, however, is that you can use any valid Todoist filter to display specific tasks.

This plugin opens up some incredible opportunities to bring your task manager into your note-taking app and create a direct link between the two of them. What’s even more remarkable about this plugin is the fact that checkboxes for tasks are clickable: you can check things off from Obsidian as you get work done, and changes will be instantly reflected in Todoist. (This is also the advantage of web apps with open APIs, but I digress.) Furthermore, you can choose to display task metadata such as dates and projects, and you can set an auto-refresh time to automatically reload these widgets while in preview mode.

Here’s what I’ve done for my dashboard: I’ve created two blocks to display tasks due today or overdue, as well as tasks due over the next three days. In both cases, these code blocks are based on a Todoist filter that excludes a specific project from view.

Here’s the filter that shows tasks due today or overdue except those from my Calliope project:

```
{
"name": "Tasks",
"filter": "(today | overdue) & !#Calliope",
"sorting": ["date"]
}
```

And here’s the one that shows me upcoming tasks for the next three days, excluding today and the Calliope project:

```
{
"name": "My Tasks",
"filter": "3 days & !#Calliope & !today",
"sorting": ["date"]
}
```

I could have dropped these code snippets directly into the Dashboard note, but it would have looked ugly. So instead I pasted the code into separate notes and embedded both in the dashboard with Obsidian’s !\[\[embed syntax\]\]. This way, the note stays compact but I retain the plugin’s functionality.

![](https://cdn.macstories.net/ab6006ed-c92b-4e4f-b319-272aeef08d81-1628211494139.png)

Special code blocks turn into Todoist embeds.

If you’re a desktop user, you can go ahead and install the plugin in Obsidian from the list of community plugins in the app. If you’re an iPhone and iPad user though, the plugin will give you an error and tell you it’s not compatible with Obsidian’s mobile app yet.

To fix this, I’ve teamed up with [Finn Voorhees](https://twitter.com/finnvoorhees), who forked the plugin and released a version that can be manually installed on iPhone and iPad. You can find [Finn’s version of Todoist x Obsidian here](https://github.com/Finnvoor/obsidian-todoist-plugin). In addition to enabling mobile compatibility, this version also includes some stylistic updates to Todoist’s embedded widgets to make them prettier.

Now you may be wondering: how do you manually install plugins as folders on iOS and iPadOS? Manual installation of plugin files in Obsidian requires opening a hidden folder and, unfortunately, hidden folders cannot be enabled in the Files app.

Well, fear not, because I created a solution to this as well. As I discovered a while back, it is possible to save files into hidden folders on iOS by leveraging the folder bookmarks feature of [Toolbox Pro](https://apps.apple.com/us/app/toolbox-pro-for-shortcuts/id1476205977). First, create a folder bookmark in Toolbox Pro by picking the root folder of your Obsidian vault. For me, that’s the ‘My Notes’ folder stored in On My iPad ⇾ Obsidian. Then, download the plugin from GitHub, uncompress it, and save the folder named ‘obsidian-todoist-plugin’ somewhere in Files. Last, [install my shortcut](https://www.icloud.com/shortcuts/5b814aac789b4604ac1226d59f566e18) to manually save plugins on iOS.

![](https://cdn.macstories.net/a8c38691-6ff0-4213-ae15-a57c4eb1ee9f-1628211270839.png)

Create a folder bookmark for your Obsidian vault in Toolbox Pro.

![](https://cdn.macstories.net/e241b337-fa16-4c39-9e05-b9c71bf2c84a-1628211271204.png)

My shortcut to save plugin files manually.

Before running the shortcut, copy the name of the plugin’s folder to your clipboard. This way, the shortcut will auto-fill the plugin’s name in its first input prompt, so you can just continue by picking, one by one, the plugin files you want to install in the newly created folder. Repeat this process for all the files contained in the plugin folder, then switch to Obsidian, reload Community Plugins, enable the Todoist plugin, and you’re done.

![](https://cdn.macstories.net/7c01a521-4a13-4b72-8938-e733a725476f-1628211294965.png)

Running the shortcut to save plugin files.

At this point, you can visit the plugin’s settings page in Obsidian to configure your Todoist credentials, then head over to the plugin’s documentation to learn about the code blocks you can drop in Obsidian. Hopefully, the plugin’s original developer will release an official update for mobile compatibility soon; in the meantime, you can use [Finn’s version](https://github.com/Finnvoor/obsidian-todoist-plugin).

The best part about this plugin is, unsurprisingly, its customization options. Because it’s entirely based on Todoist’s filters, I can choose to create embeds that focus on specific projects I’m prioritizing at the moment or, conversely, hide others I don’t want to see. This functionality is perfect for my Dashboard note, and I appreciate the closed loop this plugin creates between Obsidian and Todoist.

### Saving Links and Ideas with QuickAdd

Things are quite different in the second half of the note, which features separate sections titled ‘Working On’ and ‘On My Mind’. The names are fairly self-explanatory: the **Working On** section contains links to notes or articles I’m actively working on at the moment; the **On My Mind** section has ideas and links that are, *well*, currently on my mind at, at least for me, unfit for a task manager at this stage. What isn’t obvious is how I’ve been able to remove friction from appending text to these sections in a way that was never possible for me in other text editors or note-taking apps.

This is where we have to talk about [QuickAdd](https://github.com/chhoumann/quickadd), an incredible third-party plugin for Obsidian developed by [Christian Bager Bach Houmann](https://bagerbach.com/). QuickAdd is packed with features – including some esoteric ones such as JavaScript and calling the Obsidian API I haven’t played with – but it’s best to think about it this way: it’s the ultimate plugin to add text to existing notes, create new notes based on templates, or run macros inside Obsidian to execute multiple commands in a row via a single hotkey or command.

It’s easy to go deep down the QuickAdd rabbit hole if you don’t know where to start or if you spend too much time looking at those fascinating, complex setups shared in the Obsidian Discord community. So I’m going to give you a very practical rundown of how I use QuickAdd as a complement to my dashboard setup, which you can hopefully reuse for your Obsidian workflow.

The first thing I wanted to create was a command that instantly appends a link to the document I’m working on to the ‘Working On’ section of my Dashboard note. For example, if I’m working on the Shortcuts chapter of my iOS 15 review, I want to be able to capture a link to that document for future reference. QuickAdd is the only plugin I’ve found that has this knowledge of **appending text to the bottom of a specific section of another note**. This is a *very* specific functionality that I’m sure other writers or serious note-takers like me will appreciate.

Here’s how you can put this together: in QuickAdd’s settings, create a ‘choice’ with a unique name and select the ‘capture’ type from the menu. Add the ‘choice,’ then click the cog icon to configure it.

![](https://cdn.macstories.net/02280a81-b3b3-4413-b4a1-4c16a37348f1-1628213585672.png)

How to create a command to save what I’m working on.

In the choice’s configuration menu, you’ll have to modify these fields if you want to grab the link of the current document and append it to a section of another note:

-   **File Name**: the name of the note you’re appending text to. In my case, it’s Dashboard.md.
-   **Insert after**: enter the title of the section you want to append text to. This needs to be a specific line – I entered ‘## Working On’ since that’s the section I’m saving links into.
-   **Insert at the end of section**: enable this so that text will be appended at the end of the section within the note.
-   **Capture format**: QuickAdd supports a custom variable syntax for placeholders that are converted into different values when a command runs. You can [check out the syntax here](https://github.com/chhoumann/quickadd/blob/master/docs/FormatSyntax.md). In this case, you have to enter `{{LINKCURRENT}}`, which is the variable to generate a link to the note you’re currently focusing on.

![](https://cdn.macstories.net/png-image-9a6d235baff1-1-1628262079160.png)

How links to other notes get appended to the dashboard.

With this command setup, all I have to do when I’m working on a document I want to save in my Dashboard is hit ⌘P to show the command palette, type ‘Working’ to find the command, and run it so that a link to the note is appended to the dashboard immediately. Better yet, I can assign a hotkey to this command so I don’t even have to search for it.

I love this command since it provides me with a one-click solution to the problem of remembering all the things I’m working on and seeing them in one place. But as I kept looking into QuickAdd, I realized I could take the same append-to-section-of-a-note approach a step further with manual text input at runtime.

QuickAdd’s syntaxsupports a `{{VALUE}}` placeholder that, when a command runs, shows a native input prompt in Obsidian to type some text. I think you can see where this is going. I created another capture ‘choice’ in QuickAdd and replicated the same settings of the one above, but I swapped the section for ‘## On My Mind’ and used the ‘value’ placeholder instead. Now when I run the ‘On My Mind’ command, an input prompt comes up, I can type some text for an idea I have, and it gets saved immediately to the bottom of the ‘On My Mind’ section of the Dashboard note.

![](https://cdn.macstories.net/b65bd4b3-1247-4b29-8d13-0dbbd5de5599-1628213586380.png)

Configuring the On My Mind command.

![](https://cdn.macstories.net/4208c52d-2bfe-499f-b45c-80e5eec7b14c-1628213299338.png)

Capturing thoughts in Obsidian.

This works from anywhere in Obsidian and doesn’t force me to leave the note I’m currently working on. QuickAdd’s prompt is, effectively, a global capture tool for Obsidian. This system removes all the friction typically involved with having an idea, closing the note you’re currently working, opening another, then going back to what you were doing. I run this command dozens of times each day, and it’s become my favorite aspect of the dashboard.

As I mentioned above, QuickAdd can also run macros, which let the plugin execute multiple Obsidian commands in succession as a single block. I’ve taken advantage of the macro functionality to automate something I found myself doing manually every time in Obsidian: switching back to the Dashboard note, splitting the UI vertically to open a second pane on the right, and toggling preview mode on that pane. The end result is the workspace at the top of this story.

This is another great thing about Obsidian: I could load this workspace via the Workspaces plugin, but I’ve also figured out how to open it as a macro, with additional control, using QuickAdd. Obsidian gives me the option to *choose* the solution that works best for me rather than forcing an “opinionated” design upon me that cannot be customized to fit my needs.

To create a QuickAdd macro, open QuickAdd’s settings, then hit ‘Manage Macros’ and create a new one. Press ‘Configure’ next to the newly created macro and you can start setting it up. In my case, all I needed to do was chain all the necessary commands together in a string of actions executed from top to bottom, kind of like Shortcuts. Here are the commands I used to create a Dashboard workspace with two panes using QuickAdd:

-   **Open starred file.** This is based on the [Hotkeys for Starred Files and Searches plugin](https://github.com/Vinzent03/obsidian-shortcuts-for-starred-files), which creates commands for files you’ve [starred](https://help.obsidian.md/Plugins/Starred+notes) in Obsidian. In the screenshot below, you can see I’m using the ‘Open starred file: 1’ command, and that’s because the Dashboard note is the first one in the list of my starred files. This functionality should really be built into Obsidian; thankfully though, QuickAdd lets us execute any command, regardless of whether it’s a third-party one or not.
-   **Split vertically.** This splits the UI vertically, creating a second pane on the right.
-   **Focus on pane to the right.** Puts the focus on the new pane.
-   **Toggle edit/preview mode.** Enables preview mode on the new pane because, by default, new panes open in edit mode for me.
-   **Focus on pane to the left.** Returns focus to the Dashboard pane on the left side, which is open in edit mode.

![](https://cdn.macstories.net/8217cba8-d147-489a-ad07-7c64bb76a6df-1628213288969.png)

Recreating my Dashboard workspace with a macro.

Similarly, I also created another version of this macro that only loads the Dashboard note on the right side, leaving the document I’m currently working on in the left pane. Here’s what the macro looks like:

![](https://cdn.macstories.net/a51d6420-9ecd-4ca0-b412-9a523cb9bdf1-1628213289370.png)

My macro to split the UI and open the Dashboard note on the right.

One important note about chaining actions in QuickAdd macros: make sure to always put ‘Wait’ actions in between steps, otherwise QuickAdd won’t be able to execute them all fast enough. You can add these actions by tapping the clock icon in the macro editing UI.

***

Thanks to QuickAdd, I’ve been able to put together commands that speed up the act of capturing links to notes I’m working on, saving ideas, and opening my dashboard. All of these commands can be triggered individually with hotkeys or via the command palette, but for my convenience, I also grouped them together in a menu in QuickAdd. I did this by adding a ‘Multi’ choice in QuickAdd and dragging each command under it until they were all contained in the menu.

![](https://cdn.macstories.net/701e73db-0de9-4b30-a3de-00325cc3161e-1628213289146.png)

Menus in QuickAdd.

Now, when I hit ⌘P, type ‘dash,’ and press Enter, this is what I see:

![](https://cdn.macstories.net/9e680929-392c-4d45-936b-37399bf64fcd-1628213298307.png)

My Dashboard Menu in QuickAdd.

I don’t have to be inside Obsidian to trigger my Dashboard Menu command. Thanks to the [Advanced URI plugin](https://github.com/Vinzent03/obsidian-advanced-uri), I created a simple shortcut that opens the menu via this URL scheme:

`obsidian://advanced-uri?vault=My%20Notes&commandname=QuickAdd%3A%20Dashboard%20Menu`

I added the shortcut as an icon to my Home Screen, so whenever I want to open my Dashboard workspace or save a thought, I can press the icon to launch Obsidian and run the command.

Speaking of Obsidian and Advanced URI, I also created another shortcut that opens my dashboard in different modes whether the shortcut is running on iPad or iPhone. This is a direct launcher that goes straight to the Dashboard note without showing a QuickAdd menu in the middle, and it’s one of the icons in my iPhone dock since I use it a lot.

When the shortcut runs on iPhone, I likely don’t want to split the UI in Obsidian in multiple panes due to the smaller screen, so the shortcut simply opens the note in full-screen; if the shortcut is being executed on iPad, however, it loads my Dashboard Preview workspace, which has two panes open side-by-side. You can see how this platform-based shortcut can be created in the screenshot below:

![](https://cdn.macstories.net/304a0ce9-8684-4a87-9710-1f5c1e60b937-1628213289454.png)

My shortcut to reopen the Dashboard workspace.

***

It’s not an exaggeration to say that my Dashboard setup has tangibly improved my life over the past few months. I forget fewer things, have a better sense of all the different things I’m working on (and, believe me, they are many), and I can more easily keep up with all my hobbies because saving ideas and links with QuickAdd’s prompts is a breeze. Obsidian’s native linking capabilities lend themselves well to this kind of workflow where I can reference documents I’m working on, turn text from the dashboard into standalone notes (thanks to [Note Refactor](https://github.com/lynchjames/note-refactor-obsidian)), and jump to frequently-used notes.

For me, the Dashboard is where all work starts now, and Obsidian is the only app that gives me the tools to make all this happen.

## Just Because You Can, Doesn’t Mean You Should

This column is a sort of [sequel to my Monthly Log story](https://mailchi.mp/macstories/gouerhig38orhgq83roghrouiuhgorigohrqu) last week about why you should delete more of your notes and not feel bad about not having a ‘system’ for taking them. I love an efficient system no matter what the workflow is, which is why I tweak mine a lot. Once you have a good system in place, though, the trick is to not go overboard.

I’ve framed today’s topic in terms of automation, but it holds true for any system really. Automation just happens to be on my mind because I’ve been taking the time to reassess a lot of the ways I work and the automations I use. Some of the ways I’ve been automating tasks are outdated, and I’m working on new projects that could benefit from changing how I work. To that end, I’ve been experimenting with Obsidian plugins, creating new shortcuts, and setting up a [Loupedeck Live](https://loupedeck.com/us/products/loupedeck-live/), a device I’ll be reviewing soon.

The process of thinking through my workflows has been rewarding. It’s not something I’d suggest doing often, but as the work you do and the apps you use evolve, understanding how and why you do things the way you do can be enlightening. I can’t say that any one insight I’ve had rethinking my workflows has led to monumental productivity gains, but together, several smaller things have made my latest efforts worthwhile.

My workflow reevaluation reminded me of a couple of areas that would be trivial to automate that I don’t. It’s not that I haven’t taken the time to automate these tasks. No, the decision was very intentional, and I suspect it will surprise some of you.

I don’t automate responses to email. If someone sends me a message, I’d rather not respond to it until I have the time than to send a canned response. I can always tell when I get a canned response, masquerading as a personal message, and I don’t want to be that guy. If someone’s message is worth responding to, the response should be tailored to the context of the message and not feel like an FAQ.

That’s why I don’t use a dedicated text expansion app on any platform. I’m a fast typist, so I feel like the time I’d save isn’t worth the cost. That’s not to say I don’t use text templates, but those are a little different. I have checklists of materials I’ll need from advertisers, for example. However, when I send those, it’s always with a note that explains that I’m pasting a checklist at the bottom of the message for reference. The main body of the message is often similar for similar situations, but it’s always unique because I feel like it’s the least I can do when someone gets in touch.

Because I get a lot of email, the system has its limits. It means I don’t respond to everyone, which I’m sure disappoints some people. However, I’d rather connect with as many people as I can and disappoint a few than send robo-responses.

Instead of using text expansion, I rely on a growing list of templates like the checklists I mentioned, which are simple text files for collecting and organizing information for things like the show notes for an AppStories episode or ensuring format and content consistency among posts that appear regularly on MacStories. [Obsidian](https://obsidian.md/) is excellent for this, but before I used it, I copied one week’s template to the next week in [iA Writer](https://ia.net/writer).

The other thing I’ve never automated is publishing articles or podcast episodes. It’s easy to schedule articles and episodes for publication. The functionality is built right into WordPress. The value of doing it manually, though, is having one last chance to catch a typo or other error and being somewhere where even if I don’t catch a problem, I can correct it quickly.

Despite my best efforts, I make mistakes in articles I publish. I’ve gotten better over time, but some errors are inevitable. Fortunately, it’s simple to edit a published post, assuming you’re aware of the problem. If I’ve just published an article with a typo manually, I’ll hear from someone on Twitter within a matter of minutes. Being in front of whatever device I used to publish the story means I can fix it quickly before many people ever see it.

Whenever I see an error on someone’s homepage that’s been there for hours, I wonder if it was a scheduled post. Whether it is or isn’t, I don’t want to ever be in the position of not knowing about an issue or being unable to correct it quickly.

The point of both of these examples isn’t to suggest that no one should automate these things. Different people have different priorities. However, I do think it pays to think before you automate. Just because something can be automated doesn’t mean it should be even if it’s easy to do so. Putting in a little time and effort into thinking about why something should or shouldn’t be automated is the difference between a nifty demo and a meaningful change in the way you get things done, which is what productivity should be all about after all.
***

==**24594**== Words

- **[My Obsidian Setup, Part 3: My 'Dashboard' Note for Quick Links, Todoist Tasks, Saving Ideas, and Keeping Track of Current Projects](https://club.macstories.net/posts/extension-284)**
- [My Obsidian Setup, Part 4 Templates for Weekly Posts and Custom Mobile Toolbar - Federico](My%20Obsidian%20Setup,%20Part%204%20Templates%20for%20Weekly%20Posts%20and%20Custom%20Mobile%20Toolbar%20-%20Federico.md)