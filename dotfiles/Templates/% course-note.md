---
created: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>
modified: <% tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ss") %>
tags: [course]
<%*
  const title = tp.file.title
  const fulltitle = await tp.system.prompt("Full Title");
  const maxlec = await tp.system.prompt("Total number of lectures");
%>alias: [<%* tR += `"${fulltitle}"` %>]
title: "<%* tR += `${fulltitle}` %>"
---


# <%* tR += `${fulltitle}` %><%*
let path = tp.file.path(relative = true).replace(title+".md","")
path = path+ "Lectures"
if (path) {
    await this.app.vault.adapter.mkdir(path)
}
%>

- parent:: 
- instructor::

# Lectures
<%* if (maxlec) {tR += "`INPUT[slider(maxValue("+maxlec+")):lecture_create]`"} %>
```dataviewjs
const {createButton} = app.plugins.plugins["buttons"]

let h = dv.current().file.folder.toString();
h = h+"/Lectures"

var j = 	dv.pages()
	.where(k => k.file.folder == h)
	.sort(k => k.lecture, 'asc').lecture.last();

if (j) {
	j=j+1;
} else {
	j=1
}

if (dv.current().lecture_create){
j=Math.max(j,dv.current().lecture_create)
}

const r = ('0' + j.toString()).slice(-2);
const fname = h+"/"+dv.current().file.name+".L"+r

dv.paragraph(createButton({
	app, 
	el: this.container, 
	args: {
		name: "Next lecture: "+j, 
		type: "note("+fname+", split) template", 
		action: "% lecture-note", 
		color: "yellow",
	}
}))
```

<%* if (maxlec) {tR += "progress:: `$= let h= dv.pages('#lecture').filter(k =>  k.course.toString().includes(\"|"+title+"]]\")).sort(k => k.lecture, 'asc').lecture.last(); dv.paragraph(\"<progress style='height:15px;' value='\"+h+\"' max='"+maxlec+"'></progress> \"+h+\"/"+maxlec+"\")`"} %>

```dataview
table WITHOUT ID "[["+file.name+"|Lecture "+lecture+"]]" as lecture, date, elink(rec, "rec") as rec, topics
sort lecture
where course = this.file.link
```

# Course Outline

## Recommended Reading

# Coursework

## Assignments

## Exams
