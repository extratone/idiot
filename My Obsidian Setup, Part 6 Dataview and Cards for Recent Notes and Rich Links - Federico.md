---
share: true
dg-publish: true
---
# "My Obsidian Setup, Part 6: Dataview and Cards for Recent Notes and Rich Links"

*26-04-2022 07:41* 

> Exploring topics beyond our day-to-day coverage.
Exploring topics beyond our day-to-day coverage.

## [My Obsidian Setup, Part 6: Dataview and Cards for Recent Notes and Rich Links](https://club.macstories.net/posts/my-obsidian-setup-part-6-dataview-and-cards-for-recent-notes-and-rich-links)

I’ve spent a good portion of my holiday break studying and playing around with [Dataview](https://github.com/blacksmithgu/obsidian-dataview). If you’re into Obsidian and its plugin ecosystem, you’ve probably heard of Dataview already and seen the [examples of people](https://forum.obsidian.md/t/dataview-plugin-snippet-showcase/13673) who use this plugin to create all sorts of custom views in the app. But in case you’re not aware of it, here’s how I would describe it: Dataview lets you visualize notes from your Obsidian vault with tables and lists that support advanced filtering and sorting criteria. These tables are generated by Dataview **snippets**, which are code blocks that you drop into a note and that turn into a table when you switch to Preview mode in the Obsidian editor. Here’s what’s even more special about Dataview though: it’s based on an incredibly fast [query engine](https://blacksmithgu.github.io/obsidian-dataview/data-queries/) that lets you find hundreds of notes with a syntax that supports all sorts of note metadata, whether they are implicit to a note or explicitly declared by you.

What I just typed above is a lot to take in, right? I totally understand, which is why I’ve put off learning about Dataview for a long time, until I had a couple of weeks to tinker and experiment with it. It’s tricky not to get too conceptual and high-level when covering Dataview, so for the next few installments of this series on MacStories Weekly, I’m going to try my best to give you practical examples and guidance on what you can achieve with this plugin.

***

For starters – and I know this sounds obvious, but stay with me – I recommend checking out the detailed documentation provided by the Dataview developer [here](https://blacksmithgu.github.io/obsidian-dataview/). I don’t want to rehash a description of Dataview in this column, but I want to highlight the two key concepts behind it: data annotation and data querying.

Annotation refers to Dataview’s ability to read a specific bit of information from a note (or collection of multiple notes) in Obsidian using its own proprietary syntax. I’m referring, of course, to **metadata**. Broadly speaking, there are two kinds of metadata: those that are implicit to a note (they just “exist”), and those that you manually define using [YAML](https://help.obsidian.md/Advanced+topics/YAML+front+matter) or inline Dataview fields. For instance, the creation date of a note is an implicit metadata item since it’s just something that a note carries by default; same with a note’s file name, tags, modified date, and other built-in properties. Dataview can query all those values. At the same time, Dataview can *also* query metadata that you manually define in a note using its frontmatter (formatted as YAML) or a Dataview-specific inline syntax. You can read more about the different types of [metadata annotation here](https://blacksmithgu.github.io/obsidian-dataview/data-annotation/), and you can learn more about Dataview’s [query syntax here](https://blacksmithgu.github.io/obsidian-dataview/data-queries/).

There are plenty of pre-made Dataview examples you can check out [here](https://github.com/blacksmithgu/obsidian-dataview) and on the Obsidian forums, but allow me to share a few as well and, more importantly, detail how I’ve made [my Dashboard note](https://club.macstories.net/posts/extension-284) smarter and more powerful thanks to Dataview.

One of the first things I set out to build with Dataview was a visualization of my most recently modified notes from across the entire Obsidian vault. This is very easy to accomplish with Dataview. All it takes is to drop a code block like this one anywhere in a note:

```
```dataview
table file.mtime as "Last Modified"
where file.mtime < (date(today) + dur(1 day))
sort file.mtime DESC
limit 6
```
```

This Dataview snippet, when rendered in Preview mode, will generate a table that looks something like this:

![](https://cdn.macstories.net/friday-14-jan-2022-12-41-56-1642160525092.png)

A Dataview table for recently edited files.

If you take a look at the syntax above, I think you can understand how this all works under the hood. The code block tells Dataview to render a `table` for files `where` their modified date (the `file.mtime` metadata) is in the past day and `sort` them with descending order of modified date, which means from latest to oldest. The code block adds a `limit` of 6 notes found by Dataview, which should also display a `Last Modified` column showing the date of each parsed note. When the code runs, Dataview finds all notes matching these criteria in your vault and instantly renders them as a table.

That’s Dataview in a nutshell, and once you learn this basic syntax and approach, a world of note-filtering possibilities opens up to you in Obsidian. For example, take the following snippet:

```
```dataview
list FROM #quickLink
sort file.name ASC
limit 6
```
```

This code tells Dataview to render a bulleted `list` with 6 notes that have been tagged with `#quickLink` and sort them alphabetically by file name. When rendered, here’s the result we get:

![](https://cdn.macstories.net/friday-14-jan-2022-12-42-36-1642160560752.png)

You get the idea by now. These are the basics of Dataview, and like I mentioned above, I recommend playing around with some of these common snippets to understand how it all works behind the scenes and how Dataview could be useful for your Obsidian setup. As always with any kind of automation, do not be afraid to tinker, throw away things, and start over: it’s all part of the learning process.

Now let’s take things up a notch. One of the most exciting developments in the Obsidian-Dataview space lately has been the release of [version 4.4 of Minimal Theme](https://github.com/kepano/obsidian-minimal/releases/tag/4.4.0). I previously covered Minimal [here](https://club.macstories.net/posts/my-obsidian-setup-part-2-themes-mobile-quick-action-and-toolbar-and-third-party-plugins), and I believe it is, by far, the best alternative look you can install in Obsidian. Version 4.4 of Minimal has introduced Cards, which is a custom appearance mode that renders Dataview snippets as **a grid of cards** rather than a table. You can read more about Minimal and Cards [here](https://github.com/kepano/obsidian-minimal) and watch a demo video [here](https://youtu.be/NZrj4NaJtkk). Essentially, if you want to visualize Dataview snippets in a note as cards, install Minimal Theme and just drop the following YAML syntax at the top of a note:

```
---
cssClasses: cards
---

```

Once you do that, a Dataview table will be displayed by Minimal Theme as a grid of “note cards” instead, which looks fantastic in my opinion.

![](https://cdn.macstories.net/friday-14-jan-2022-12-43-53-1642160639865.png)

Cards in Obsidian.

Here, for instance, is the aforementioned table of recently modified notes displayed as cards instead:

![](https://cdn.macstories.net/friday-14-jan-2022-12-45-52-1642160757607.png)

The same table rendered as a grid of cards.

I love how cards are rendered by Minimal and I especially appreciate the hover effects – supported on iPad too – that you see when you place the cursor on top of a note. If you have the Page Preview plugin enabled in Obsidian, you can hover with the cursor over a linked file name and you’ll get a popup with a preview of the page without even having to open it.

The design of Minimal cards and the integration with Dataview got me thinking: what else could I display as cards in Obsidian featuring multiple fields and perhaps even inline images? And another question followed immediately: what if I could figure out a way to save URLs in Obsidian as “rich links” with thumbnail previews, similarly to how you can save links in Craft or Apple Notes?

This took me a few days of work and fine-tuning, but here’s the result:

![](https://cdn.macstories.net/friday-14-jan-2022-12-49-39-1642160984467.png)

Rich links in my Dashboard note.

Now, you’re probably thinking that my screenshot looks nothing like Obsidian. And yet, the grid of links displayed as cards with metadata and the interactive ‘Mark as Done’ button is entirely powered by Dataview and based on a code block that is rendered as a grid of cards thanks to Minimal Theme.

Let me explain all the steps involved in this system and share all the pieces you’re going to need if you want to start using it yourself. First, make sure you install [Dataview](https://github.com/blacksmithgu/obsidian-dataview), [Minimal Theme](https://github.com/kepano/obsidian-minimal), and the [Buttons](https://github.com/shabegom/buttons) plugin. I’m going to talk about Buttons more in depth in the future, but it’s basically a plugin that lets you create interactive buttons (again, based on custom code snippets) that execute specific commands when they’re clicked in preview mode. Also, install the [MetaEdit](https://github.com/chhoumann/MetaEdit) plugin, which will allow Buttons to modify properties of the rich links we’re going to save in Obsidian, and [Sortable](https://github.com/alexandru-dinu/obsidian-sortable), which adds dropdown menus with sorting options to Dataview tables.

Next up, create a ‘Links’ folder in the root of your Obsidian vault. While in the past I would save links in Obsidian by, well, just pasting raw URLs in my Dashboard note, this new system is based on Dataview, which means all the links we’re saving are standalone notes stored in a folder. Here’s what one of these notes looks like:

![](https://cdn.macstories.net/friday-14-jan-2022-12-50-12-1642161016906.png)

A standalone note for a link.

As you can see, the note features a frontmatter with YAML-based metadata. These individual pieces of metadata are the values that Dataview will query and process to put together a table, which will then be rendered as a grid of cards by Minimal Theme. Which begs the question: how can you actually save links from Safari or any other app with this kind of formatting?

This is where Shortcuts comes in. To turn a webpage I want to save for later in Obsidian (usually because it’s something I want to check out / buy / link on MacStories; articles I want to read go in [Matter](https://hq.getmatter.app/)), I’ve put together a shortcut called **Save Link** that extracts metadata directly from a webpage’s source. Specifically, the shortcut can parse a webpage’s HTML and find its [Open Graph tag](https://ogp.me/) for the cover image, which will then be rendered by Dataview and Minimal Theme as an inline image for the “rich link” we’ve saved in Obsidian. Whenever you see a note-taking app that supports saving URLs as rich links (such as Notes or Craft), they’re always checking the same `og:image` meta property in HTML to see which image should be presented as the thumbnail preview of the URL. I made a shortcut that extracts the same information and saves it as part of a note’s YAML frontmatter in Obsidian.

![](https://cdn.macstories.net/friday-14-jan-2022-12-50-49-1642161053750.png)

The shortcut extracts Open Graph tags via regular expressions.

You can run Save Link from the share sheet on iPhone and iPad in Safari and Safari View Controller; alternatively, you can run the shortcut manually from the Home Screen or the Shortcuts app, and you’ll be prompted to paste the URL you want to save in Obsidian.

![](https://cdn.macstories.net/friday-14-jan-2022-12-54-50-1642161297622.png)

There are some details worth noting about the shortcut: tracking parameters are automatically removed from URLs thanks to a regex that [Robb Knight put together](https://rknight.me/apps/tracker-zapper/); the link is saved alongside a timestamp so you can see when you first saved a webpage in Obsidian; and, you can configure the folder where links should be saved as notes in the ‘Save File’ action at the end of the shortcut as well as modify the default text for the note and any YAML metadata tags.

You can [download my Save Link shortcut here](https://www.icloud.com/shortcuts/9f792ec2bc684f799ddeb6ec30f51068).

With a system in place to save links from Safari as standalone notes in Obsidian, I needed to figure out a way to query them all and visualize them as a table in Obsidian with Dataview. My idea was relatively simple: I wanted to query all notes saved in the ‘Links’ folder, but only display the ones that had a `status` metadata value of `new`, meaning that Dataview would only show me *new* links I recently saved in the app. But that meant I also had to come up with a way to mark a link as “not new” anymore when I was done with it.

To make this work, I used DataviewJS and modified a script shared by the creator of the MetaEdit plugin [here](https://github.com/chhoumann/MetaEdit). [DataviewJS](https://blacksmithgu.github.io/obsidian-dataview/api/intro/) is a JavaScript API for Dataview that lets you combine arbitrary JS code with regular Dataview queries, tables, and access to the Obsidian plugin API. Basically, it means you can put together more advanced Dataview code blocks that do all the things non-JS Dataview snippets can do, *but* you have greater freedom since you can run any code you want in them. This is a topic I’ll revisit in the next installment of this series for another script I created in DataviewJS.

In the case of rich links, I liked the idea of a button I could click in the table to change a note’s `status` from `new` to `done`. DataviewJS can do this because it has access to the API for the Buttons and MetaEdit plugins, which can create buttons and change frontmatter values in notes, respectively. So, after a bit of trial and error, here’s how I modified the DataviewJS snippet I found online to parse and visualize my rich links:

```
```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api
const {createButton} = app.plugins.plugins["buttons"]
dv.table(["Image", "Title", "Note", "Link", ""], dv.pages('"Links"')
.where(p => p.status == 'new')
.sort(p => p.timestamp, 'desc')
.map(p=> ["![](" + p.cover + ")", p.title, "📝 " + p.file.link, "**[" + "🔗 " + p.domain + "](" + p.link + ")**", createButton({app, el: this.container, args: {name: "✅ Mark as Done"}, clickOverride: {click: update, params: ['status', 'done', p.file.path]}})])
)
```
```

When you switch to preview mode in Obsidian, this is table you get:

![](https://cdn.macstories.net/friday-14-jan-2022-12-57-29-1642161454060.png)

Dataview’s default table mode.

As you can see, the script queries Obsidian for notes in the Links folder that have a `status` set to `new`, creates columns for Image, Title, Note, and Link, then maps metadata values for each note to the respective column. The Markdown image syntax is used in the JavaScript code to render native images in the table. The final step was to adopt Minimal Theme’s CSS classes to turn this table into a grid of cards for each link, which would also display a ‘Mark as Done’ button at the bottom of each link card. So I added this frontmatter code to my Dashboard note:

```
---
cssClasses: table-max, cards, cards-16-9, cards-align-bottom
---

```

And the result is what I always wanted to have in Obsidian:

![](https://cdn.macstories.net/friday-14-jan-2022-12-57-59-1642161483896.png)

The same table as cards.

Each card lets me do three things: I can open the URL in Safari by tapping the link; I can open the standalone note associated with each link if I want to add some comments to it; or I can click the ‘Mark as Done’ button in the card, which will instantly change the note’s status and remove it from my Dataview visualization (but the note itself will remain in Obsidian). I genuinely *love* the workflow I’ve built here: it lets me save links in Obsidian just as quickly as before, but it adds more context around each link with titles and image previews, which I didn’t have before when I was just pasting raw URLs in plain text. I hope you’ll find it useful, too.

***

The freedom granted by this dual Obsidian-Shortcuts system is unprecedented for note-taking apps on Apple platforms. It does require some understanding of how Dataview works and a bit of preparation upfront, which is exactly why I’m writing about this stuff – so other people can use the same system. As I noted above, this is just my first story on what I’ve built with Dataview in Obsidian: stay tuned, it’s [going to be a fun journey](https://twitter.com/viticci/status/1481687474753658890).
***

==**14261**== Words
```
- **[My Obsidian Setup, Part 6: Dataview and Cards for Recent Notes and Rich Links](https://club.macstories.net/posts/my-obsidian-setup-part-6-dataview-and-cards-for-recent-notes-and-rich-links)**
- [My Obsidian Setup, Part 7 A YouTube Watch-Later System, Powered by Shortcuts and Dataview - Federico](My%20Obsidian%20Setup,%20Part%207%20A%20YouTube%20Watch-Later%20System,%20Powered%20by%20Shortcuts%20and%20Dataview%20-%20Federico.md)