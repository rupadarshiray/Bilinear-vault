---
created: 2022-11-07T08:53:56
modified: 2022-11-07T08:54:04
tags:
  - course
alias:
  - Abstract Algebra
title: Abstract Algebra
lecture_create: 0
---


# Abstract Algebra

[parent:: [[STUDY Algebra]]] [instructor::]

# Lectures

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

if (Math.max(j,dv.current().lecture_create)){
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
