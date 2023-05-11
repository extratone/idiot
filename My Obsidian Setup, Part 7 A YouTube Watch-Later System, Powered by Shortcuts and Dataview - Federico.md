---
share: true
dg-publish: true
---
# "My Obsidian Setup, Part 7: A YouTube Watch-Later System, Powered by Shortcuts and Dataview"

*26-04-2022 07:43* 

> Exploring topics beyond our day-to-day coverage.
Exploring topics beyond our day-to-day coverage.

## [My Obsidian Setup, Part 7: A YouTube Watch-Later System, Powered by Shortcuts and Dataview](https://club.macstories.net/posts/obsidian-setup-part-7)

In last week’s issue of MacStories Weekly, I explained how I turned my Dashboard note into a richer, more interactive hub thanks to [Dataview snippets displayed as cards](https://club.macstories.net/posts/my-obsidian-setup-part-6-dataview-and-cards-for-recent-notes-and-rich-links), which show me a grid of links I’ve recently saved, plus a collection of recently modified notes. As I covered last week, the cards displayed in my Dashboard are an alternative look for a [Dataview](https://github.com/blacksmithgu/obsidian-dataview) table made possible by [Minimal Theme](https://github.com/kepano/obsidian-minimal); those cards feature an interactive ‘Mark as Done’ button that takes advantage of the [Buttons](https://github.com/shabegom/buttons) and [MetaEdit](https://github.com/chhoumann/MetaEdit) plugins to change each linked note’s status from `new` to `done`.

It’s been fun watching members of [our Discord](https://club.macstories.net/faq/discord) as well as the [Obsidian forums](https://forum.obsidian.md/) tweak and adapt my setup to their needs, so this week I want to share something else I’ve built with the same system that has fundamentally changed my Obsidian workflow: a watch-later system for YouTube videos powered by Shortcuts, Markdown files, and, of course, Dataview.

Let’s actually start from the end result, so you can immediately have some context as to what I’m referring to:

![](https://cdn.macstories.net/wednesday-19-jan-2022-15-42-34-1642603361385.png)

My watch-later system in Obsidian.

As you can see, the look of my ‘YouTube Videos’ note is fairly similar to the rich link section of the Dashboard note I covered last week. This is a note that contains a Dataview snippet, which aggregates notes from a specific folder that are rendered as a table. In plain text, this is what the entire note looks like:

![](https://cdn.macstories.net/friday-21-jan-2022-11-44-10-1642761855493.png)

My YouTube Videos note before being rendered in preview mode.

You’ll notice the `cssClasses` for Minimal Theme, which I also covered last week. That’s the special syntax that makes it possible to render a standard Dataview table as a grid of cards. In fact, if I remove the YAML syntax for cards, here’s what the same Dataview snippet is rendered as:

![](https://cdn.macstories.net/friday-21-jan-2022-11-46-48-1642762013215.png)

The same Dataview snippet, rendered without the extra CSS for cards.

So far, this is all pretty standard and in line with my explanation from last week. For this system, however, I had to put quite some time into the *shortcut* that makes it possible to save YouTube links as standalone Markdown notes with the proper metadata necessary for this Dataview snippet to work.

Let’s back up a little. Like many others these days, I enjoy watching a lot of YouTube videos from my favorite channels, and I don’t think I’m alone in feeling like there’s always more content than time I have for it in a regular day. So, I want to save links to these videos somewhere and make sure I can find them again later and catch up with them at my own pace. For a while I tried to use YouTube’s built-in Watch Later playlist, but I don’t like how many taps are required in the YouTube UI to open the playlist. I also tried to save links to YouTube videos in read-later systems like Reading List, [Raindrop](https://raindrop.io/), [GoodLinks](https://goodlinks.app/), and [Matter](https://hq.getmatter.app/); the problem with those services is that they’re always optimized for articles first and foremost, and they never offer video-specific filters or details such a displaying the duration or channel names of saved videos. Therefore, once I had a good foundation in place for saving rich links and displaying them with Dataview, I realized I wanted to build the same system, but specifically optimize it for YouTube content.

The trickiest part about turning a YouTube URL into a note that contains information about the video is **extracting metadata about the video** from the YouTube website. YouTube has an API, but it requires a lot of configuration for OAuth-based authentication in Shortcuts, and I didn’t have the time, nor patience, to go down that road. So as is often the case for web services that do not want to cooperate with Shortcuts through native actions or an easily accessible API, I turned to a tried and proven method:

Scraping webpages with regex.

The shortcut I put together is called Save YouTube Link and, like last week’s Save Link shortcut, it turns a link (passed from the YouTube app, the share sheet, or manually pasted into Shortcuts) into a Markdown note in Obsidian with YAML metadata. These bits of metadata include the original video URL, channel name, video title, thumbnail URL, and duration of the video. Here’s what a note created by Save YouTube Link looks like:

![](https://cdn.macstories.net/friday-21-jan-2022-11-52-00-1642762325976.png)

A YouTube link saved as a note with metadata.

As you can imagine, all these metadata values are then parsed by Dataview and used to assemble a table that presents notes as rich links with thumbnails, links, duration, and a button to mark videos as “watched” in Obsidian. Once again, here’s what the final table looks like in Cards mode:

![](https://cdn.macstories.net/friday-21-jan-2022-11-53-26-1642762415245.png)

And here is the Dataview snippet that powers it all:

```
---
cssClasses: cards, cards-align-bottom, cards-16-9
tags: ['quickLink']
---
```

```
```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api
const {createButton} = app.plugins.plugins["buttons"]
dv.table(["Image", "Name", "Length", "Saved", "Link", ""], dv.pages('"YouTube"')
.where(p => p.status == 'New')
.sort(p => dv.date(p.saved), 'desc')
.map(p=> [p.thumb, "📝 " + p.file.link, p.duration, p.saved, "" + "[" + "🔗 " + p.channel + "](" + p.URL + ")", createButton({app, el: this.container, args: {name: "📺 Watched"}, clickOverride: {click: update, params: ['status', 'Watched', p.file.path]}})])
)
```
```

It is, effectively, the same setup as my Dashboard featuring rich links, but it uses another folder as source for notes that are formatted differently. Which brings it all back to the shortcut required to save YouTube links as Markdown notes with a YAML frontmatter.

The shortcut takes a very crude, yet effective approach to scraping YouTube webpages for information: it downloads YouTube links as webpages using the ‘Get Contents of URL’ action, converts the result to an HTML variable, then uses multiple regular expressions hard-coded to match specific strings of text that contain the information we need. When I say “crude”, this is what I mean:

![](https://cdn.macstories.net/thursday-20-jan-2022-13-10-16-1642680621918.png)

Hard-coded regular expressions to scrape YouTube for video metadata. In this case, channel names and video titles.

Scraping is never a reliable technique to get the information you want out of a webpage. Websites are redesigned, how source code is presented to web browsers (or the ‘Get Contents of URL’ action) changes over time, and your hard-coded scraping script may stop working and require an update. But sometimes scraping is the only or most effective way, and this was the case for me and this YouTube shortcut. I know that it may break and require a fix eventually, but on balance, I’d still prefer that occasional bug fix over spending days trying to figure out Google authentication flows and the YouTube API in Shortcuts.

I’ve been using this scraping-based YouTube shortcut for nearly two months, and it has always worked reliably, so I’m very happy with it for now. That said, be aware that it is based on some ridiculous regular expressions that have been hard-coded into the shortcut to make some sense out of the complicated HTML that YouTube returns. My favorite example is this wild series of actions I had to put together to extract video duration as milliseconds from YouTube and convert it to a readable duration string formatted with minutes and seconds.

![](https://cdn.macstories.net/thursday-20-jan-2022-13-23-28-1642681413982.png)

Scraping video duration from YouTube.

Once all the scraping is done and variables are ready at the end of the shortcut, a ‘Text’ action prepares all the YAML syntax we need for Dataview to work in Obsidian:

![](https://cdn.macstories.net/thursday-20-jan-2022-13-26-10-1642681576313.png)

The newly-generated Markdown note featuring YouTube metadata for the selected video is then saved to a folder in Obsidian, and the video will show up in the note that contains the Dataview snippet as a new card:

![](https://cdn.macstories.net/friday-21-jan-2022-11-59-21-1642762772392.png)

Saving YouTube links on iPhone.

There is one important detail I should note here: my Dataview snippet assumes that all YouTube links are saved as notes in a folder in the root of your vault called ‘YouTube’. If you want to save notes in a different folder, make sure you modify this part of the Dataview snippet to include the path of the folder you want to use:

```
dv.pages('"YouTube"')
```

So that’s the system I’ve built. Now whenever I find a YouTube video I want to watch later, I can save it with the Save YouTube Link shortcut in Obsidian, load my YouTube Videos workspace, and Dataview will show me a grid with cards for all the videos I’ve saved. I can tap links in the grid to reopen videos in the YouTube app for iPhone or iPad (or the website on Mac), and click the ‘Watched’ button when I’m done with them to remove them from the grid. Thanks to the [Sortable](https://github.com/alexandru-dinu/obsidian-sortable) plugin, the Dataview table/grid can be sorted by any of the properties available for videos; by default, the grid is sorted by date saved from latest to oldest, but you can also sort videos by title, channel name, or duration.

![](https://cdn.macstories.net/friday-21-jan-2022-12-01-47-1642762916605.png)

Sorting videos thanks to the Sortable plugin.

I love what Obsidian, Dataview, and Shortcuts have allowed me to create here. This is the happiest I’ve ever been with a watch-later solution for YouTube videos, and I hope you’ll find it useful too.

You can find my Dataview snippet as a private gist [here](https://gist.githubusercontent.com/viticci/bc3c8753ef73c28dfe9a28ecedece98b/raw/47bb45ce78c003ebbd93cf3060cd05f7ee4075f4/YouTube%2520Videos.md), and you can [download my Save YouTube Link shortcut here](https://www.icloud.com/shortcuts/44693b02891a44a59b176ac626cf077b).
***

==**9091**== Words

- **[My Obsidian Setup, Part 7: A YouTube Watch-Later System, Powered by Shortcuts and Dataview](https://club.macstories.net/posts/obsidian-setup-part-7)**