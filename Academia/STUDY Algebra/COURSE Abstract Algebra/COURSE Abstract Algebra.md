---
created: 2022-11-07T08:53:56
modified: 2022-11-07T08:54:04
tags:
  - course
aliases:
  - Abstract Algebra
title: Abstract Algebra
parent: "[[STUDY Algebra]]"
cssclasses:
  - cards
---


# Abstract Algebra

## Lecture notes

```dataviewjs
const {createButton} = app.plugins.plugins["buttons"]

let h = dv.current().file.folder.toString();
var i = 	dv.array(dv.pages("#lecture").where(k => k.file.folder == h).map(k => k.file.name))
var j=i.length

if (j) {
	j=j+1;
} else {
	j=1
}

const r = ('0' + j.toString()).slice(-2);
const fname = h+"/"+dv.current().file.name+".L"+r

dv.paragraph(createButton({
	app, 
	el: this.container, 
	args: {
		name: "New lecture note: "+j, 
		type: "note("+fname+") template", 
		action: "% lecture-note", 
		color: "yellow",
	}
}))
```

```dataviewjs

function gethead(filename, filepath){

var {path} = app.vault.getFileByPath(filepath)

if (app.metadataCache.getCache(path).headings)
	{return app.metadataCache.getCache(path).headings.map(b=> b.heading)}
else 
	{ return ""}
}

// dv.paragraph(gethead(dv.current().file.path))

const v = dv.pages()
	.where(b => b.file.folder == dv.current().file.folder && !b.file.name.contains("Drawing")
	&& !(b.file.name == dv.current().file.name)
	)
	.sort(b => b.file.tags)

dv.table(["Note", "tags", "topics"], v.map(b => [b.file.link, b.file.tags, gethead(b.file.name, b.file.path)]))
```
