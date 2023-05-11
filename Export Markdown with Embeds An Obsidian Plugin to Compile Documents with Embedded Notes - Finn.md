---
share: true
dg-publish: true
---
# "Export Markdown with Embeds: An Obsidian Plugin to Compile Documents with Embedded Notes"

*26-04-2022 07:41* 

> September 23, 2021
[September 23, 2021](https://club.macstories.net/posts/export-markdown-with-embeds)

![](https://cdn.macstories.net/ivborw0kggoaaaansuheugaac50aaajwcayaaaakgq9xaaaacxbiwxmaaastaaaleweampwyaaam-1632330072263.png)

Compiling a table of contents.

Export Markdown with Embeds is a customizable plugin that compiles documents with embedded nested documents into a single document. Obsidian’s [note embed feature](https://help.obsidian.md/How+to/Embed+files) allows you to embed a file or note in another note using the syntax: `![[My Note]]`. The contents of embedded notes will be shown in Obsidian’s preview mode in place of the link. The feature is a good way to break up longform writing into sections but still be able to review it as a single document. However, when you export a note that has others embedded in it, the exported text includes the note, not the *contents* of embedded notes.

When the Export Markdown with Embeds plugin is run, it swaps the contents of any linked notes into the note that you’re exporting. This makes it easy to to create a note that serves as a table of contents of embedded notes for navigating between sections of a long document. You can use Obsidian’s built-in preview functionality to read the full document in the app or use Export Markdown with Embeds to export it as Markdown-formatted text.

The plugin features a primary command and two convenience commands. The main command presents a popup with export options. The first option allows you to save the export as a new note with the first heading as the title if possible. Alternatively, you can copy the exported material to the clipboard, in which case all [internal links](https://help.obsidian.md/How+to/Internal+link) will automatically be replaced with callback links that open the linked file in Obsidian.

![](https://cdn.macstories.net/image-1632357427005.png)

Exporting a table of contents with embedded notes to the clipboard.

The second option is 'Increase headings of referenced notes '. Enabling this option will automatically increase the level of all headings in an embedded note by 1, creating a hierarchical structure. This allows you to create a 'Chapter ’ note that contains an embedded 'Section ’ note, and each heading in the 'Section ’ note will be exported as a subheading of 'Chapter '. This happens recursively, meaning **embedded notes can contain embedded notes inside of them**.

![](https://cdn.macstories.net/image-1632357233337.png)

From left to right: the table of contents, a chapter, and a section from Federico’s iOS review, which was compiled with this plugin.

The third option when exporting is 'Remove YAML ', which simply removes any [YAML front matter](https://help.obsidian.md/Advanced+topics/YAML+front+matter) from the document and any embedded documents when exporting. YAML is used to store metadata about your Obsidian notes but usually, it’s not something you want to export for publication.

The fourth and most niche option is 'Convert references using baseURL '.

This option can be used to export notes into a format that can be used to generate a paginated web post. A ‘baseURL’ must be specified in the YAML front matter of the document you are exporting, and a ‘page separator’ must be specified in the plugin’s settings. Once both of these are in place, the export plugin will automatically insert the page separator above each H2 (or other level specified in the plugin settings). These separators can be parsed by a blog post generating script to place each section on a new page.

The ‘baseURL’ allows [internal links](https://help.obsidian.md/How+to/Internal+link) to headings in the exported document to be replaced with paginated section links. For example, specifying `https://www.macstories.net/stories/ios-and-ipados-15-the-macstories-review` as 'baseURL ’ will replace all internal links with `https://www.macstories.net/stories/ios-and-ipados-15-the-macstories-review/pageNumber/#heading`, where `pageNumber` will be determined based on how many page separators are above the linked heading.

Apart from the main 'Export Markdown with Embeds ’ command, the plugin has two other commands to quickly export using common settings. The 'Share Markdown with Embeds ’ will flatten and export a note using both the 'increase heading levels ’ option and 'remove YAML ’ option, converting internal links to callback URLs. It will then present the flattened note in the native iOS share sheet. The second command, 'Share Markdown with Embeds using baseURL ', will do the same as the previous, however it will use the 'Convert references using baseURL ’ option described above.

This plugin allows you to split up a long project (such as Federico’s [iOS and iPadOS 15 review](https://www.macstories.net/stories/ios-and-ipados-15-the-macstories-review/)) into more manageable sections that can later be exported into a final single file.

## Download and Installation

This plugin is *not* available in the ‘Community Plugins’ section of Obsidian, which means you’ll have to **install it manually**.

To do this, you have to disable Safe Mode in Obsidian; then, use a Mac, PC, or Android device to manually install the plugin files. You can read more about [Safe Mode here](https://help.obsidian.md/Advanced+topics/Third-party+plugins).

To install the plugin, follow these steps:

-   Disable Safe Mode in Obsidian’s settings
-   Expand the plugin’s .zip archive
-   Using Finder, navigate to the hidden `.obsidian` folder located in your vault, then open the `plugins` folder
    -   To view hidden files and folder in the Finder, press this keyboard shortcut: ⇧⌘. (Shift-Command-Period)
-   Paste the plugin’s folder inside Obsidian’s `plugins` folder
-   Reload Obsidian and enable the Export Markdown with Embeds plugin under Community Plugins

***

I hope you’ll find Export Markdown with Embeds useful as much as I did when I was working on the [iOS and iPadOS 15 review](https://www.macstories.net/stories/ios-and-ipados-15-the-macstories-review/). As I will explain later this week in my ‘Making Of’ story, Export Markdown with Embeds was the plugin that allowed me to break this year’s iOS and iPadOS review into smaller, more manageable sections, and I’m happy that Club members will now be able to use it too.
***

==**5489**== Words

- **[Export Markdown with Embeds: An Obsidian Plugin to Compile Documents with Embedded Notes](https://club.macstories.net/posts/export-markdown-with-embeds)**