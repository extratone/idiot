---
share: true
dg-publish: true
---
# "OverClip: A System for Saving Podcast Clips in Obsidian as Text"

*26-04-2022 07:41* 

> Get help and suggestions for your iOS shortcuts and productivity apps.
Get help and suggestions for your iOS shortcuts and productivity apps.

## [OverClip: A System for Saving Podcast Clips in Obsidian as Text](https://club.macstories.net/posts/overclip-a-system-for-saving-podcast-clips-in-obsidian-as-text)

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-8-1627645732035.png)

Excerpts of podcasts are notoriously hard to share. In recent years, the situation has improved with share extensions in apps like Overcast and Castro that allow you to save or share a timestamped URL or audio or video clip, which I love, but of course, I wanted something more.

URLs and clips files solve the sharing problem on social media quite nicely, but they don’t do me much good if I want to quote something I hear on a podcast in a story I’m writing. Even if I save short clips, I need to put them somewhere, find them again, register, transcribe, and find a URL to link the clip.

Since I started using Obsidian, I’ve been saving quotes from stories I read along with a link back to the source and other metadata using Shortcuts. The format is simple but effective because everything is plain text, allowing me to use the excerpt as a blockquote in a story and link it properly. Here’s what one of those notes looks like in Obsidian:

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-9-1627645876049.png)

A Markdown-formatted plain text research note.

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-10-1627645876035.png)

The same note in Obsidian’s Preview mode.

The extra content you see at the top in the plain text version of the note is [YAML front matter](https://en.wikipedia.org/wiki/YAML), a format for metadata that is useful for finding and organizing large collections of research material.

I’ve been thinking about ways to expand this rather simple text-based setup to incorporate other media that I want to save for research purposes. That led me to think about podcasts, which resulted in the creation of OverClip, a shortcut that takes snippets of audio from podcast episodes using Overcast’s excellent shortcuts and share sheet features and converts the audio into text. Then, OverClip compiles a plain text note in Obsidian complete with metadata, a text version of the audio clip, and the audio clip embedded in the note for playback.

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-11-1627646101978.png)

Overcast clip sharing.

OverClip, which runs from the share sheet, requires Overcast’s paid subscription for clip sharing, Toolbox Pro for converting audio and saving the results of the shortcut to a local folder on an iPhone or iPad, and Obsidian. The first step is to select a clip you want to save from a podcast episode in Overcast using the share sheet to pick Overcast’s audio-only option.

When OverClip is selected from the share sheet, the first thing it does is send the audio clip to Toolbox Pro, opening the app to process the audio. You’ll notice that the second step of the shortcut is a Wait action. That’s because Toolbox Pro needs time to run the audio-to-text conversion. Based on my tests, the Wait timer needs to be set to roughly half the length of the clip. If the wait is too short, the plain text note with embedded audio will still be created in Obsidian, but it won’t include the converted audio as a blockquote. I’ve set the wait to 15 seconds by default because I rarely save snippets longer than that and 30 seconds is the clip length to which Overcast defaults, but you may want to adjust the wait after using the shortcut for a while.

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-1627655821155.png)

Converting audio to text with OverClip using Toolbox Pro.

You could use a Wait to Return action here instead of Wait, and OverClip will pause until you return to Shortcuts. However, if you go that route, don’t return to Shortcuts too soon because even after Toolbox Pro says it has finished converting your audio to text and putting it on the clipboard, the shortcut may not pick up the blockquote. Because I don’t trust Impatient John to wait long enough, I prefer the Wait action.

While I’m on the subject of caveats, OverClip doesn’t work when Toolbox Pro is in Slide Over. This may be an iPadOS 15 bug, but Toolbox Pro needs to run full-screen or in Split View for everything to work.

Getting back to how OverClip works, you’ll see I stash the text from the audio clip in a variable until I’m ready for it. The next action is Overcast’s Current Episode Info action, which is packed with information about whatever is currently playing in the app, which happens to also be the episode from which you’re sharing a clip.

I also grab the current date and time in a custom format where everything is separated by dashes, which, unlike colons, are safe characters for Obsidian file names. To the date, I append ‘Overcast Excerpt,’ putting the two together in a Text action that will become the audio file’s name.

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-2-1627656614593.png)

Gathering the components for my Obsidian note.

The biggest Text action near the end of the shortcut is where the body of the note is put together. The top section is YAML-formatted front matter that lists the name of the podcast, the episode, when it was saved, the source URL, the timestamped URL, and the episode summary, which is usually a subtitle for most podcast episodes. This metadata is handy for finding and filtering notes and is only visible in Obsidian’s editing mode. In preview, the YAML data disappears, and all you’ll see is your formatted note.

Beneath the metadata is a Markdown-formatted link to the exact spot in the podcast episode where the clip begins, followed by a Markdown blockquote of the text pulled from the audio clip. Finally, the audio clip is embedded at the bottom of the note. Obsidian uses the syntax `![[filename]]` to embed a variety of different kinds of media in plain text notes including PDFs and popular image, audio, and video file formats. After renaming the file and saving the audio clip into a subfolder called ‘Assets,’ which is a subfolder of my ‘Inbox’ folder, dropping the file name into the note using Obsidian’s file-embed syntax allows me to re-listen to the clip anytime.

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-13-1627646334748.png)

OverClip’s text and file-saving actions.

Once the body of the note has been built, OverClip uses Toolbox Pro to construct the file names for the note and saves to a local Inbox folder in ‘On My iPad’ that I use for items I send to Obsidian from the share sheet. Finally, the shortcut uses Toolbox Pro’s Return to Home Screen action to get out of that app and back to the Home Screen so OverClip can relaunch Overcast, so I can resume listening to the podcast.

OverClip isn’t perfect. There are the caveats I mentioned above, and the shortcut takes a while to run, but that hasn’t outweighed the utility of the shortcut for me overall. The audio-to-text conversion is surprisingly good and readable if your clip’s audio is clear and there aren’t multiple people talking at once. Moreover, even if there’s an error in speech recognition, you always have the audio clip available to playback.

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-14-1627646493638.png)

A plain text note created by OverClip, which includes a perfect conversion of the audio to the quoted text.

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-15-1627646569157.png)

The same note in Obsidian’s Preview mode, including an inline player to re-listen to the clip.

You can download OverClip [here](https://www.icloud.com/shortcuts/f355747701554257a2b02a2d7361ae41).

[Submit a Shortcut Request](https://docs.google.com/forms/d/e/1FAIpQLSeViYJRP69lNKgbmNWqxY1iEnz851gLE375swzC12Qarm-RxA/viewform?usp=sf_link)
***

==**6772**== Words

- **[OverClip: A System for Saving Podcast Clips in Obsidian as Text](https://club.macstories.net/posts/overclip-a-system-for-saving-podcast-clips-in-obsidian-as-text)**