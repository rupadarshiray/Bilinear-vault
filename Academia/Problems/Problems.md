---
created: 2025-07-07T18:17:13
modified: 2025-07-07T18:17:13
tags: []
alias: []
---

# Problems


```dataviewjs
const {createButton} = app.plugins.plugins["buttons"]
const fname = dv.current().file.folder+"/Untitled"

dv.paragraph("[["+fname+"|Create a new problem]]")
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
