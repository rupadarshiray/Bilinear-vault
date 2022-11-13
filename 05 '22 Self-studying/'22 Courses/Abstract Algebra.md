---
created: 2022-11-07T08:53:56
modified: 2022-11-07T08:53:56
tags: [course]
alias: ["Abstract Algebra"]
title: "Abstract Algebra"
---


# Abstract Algebra

- parent:: 
- instructor::

# Lectures
`INPUT[slider(maxValue(5)):lecture_create]`
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

progress:: `$= let h= dv.pages('#lecture').filter(k =>  k.course.toString().includes("|Abstract Algebra]]")).sort(k => k.lecture, 'asc').lecture.last(); dv.paragraph("<progress style='height:15px;' value='"+h+"' max='5'></progress> "+h+"/5")`

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
