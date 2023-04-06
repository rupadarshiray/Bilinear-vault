---
created: 2023-04-06T19:08:00
modified: 2023-04-06T19:08:00
tags: []
alias: []
BC-folder-note: down
BC-tag-note:: #problem 
---

# Problems

```dataviewjs
const {createButton} = app.plugins.plugins["buttons"]
let h = dv.current().file.folder.toString();

dv.paragraph(createButton({
	app, 
	el: this.container, 
	args: {
		name: "New problem", 
		type: "note("+h+"/Untitled, split) template", 
		action: "% problem",
		id: "blue"
	}
}))
```

```dataview
table WITHOUT ID "**"+striptime(created)+"**" as "date created","[["+file.name+"|"+title+"]] "+file.tags as title, resolved
from (#problem  OR #Problem)
sort created DESC
where dur(date(  2021-10-01) - created).minutes < 0

```