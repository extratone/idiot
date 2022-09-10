```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api
const {createButton} = app.plugins.plugins["buttons"]
dv.table(["Image", "Title", "Note", "Link", ""], dv.pages('"Links"')
.where(p => p.status == 'new')
.sort(p => p.timestamp, 'desc')
.map(p=> ["![](" + p.cover + ")", p.title, "📝 " + p.file.link, "**[" + "🔗 " + p.domain + "](" + p.link + ")**", createButton({app, el: this.container, args: {name: "✅ Mark as Done"}, clickOverride: {click: update, params: ['status', 'done', p.file.path]}})])
)
```