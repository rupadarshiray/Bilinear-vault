---
created: 2023-04-06T19:03:19
modified: 2023-04-06T19:03:19
tags: []
alias: []
---

# Library

*add your files here and see the magic!*

```dataviewjs

const currf = dv.current()
const currout = currf.file.outlinks

const nonMdFiles = app.vault.getFiles().filter(file =>  file.path.includes(currf.file.name) && file.extension != 'md');

const totfiles = nonMdFiles.map(file => dv.fileLink(file.path))

var newf = totfiles.filter(b => !currout.includes(b));
if (newf.length > 0) {dv.paragraph("## New arrivals")
dv.list(newf)}

```