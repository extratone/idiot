```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api
const {createButton} = app.plugins.plugins["buttons"]
dv.table(["Image", "Name", "Length", "Saved", "Link", ""], dv.pages('"YouTube"')
.where(p => p.status == 'New')
.sort(p => dv.date(p.saved), 'desc')
.map(p=> [p.thumb, "📝 " + p.file.link, p.duration, p.saved, "" + "[" + "🔗 " + p.channel + "](" + p.URL + ")", createButton({app, el: this.container, args: {name: "📺 Watched"}, clickOverride: {click: update, params: ['status', 'Watched', p.file.path]}})])
)
```