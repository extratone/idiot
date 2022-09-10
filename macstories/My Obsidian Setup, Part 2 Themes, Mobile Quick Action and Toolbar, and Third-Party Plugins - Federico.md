---
share: true
dg-publish: true
---
# "My Obsidian Setup, Part 2: Themes, Mobile Quick Action and Toolbar, and Third-Party Plugins"

*26-04-2022 07:41* 

> Exploring topics beyond our day-to-day coverage.
Exploring topics beyond our day-to-day coverage.

## [My Obsidian Setup, Part 2: Themes, Mobile Quick Action and Toolbar, and Third-Party Plugins](https://club.macstories.net/posts/my-obsidian-setup-part-2-themes-mobile-quick-action-and-toolbar-and-third-party-plugins)

In the [first installment of my new Obsidian series](https://mailchi.mp/macstories/iufheagrqo8y7fqrtg3igfrqw8grqwfiogfrwqiygfrqwqq) I published last week, I covered the basics of the [app](https://obsidian.md/) to get started with its (many) settings, built-in core plugins, and different types of sync. This week, we’re taking a look at the Obsidian theme I’m using right now, options for customizing command activation on iPhone, and a collection of third-party ‘community’ plugins I’ve been using for the past few months. Let’s jump back in.

### The Theme I’m Using (and SF Mono)

I want to cover this one right away since you’re going to notice that screenshots in this story feature a new Obsidian look compared to last week. The theme I’m using right now is called [Minimal](https://github.com/kepano/obsidian-minimal); it was created by Stephan Ango with the goal of bringing Obsidian closer to Apple’s [macOS HIG](https://developer.apple.com/design/human-interface-guidelines/macos/overview/themes/) by using native system fonts, rounded corners for panels and popups, pill-shaped tags, and more. The theme was recently updated for iPhone and iPad, and it is, in my opinion, one of the best looks you can install for Obsidian on Apple platforms at the moment.

![](https://cdn.macstories.net/08f84964-ed5a-415f-a3d0-59a38d0a0a69-1627045397711.png)

Minimal on iPhone.

![](https://cdn.macstories.net/74bda7f2-0d46-41bf-953e-09c2912fbdab-1627045539121.png)

Minimal on iPad.

There are *hundreds* of Obsidian themes out there; the number skyrockets if you consider how you can further tweak themes via [CSS snippets](https://help.obsidian.md/Advanced+topics/Customizing+CSS). A lot of Obsidian themes, however, are not optimized for iPhone and iPad yet, or they don’t apply Apple’s design sensibilities to the app, or, even worse, only come with a dark mode UI, which is usually too low-contrast for me.

Minimal is the opposite. For starters, its developer has done a lot of work to make different parts of the Obsidian UI more Apple-like and palatable to iOS and iPadOS users. On iPad, the command palette is a floating popup reminiscent of the quick switchers seen in [Craft](https://apps.apple.com/us/app/craft-docs-and-notes-editor/id1487937127) and [Agenda](https://apps.apple.com/us/app/agenda/id1370289240); the preference pane is displayed as a large card raising from the bottom of the screen; sidebars (such as the file explorer or backlinks pane) have a nice floating appearance and support hover effects when moving the pointer over buttons and documents.

![](https://cdn.macstories.net/981debae-76dc-484c-b735-36e25f45f539-1627045539810.png)

Floating sidebars in Minimal.

![](https://cdn.macstories.net/31c354b9-d721-46f6-984c-ec7ca3d91228-1627045538901.png)

The floating command palette in Minimal.

I particularly appreciate the design of context menus on iPad, such as this popup you get by right-clicking a document in the file explorer sidebar:

![](https://cdn.macstories.net/90580b09-dfcc-48f8-8322-20a8b3ebb197-1627045539901.png)

Minimal’s context menus.

What also makes Minimal stand out is the availability of a companion [Minimal Theme Settings plugin](https://github.com/kepano/obsidian-minimal-settings) created by the developer to customize the theme to fit your needs and tastes better. This is where it gets interesting since most themes don’t offer this kind of personalization. Once you’ve installed Minimal and Minimal Theme Settings, head over to the plugin’s preference page and you’ll notice you can change the theme’s accent color hue and saturation. Minimal is, well, a very *minimal* theme, but it uses accent colors for elements such as hyperlinks, text selection, note links, and buttons in settings. If you want to give Obsidian a green or blue accent color, just move the two sliders until you’ve gotten the color you like. In the future, it’d be nice to be able to input a single HEX value rather than having to use manual sliders.

![](https://cdn.macstories.net/0f3ec3cf-bd87-46c9-8e24-feb61d63dc2a-1627046480474.png)

Different accent colors in Obsidian.

Minimal also comes with separate appearance modes for light and dark mode, which can be configured to follow the system’s appearance setting or not. (Personally, I prefer Obsidian to switch to dark mode when I enable dark mode in Control Center.) I’ve decided to go with all white for light mode and true black for dark mode; if the all white option is too low contrast for you, there are low and high contrast modes you can enable for the light theme setting. Unsurprisingly, true black mode looks fantastic on OLED iPhones and the M1 iPad Pro with mini-LED display:

And then we have fonts. For a few years now, I’ve been writing all my articles and newsletters using a monospaced font. I used to have iA Mono back when I was an [iA Writer](https://apps.apple.com/us/app/ia-writer/id775737172) user; in other text editors, whenever possible, I prefer to fall back to Apple’s own SF Mono font. Other Obsidian themes I’ve tested make it surprisingly difficult to switch to a different font for the text editor, and I’ve spent way too much time trying to force this change using CSS snippets found online. The Minimal theme and its associated plugin make this process incredibly easy thanks to built-in menus to switch the fonts used in the app’s UI and preview mode, the text editor, and code blocks. All you have to do is open the Minimal Theme Settings page, scroll to the font section, and pick from a list of prepackaged font selections. Assuming you have those fonts installed on your device, just reload Obsidian, and changes will take effect.

![](https://cdn.macstories.net/49270f1e-b110-4262-9190-db6e0cc24917-1627047919409.png)

Changing fonts in Minimal Theme Settings.

The only issue is – you have to install those fonts manually on your device beforehand using apps such as [AnyFont](https://apps.apple.com/us/app/anyfont/id821560738) or [Fontcase](https://apps.apple.com/us/app/fontcase-manage-your-type/id1205074470) (I prefer the latter since it lets me easily import [multiple font files at once from the Files app](https://www.macstories.net/reviews/fontcase-simplifies-custom-font-installation-on-ios-and-ipados/)). And because Apple’s SF Mono font is not pre-installed on iOS or iPadOS by default, there are some additional steps to follow. First, download the .dmg file for the SF Mono font from [Apple’s Fonts webpage](https://developer.apple.com/fonts/) on your Mac. The disk image contains an installer file that saves SF Mono’s font files somewhere on your computer, and you need to extract those **.otf files** (avoid the .ttf ones if you want to bring them over to iOS or iPadOS).

![](https://cdn.macstories.net/screen-shot-2021-07-21-at-12-05-24-pm-1626863836722.png)

The installer package for SF Mono.

Thankfully, there’s a relatively easy solution to this as well. For the past few years, I’ve been using the excellent [Pacifist app for macOS](https://www.charlessoft.com/) to inspect the contents of installer packages and extract them to the Finder. For SF Mono, all I had to was drag the installer to my desktop, open it with Pacifist, expand its directory until I found the Fonts folder stored within it, and extract it to a folder in Finder. You’ll have to use an additional desktop app for this, which isn’t ideal, but I purchased Pacifist years ago and have used it dozens of times to extract all kinds of files from installer packages, so the investment paid off. I can’t recommend this app enough.

![](https://cdn.macstories.net/screen-shot-2021-07-21-at-12-05-42-pm-1626863836748.png)

Select ‘Open’ to open an installer package with Pacifist…

![](https://cdn.macstories.net/screen-shot-2021-07-21-at-12-06-24-pm-1626863838341.png)

…find the folder containing the font files you need…

![](https://cdn.macstories.net/screen-shot-2021-07-21-at-12-06-39-pm-1626863837139.png)

…and extract them to Finder.

Once I had a folder containing SF Mono’s .otf files, I synced it to my devices using iCloud Drive, manually installed them via the profile-based method supported by Fontcase, force-quit Obsidian, and the app’s text editor started correctly using SF Mono as the monospaced font for the editor.

![](https://cdn.macstories.net/be478450-19c1-42dc-8a1b-dcc964ae8579-1627048029064.png)

Installing multiple font files at once with Fontcase.

![](https://cdn.macstories.net/4ffe81f6-0cbc-4156-bfd1-a2c0ec128601-1627048029047.png)

SF Mono and SF Pro in Obsidian.

Thanks to Minimal, I now have a beautiful theme for Obsidian that works well in the iOS and iPadOS app and which lets me use my favorite Apple typeface for the editor. If you’re looking for a different appearance for the Obsidian app, I highly recommend Minimal and its Minimal Theme Settings plugin.

### Customizing the Mobile Quick Action

One of my favorite details of Obsidian for iPhone is the mobile quick action – a handy pull-down gesture that lets you execute *any* command by swiping down anywhere in the app. The iPhone version of Obsidian is (unsurprisingly) harder to navigate than the Mac and iPad apps due to the lack of an external keyboard (unless you use a Bluetooth keyboard with your iPhone; in that case, I salute you), so the quick action can come in handy to trigger commands that would otherwise require multiple taps on the iPhone’s smaller screen.

![](https://cdn.macstories.net/a7ebe4ee-54a2-4b8a-8111-adad8dafcf7b-1627048190392.png)

Triggering the quick action on iPhone.

My recommendation for the iPhone quick action is to assign it to trigger the command palette. This way, you can quickly swipe down anywhere in the app and you’ll be instantly presented with a list of commands you can activate with one tap. The keyboard comes up as soon as the command palette is shown (so you can look for a command by name with fuzzy search, as I explained last week), and you can also pin specific commands to the top of the palette for even faster access.

The command palette should be assigned to the mobile quick action by default. If it isn’t, or if you prefer to pair any other command with the quick action, you can customize it in Options ⇾ Mobile ⇾ Configure Mobile Quick Action.

### Customizing the Mobile Toolbar and Command Palette

There’s more to customizing how commands are triggered in Obsidian for iPhone and iPad than the quick action: you can also configure the row of controls displayed above the keyboard, and, as I mentioned above, you can pin commands to the top of the command palette.

Let’s start from the command palette. Open Obsidian’s Options screen, open the Command Palette’s core plugin settings page, and you’ll be presented with a list of pinned commands. This list will likely be empty the first time you open this screen, so tap into the search bar next to ‘New Pinned Command’ and you can search for *any* command available in the app to make it a pinned one. All commands – both built-in commands and the ones exposed by plugins – will show up here, and you’re free to pin whatever you want. Once you’ve selected some, you can rearrange their order in the list of pinned commands.

![](https://cdn.macstories.net/82acfcd8-b676-41ae-9d72-823388f9e87a-1627048924769.png)

Creating pinned commands for the command palette.

I highly encourage the use of pinned commands and, more importantly, to revisit this page over time as you get a sense of the commands you use the most on your iPhone and iPad, tweaking the list accordingly. There are hundreds of commands available in Obsidian, and the list grows the more plugins you install, so it’s good to have a list of pins that evolves with your needs over time. In a nice touch, the command palette shows you the hotkey associated with each command on iPad, so it can also serve as a handy cheat sheet to memorize keyboard shortcuts.

[![](https://mcusercontent.com/9f4b80a35728f7271fe3ea6ff/images/29b67ebb-9553-2a17-5db1-246971f57962.png)](https://cdn.macstories.net/93caa481-ff92-47bc-b1f8-3532389a5fd7-1627048536557.png)

You can also customize the toolbar containing text editing controls displayed above the keyboard. By default, the toolbar comes with shortcuts related to text editing and writing, such as toggling bold and italics, indenting and outdenting list items, moving the caret, or inserting attachments into notes. You can delete default commands you don’t want, rearrange their order, and add other commands provided by default. Since I do most of my note-taking and writing on iPad and use an external keyboard, I don’t use the toolbar a lot, and I prefer to keep the list of options to a minimum. I use it more on iPhone, where it’s nice to have certain formatting controls or shortcuts that save me a few taps when I’m writing or editing a note.

![](https://cdn.macstories.net/cbe68e72-13b9-4d4e-9bc7-0848df4f7a89-1627048925382.png)

Customizing the mobile toolbar with global commands.

However, what I *really* like about the toolbar is the ability to pin any global command as a custom accessory displayed above the keyboard. This option is consistent with Obsidian’s command palette, and it allows you to add any other command from the app and show it as a button above the keyboard. To do this, open Options ⇾ Mobile, scroll to the bottom of the page, and tap into the search bar next to ‘Add Global Command’. From here, you can search for any global command you want and add it to the toolbar for fast access.

A word of caution for global commands: because not all of them are necessarily optimized for toolbar usage, you may not see dedicated icons for them above the keyboard. If that’s the case, a global command will be displayed with a generic ‘?’ icon, which can be confusing if you add a bunch of global commands that don’t have toolbar icons and can’t tell them apart. I’ve only added a couple to my iPhone, so I can remember which one is which, but I hope more plugins will start adding support for toolbar icons soon.

### Third-Party Plugins I’m Using

In case it’s not clear by now, there are hundreds of third-party plugins for Obsidian – some of which can do things you’d never expect from a text editor (how about a [Kanban board](https://github.com/mgmeyers/obsidian-kanban)? What about [mind maps](https://github.com/lynchjames/obsidian-mind-map)?). Therefore, this is by no means an exhaustive list of all the plugins I’m playing around with. However, I wanted to call out some of the community plugins I’ve been using for a while now, since I believe they’re a good place to start when it comes to exploring the many possibilities offered by Obsidian.

**[Advanced Obsidian URI](https://github.com/Vinzent03/obsidian-advanced-uri)**. Here’s a wild one: what if I told you that third-party Obsidian plugins can register URL schemes otherwise not supported by default in Obsidian? That’s what Advanced Obsidian URI does: it exposes additional commands via the Obsidian URL scheme, such as loading workspaces, appending text to files, or opening your daily notes. I mostly use this plugin to load my favorite workspaces via shortcuts on the iPhone and iPad, which can be done by opening a URL like this one:

`obsidian://advanced-uri?vault=My%20Notes&workspace=Dashboard%20Preview`

As you can see, this plugin uses the Obsidian URL scheme, but it adds an ‘advanced-uri’ command that can be set to open the ‘Dashboard Preview’ workspace in the vault called ‘My Notes’.

**[Cycle Through Panes](https://github.com/phibr0/cycle-through-panes)**. This is one of those features that should be built into Obsidian by default: with this plugin, as the name implies, you can cycle through multiple open panes via ⌃Tab. This command is so ingrained in my muscle memory now, I often forget it’s actually provided by a plugin.

**[Buttons](https://github.com/shabegom/buttons)**. This is one of the third-party plugins that will require a standalone, deeper dive in the future. With Buttons, you can, well, create buttons that perform specific features while in preview mode. In editing mode, all you see is a special code block with a proprietary syntax; as soon as you enter preview mode, the syntax becomes a colored button you can click to do something. There are several different kinds of button types: you can create buttons that run commands, open links, perform calculations, create new notes from templates, append or prepend text to notes, and more. In the screenshot below, you can see how I’ve been using this plugin to put together a button that lets me create a note with a timestamp and tag; I plan to write about this more in depth in future installments.

![](https://cdn.macstories.net/de2f526a-589d-450d-8713-121e85bce643-1627048536883.png)

A button’s syntax (left, first red code block) and the final result (right, blue button).

**[Dataview](https://github.com/blacksmithgu/obsidian-dataview)**. Dataview is, quite possibly, the most complex and incredible third-party plugin at the moment. Effectively, Dataview lets you use your Obsidian vault as a database, and there’s a special syntax to create code blocks that query from that database. Like Buttons, when you hit preview mode, that special code block becomes something else; in this case, Dataview code blocks become tables that show you the result of your query.

It can be hard to wrap your head around Dataview, which is why this plugin will also require a deeper exploration in the future. In the meantime, I suggest you check out the full documentation [here](https://blacksmithgu.github.io/obsidian-dataview/) to get a sense of the dynamic views you can create with Dataview. To give you a first example of how I’m using Dataview, I’ve put together a table that pulls in article highlights I save into Obsidian when I’m catching up on stories in Safari Reading List. These notes are saved with a specific syntax, which Dataview can query, and they’re then presented in a table which is sorted by date. Stay tuned for a future installment in which I will describe my workflow for this.

![](https://cdn.macstories.net/e881080c-4b99-4ef7-b7a4-3f429593e597-1627048537090.png)

The Dataview syntax (right) and the resulting table with queried results (left).

**[Note Refactor](https://github.com/lynchjames/note-refactor-obsidian)**. If you’ve ever found yourself working on a long document and realizing it could be split into multiple, shorter notes, allow me to introduce you to Note Refactor. This plugin lets you extract a selection from the text editor into a new note and (optionally) use the first line of text from the selection as the new note’s filename. This has been perfect for me for all those times when I’m working on a story, create a few headings for sections and start writing, then realize I’d prefer to split those sections into their own separate notes. The plugin comes with two settings I recommend enabling: you can choose to split new notes into the same folder as the current file (so you can keep files from the same project in the same folder) and you can embed a newly split note into the original one by default.

![](https://cdn.macstories.net/c2f02e72-0a1b-48e2-ba34-ca60fb5c9cb9-1627048925422.png)

Refactoring a section of a note into a separate, standalone note.

**[Workbench](https://github.com/ryanjamurphy/workbench-obsidian)**. Developed by Obsidian user extraordinaire Ryan J.A. Murphy, Workbench lets you collect working materials by appending links to specific notes or sections of notes at the bottom of a general ‘workbench’ that serves as an inbox of sorts. For me, this is the ‘Dashboard’ note I’m going to describe in the next installment of this series, which is a note where I keep all kinds of links and temporary notes for things that are on my mind at the moment. Amazingly, Workbench lets you immediately append any internal link by ⌥-clicking it, and you can also save any line of text at the bottom of your workbench by ⌘⌥-clicking it. Alternatively, you can use the ‘Link the current note in your Workbench’ command, which I’ve pinned to the top of the palette on iPhone and trigger with ⌘⌥W on my iPad Pro.

That’s it for this week. There’s still a lot to cover in Obsidian, but I feel like I’ve explained the basics of the app, and it’s time to start digging into advanced workflows, plugins, and my approach to note-taking and writing. In the meantime, if you have an interesting setup in Obsidian or have plugin suggestions for me, I’d [love to hear from you](https://twitter.com/viticci).

### Always On

When [Mark Gurman reported for Bloomberg](https://www.bloomberg.com/news/articles/2021-07-14/apple-seeks-up-to-20-increase-in-new-iphone-production-for-2021) that Apple might launch an iPhone with an always-on display, my ears perked up. That’s because I’ve been running an iPhone and iPad with the Auto-Lock feature turned off for months. If Apple goes with such a display, I expect it will be coupled with new iOS 15 features, but even without that, there’s a lot to like about leaving your screen on all the time.

I didn’t set out to test what having an always-on screen would be like. It started with my review of the [Twelve South HoverBar Duo](https://www.macstories.net/reviews/hoverbar-duo-the-macstories-review/), which is my current favorite iPad stand. I love the stand’s range of motion and ability to hold everything from my iPhone 12 Pro Max to the 12.9" iPad. Before the HoverBar Duo, I’d used iPad stands with a keyboard and trackpad for writing. What made Twelve South’s stand a little different is that its adjustability allows an iPhone or iPad to function exceptionally well as a second screen.

I set the HoverBar Duo up on my desk next to the external display I use with my 2018 Mac mini, and the two made a great pair. Sometimes I’d use Sidecar, so my iPad served as a true second display, but more often, I ran native iPadOS versions of apps like Discord, Messages, and Spark on it.

However, I quickly realized that the iPad’s maximum auto-lock timer is too short at five minutes for this kind of setup. That time period is fine if I’m actively using apps on the iPad, but when I’m just monitoring conversations and keeping an eye out for notifications, having to unlock the iPad repeatedly gets old fast.

Having your device’s screen auto-lock is a valuable security feature, but I was testing the HoverBar Duo in the dead of winter during a pandemic. I wasn’t going out much, so locking my devices wasn’t a big concern. Access to power to charge the iPad or run it connected to a power adapter wasn’t an issue either. So, I turned auto-lock off to see how it would go.

I was pleasantly surprised. My experience with the iPad was so good, in fact, that I decided to add my iPhone to the mix. My iPhone usually sits to one side of my desk on a [Belkin 3-in-1 MagSafe charger](https://www.belkin.com/us/chargers/wireless/charging-stands-docks/boost-charge-pro-3-in-1-wireless-charger-with-magsafe-15w/p/p-wiz009/), which holds it up at the perfect angle to see the screen. Keeping the screen on for stretches of the day proved useful there too. I’d run a quick shortcut, adjust lights and other HomeKit accessories from Home, monitor video cameras, and AirPlay music to my HomePods. I can do most of that on my Mac too, but for some apps, quickly dipping in and out of them on an iPhone feel more lightweight than launching an app on the Mac to do the same thing.

To my surprise, even when the iPhone 12 Pro Max wasn’t sitting on its charger, keeping the display on at all times didn’t drain the battery as fast as I expected. Over the years, Apple has fine-tuned the battery consumption of its devices, and although powering the screen is a big draw on the battery, an idle iPhone draws less power than you might expect.

Also, it’s worth noting that it’s not like I keep my iPhone and iPad on 24/7. If I don’t need either one, I turned the screen off with the side button. That helps minimize battery drain, too, although I am sure my battery calculus will continue to shift as I spend more time away from home again. Still, I’ve been pleased with how well the batteries of my devices have held up to the experiment.

The entire experience has made me wonder how Apple might pair an always-on display with the iOS 15 update. Earlier this year, [Federico and I speculated](https://appstories.net/episodes/218/) that the Today page might be removed from iOS and replaced with the App Library. That got me wondering if a version of the Today page might move to the Lock Screen. That would be the perfect spot for a weather, battery, Fitness rings, and other widgets and notifications. Widgets have already been designed to use minimal resources, so putting them on the Lock Screen and allowing users to tap them to launch directly into the corresponding app would be handy.

The always-on route seems inevitable, though I’m not sure if it will be this year or not. The battery life of Apple’s larger iPhones feels ready for the transition, but it’s hard to imagine the feature being a good fit for an iPhone mini or SE. One option that I think is likely is that Apple would allow an always-on display to be turned off when you wanted to maximize the device’s longevity. Still, having lived with the screens of my iPhone and iPad on for long stretches for the past 4-5 months, I’m excited by the prospects of what the transition could mean for the way we use our iPhones.
***

==**21883**== Words

- **[My Obsidian Setup, Part 2: Themes, Mobile Quick Action and Toolbar, and Third-Party Plugins](https://club.macstories.net/posts/my-obsidian-setup-part-2-themes-mobile-quick-action-and-toolbar-and-third-party-plugins)**