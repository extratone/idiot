```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api
const {createButton} = app.plugins.plugins["buttons"]
dv.table(["Image", "Title", "Note", "Link", "Saved On", "Saved From", "Word Count", ""], dv.pages('"Read Later"')
.where(p => p.status == 'unread')
.sort(p => p.readable_timestamp, 'desc')
.map(p=> ["![](" + p.cover + ")", p.title, "📝 " + p.file.link, "**[" + "🔗 " + p.domain + "](" + p.link + ")**", p.readable_timestamp, "Saved from: " + p.platform_saved, "Words: " + p.word_count, createButton({app, el: this.container, args: {name: "✅ Mark as Read"}, clickOverride: {click: update, params: ['status', 'archived', p.file.path]}})])
)
```