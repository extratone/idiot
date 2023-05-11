---
share: true
dg-publish: true
telegraph_page_url: https://telegra.ph/Todoist-Tasks-An-Obsidian-Plugin-to-Create-Tasks-in-Todoist-with-Two-Way-Linking---Finn-09-08
telegraph_page_path: Todoist-Tasks-An-Obsidian-Plugin-to-Create-Tasks-in-Todoist-with-Two-Way-Linking---Finn-09-08
---
# "Todoist Tasks: An Obsidian Plugin to Create Tasks in Todoist with Two-Way Linking"

*26-04-2022 07:41* 

> September 20, 2021
[September 20, 2021](https://club.macstories.net/posts/todoist-tasks-an-obsidian-plugin-to-create-tasks-in-todoist-with-two-way-linking)

![](https://cdn.macstories.net/1bf466fc-e21d-458e-bdd7-27e7d7dbac1c-1632062515792.png)

The Todoist Tasks plugin in Obsidian.

Todoist Tasks is a plugin for [Obsidian](https://obsidian.md/) that enables you to create tasks in [Todoist](https://todoist.com/) directly from Obsidian. As you take notes or write in Obsidian, you can create inline tasks using syntax describing the project, label, section, due date, priority, and any notes associated with a task.

Running the ‘**Create and update tasks in current file**’ command in Obsidian will find new tasks in the current note, create the task in Todoist using the [Todoist API](https://developer.todoist.com/guides/#developing-with-todoist), and add a link to the task in Obsidian using the Todoist URL scheme.

Tasks can then be marked as completed in Obsidian *or* Todoist, and they will be marked as completed in the other when running the command next.

## The Syntax

The syntax for defining tasks in Obsidian is loosely based on the [Todoist Quick Add syntax](https://todoist.com/help/articles/task-quick-add).

Tasks are created by adding a Markdown task using the `- [ ]` syntax. The task title is used in Todoist, and any metadata must follow the title. Each task must have a Todoist project specified, which can be added using a `#` followed by the project name. For example:

`- [ ] Example Task Title #My Project`

Tasks can also have optional labels, sections, due date, priority, and notes. A task can have any number of labels, which are created using `@` followed by the label name. Sections are groups which can be added to a project in Todoist, and are created using `+` followed by the section name. A due date can be added to a task using `/` followed by a due date string.

Due dates are described in natural language (find out more [here](https://todoist.com/help/articles/due-dates-and-times#some-example-date-formats-you-can-use)). A task priority can be added using `!` followed by a priority, ranging from `p1` to `p4`. Lastly, notes can be added to a task by including text inside parentheses, which will be added to the description field in Todoist.

![](https://cdn.macstories.net/d4869dd3-5b9a-461b-b304-7b7356e33979-1632145685673.png)

Creating tasks from Obsidian using Todoist Tasks.

Here is an example of a task created in Obsidian using all of this syntax:

`- [ ] Example Task #myproject @mylabel1 @mylabel2 +mysection /tomorrow at 3pm !p2 (do this soon!)`

While a **task title and project are required**, all other syntax is optional and can appear in any order. After running the ‘Create and update tasks in current file’ command, the task will be updated to include a link to the newly created task in Todoist as well as an [Obsidian block ID](https://help.obsidian.md/How+to/Link+to+blocks). This allows the task in Todoist to contain a link back to the Obsidian task.

## YAML Front Matter Integration

Task metadata can also be specified in a note’s [YAML front matter](https://help.obsidian.md/Advanced+topics/YAML+front+matter). This metadata will be applied to all tasks in a note, so you don’t need to specify the same metadata each time.

Example:

```
---
project: myproject
label: mylabel1, mylabel2
section: mysection
dueDate: tomorrow at 3pm
priority: p2
notes: (do this soon!)
---
```

![](https://cdn.macstories.net/21b56f35-d757-488a-9e3f-d325c2c71090-1632145899596.png)

You can use YAML front matter to define global task attributes for the current note.

While the syntax takes some getting used to, it enables task creation without leaving the context of your writing. The Todoist Tasks plugin is perfect for creating tasks alongside your research, outlining, and writing without having to ever leave Obsidian.

## Download and Installation

This plugin is *not* available in the ‘Community Plugins’ section of Obsidian, which means you’ll have to **install it manually**.

To do this, you have to disable Safe Mode in Obsidian; then, use a Mac, PC, or Android device to manually install the plugin files. You can read more about [Safe Mode here](https://help.obsidian.md/Advanced+topics/Third-party+plugins).

To install the plugin, follow these steps:

-   Disable Safe Mode in Obsidian’s settings
-   Expand the plugin’s .zip archive
-   Using Finder, navigate to the hidden `.obsidian` folder located in your vault, then open the `plugins` folder
    -   To view hidden files and folder in the Finder, press this keyboard shortcut: ⇧⌘. (Shift-Command-Period)
-   Paste the plugin’s folder inside Obsidian’s `plugins` folder
-   Reload Obsidian and enable the Todoist Tasks plugin under Community Plugins
-   When prompted, paste your private Todoist API token in the plugin’s preferences, which you can get [here](https://todoist.com/prefs/integrations).

The Todoist Tasks plugin does not collect any data. The plugin communicates exclusively with the Todoist API and stores your API token locally inside Obsidian’s ‘plugins’ folder.

***

I hope you’ll find Todoist Tasks useful as much as I did when I was working on the [iOS and iPadOS 15 review](https://www.macstories.net/stories/ios-and-ipados-15-the-macstories-review/). As I will explain later this week in my ‘Making Of’ story, Todoist Tasks was essential to keep track of various tasks throughout the story while retaining the ability to view them in-place inside Obsidian. This plugin enables the kind of deep integration between task manager and text editor I’ve always wanted, and I’m happy that Club members will now be able to use it too.
***

==**4612**== Words

- **[Todoist Tasks: An Obsidian Plugin to Create Tasks in Todoist with Two-Way Linking](https://club.macstories.net/posts/todoist-tasks-an-obsidian-plugin-to-create-tasks-in-todoist-with-two-way-linking)**