---
share: true
dg-publish: true
---
# "My Obsidian Setup, Part 8: Simplifying Thought Capture with 'On My Mind'"

*26-04-2022 07:41* 

> Exploring topics beyond our day-to-day coverage.
Exploring topics beyond our day-to-day coverage.

## [My Obsidian Setup, Part 8: Simplifying Thought Capture with 'On My Mind'](https://club.macstories.net/posts/my-obsidian-setup-part-8-simplifying-thought-capture-with-on-my-mind)

The last time [I wrote about appending text](https://club.macstories.net/posts/shortcuts-essentials) to my Dashboard note in Obsidian in November 2021, I shared two distinct methods to do so, both based on shortcuts. The first one relied on the [QuickAdd plugin](https://github.com/chhoumann/quickadd) and its ability to insert text into specific sections of notes in Obsidian; QuickAdd doesn’t support passing text to its input field from Shortcuts via, say, a URL scheme, so my shortcut worked by asking you to type some text first, which it then copied to the clipboard so you could paste it into QuickAdd’s UI. An ingenious workaround, but not an elegant one.

The second method was based on [Shortcuts’ native Files actions in iOS 15](https://club.macstories.net/posts/automation-academy-diving-deeper-into-shortcuts-files-actions-for-ios-and-ipados-15), and it worked by directly inserting text into the Dashboard.md document stored in the Files app (I keep my Obsidian vault in local storage and use the Obsidian Sync service). Over time, I’ve grown to prefer this method of appending text to my Dashboard: it’s faster, I don’t see the QuickAdd interface when Obsidian launches, and, more importantly, I don’t have to tap ‘Paste’ in the QuickAdd input UI.

Over the past few months, however, I’ve also realized that I wanted to simplify my workflow for capturing ideas and make it more flexible. So today, I’m sharing a spin-off of my original Append to Dashboard shortcut called **On My Mind**, which is based on the same technique but specifically optimized for fast idea capture on multiple Apple devices. The shortcut is largely similar to the one I shared last year, but there are some key differences regarding user interaction and text-entering methods I’m going to describe below.

***

First, the simplification occurred because I realized I don’t need multiple sections in my Dashboard note to save thoughts. I found that I was always dropping thoughts and ideas into the ‘On My Mind’ section of the note, but the original Append to Dashboard shortcut would always prompt me to pick a specific section from the note every time. I wanted to drop that extra section-picking step and default to always *prepending* new thoughts at the top of the On My Mind section. Prepending instead of appending is a new thing for me, but I’ve discovered that it works better for my brain since it means most recent ideas are also the most recent lines of text at the top of the section.

So, for On My Mind to work, you’ll have to enter the Markdown syntax of the specific section of your Dashboard note where you always want to save your thoughts. You’ll be asked to complete this step at setup, but you can also tweak this in the ‘Text’ action near the beginning of the shortcut, as pictured below:

![](https://cdn.macstories.net/cleanshot-2022-03-24-at-12-17-26-2x-1648120666111.png)

You can define a specific section of the Dashboard where you want to prepend text.

Prepending text at the top of a section is also much easier to do in Shortcuts than appending, which required regular expressions to determine where a section ended and another began. When we’re prepending text, all we need to do is replace the Markdown heading of the section with the heading *plus* the text we’re appending. This is what it looks like in the shortcut:

![](https://cdn.macstories.net/cleanshot-2022-03-24-at-12-35-44-2x-1648121761820.png)

Prepending text to a section of a note in Obsidian. You can see how the original text is modified and re-saved as the same document in the same folder.

With this new system, saving random ideas and thoughts in my Dashboard note in Obsidian couldn’t be easier. From the Home Screen widget on my iPhone and iPad, I can type some text and it gets immediately inserted at the top of the On My Mind section:

![](https://cdn.macstories.net/friday-25-mar-2022-11-43-53-1648205044632.png)

Saving thoughts from the Home Screen via On My Mind.

The process is even faster on the Mac, where I can trigger the shortcut with a system-wide hotkey (⌘⌥⌃O for me) and capture ideas from anywhere on my computer. I’ve been doing this with [Raycast](https://www.raycast.com/), and I love it.

![](https://cdn.macstories.net/cleanshot-2022-03-25-at-11-44-43-2x-1648205090747.png)

On macOS, I can trigger On My Mind’s manual text input from anywhere.

All this has been great for me, but there was a missing piece: dictation. I often find myself in two similar, but different, scenarios in which I’d prefer to save ideas by dictating them without any manual interaction whatsoever: when I’m in the car, and when I’m wearing AirPods and doing things around the house. How could I extend On My Mind so it would fall back to dictation input only in those scenarios?

As it turns out, Apple doesn’t provide users with a way to check the audio playback destination of the device where a shortcut is running. Fortunately, third-party developers have thought about this problem and there are a couple of options to add audio-checking capabilities to Shortcuts. My favorite, and the one I’m now using in On My Mind, is the ‘Get Audio Playback Destination’ action offered by the free [Actions](https://apps.apple.com/us/app/actions/id1586435171) app, a MacStories team favorite. This action works on iPhone and iPad only, and it does not detect AirPlay devices, but it can correctly identify whether audio is playing through your device’s speakers, AirPods, or a connected Bluetooth device. Thanks to the Actions app, my shortcut can now quickly check where audio is playing; the action runs in a fraction of a second and works entirely in the background; the only requirement is that you [download the Actions app from the App Store](https://apps.apple.com/us/app/actions/id1586435171) before trying dictation with On My Mind.

When the action from Actions (I know, *I know*) runs, it first checks if the Audio Playback Destination variable contains the word ‘AirPods’. If it does, the shortcut will bring up the native dictation UI instead of keyboard input so you can dictate your text. Dictation parameters (language, pause, etc.) can be configured as always in the Shortcuts editor, and text is immediately transcribed as-you-speak thanks to Apple’s fast on-device processing. The dictated text is turned into actual text and prepended to a section of a note in Obsidian, just like I described above.

![](https://cdn.macstories.net/friday-25-mar-2022-11-49-11-1648205359235.png)

Dictating text when AirPods are connected.

I took a slightly different approach for connected devices that are not AirPods. I did this because of an issue that is very specific to me; if you also have this problem, this is likely going to apply to you as well; if it doesn’t, feel free to delete the entire block of actions I’m going to describe below.

I don’t have a CarPlay-enabled car, which means my iPhone automatically connects to it using a standard Bluetooth connection. That has been mostly okay for music playback (although I don’t see album artwork for music on the car’s display), but the system has been absolutely *horrible* for Siri and any kind of voice input. There are multiple issues here: if I try to activate Siri, dictate a message, or send an audio message via WhatsApp, there’s a 5-second delay between pressing the button and voice input actually activating; second, I don’t know why, but the voice quality of Siri in this mode is terrible, making it sound like a robot stuck in a tin can; third, and perhaps worst of all, if I do decide to dictate messages this way, the car’s microphone also makes me sound like that robot. And it’s very strange, because this only applies to voice input for Siri and dictation; people say that I sound crystal-clear on phone calls I take from the car.

I have no idea why this is the case, and I can’t wait to get a CarPlay-enabled car, but I wanted to find a solution to this problem for my On My Mind shortcut in the meantime. The solution I came up with may be a little unconventional, but it works: if the shortcut detects that it’s connected to a Bluetooth output device that *isn’t* AirPods, Bluetooth is temporarily turned off, text can be dictated via the iPhone’s built-in microphone, then Bluetooth is immediately re-activated so my iPhone can reconnect to my car’s Bluetooth system. Here’s what this flow of actions looks like in the shortcut:

![](https://cdn.macstories.net/cleanshot-2022-03-25-at-11-27-39-2x-1648204069242.png)

How the shortcut turns off Bluetooth and instantly re-enables it.

With this method, I’ve been able to save the occasional idea I have while driving without a) distractions and b) having to deal with whatever is going on between my iPhone and the car’s terrible Bluetooth voice input.

The result of this optimization process is the fastest, most versatile idea-capturing workflow I’ve ever had with Obsidian or with any note-taking app, really. Now, no matter the device I’m using and no matter how I’m triggering the shortcut, I know I can invoke On My Mind and I’ll be able to quickly capture a thought in seconds and send it to a section of my Obsidian dashboard right away, with no further interactions. This shortcut has genuinely helped me forget fewer things and use Obsidian even more, and I hope you’ll find it useful as well.

You can [download On My Mind here](https://www.icloud.com/shortcuts/e071866a3d444cbda818b3a13d7a45a1).
***

==**8590**== Words

- **[My Obsidian Setup, Part 8: Simplifying Thought Capture with 'On My Mind'](https://club.macstories.net/posts/my-obsidian-setup-part-8-simplifying-thought-capture-with-on-my-mind)**