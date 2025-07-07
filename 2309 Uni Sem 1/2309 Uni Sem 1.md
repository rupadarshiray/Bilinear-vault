---
created: 2022-09-25T14:04:56
modified: 2022-09-25T14:04:56
tags:
aliases: []
cssclasses:
  - cards
  - cards-cover
parent: "[[23 Uni]]"
---

# [[23 Uni|University]] Semester 1

```dataviewjs

var a = moment("2026-01-06");
var b = moment("2026-05-07");

var n = moment()
var t = moment().startOf('day');

let q =  b.diff(a, 'days')+1;
let p =  b.diff(t, 'days');
let r =  t.diff(a, 'days');

let h = n.diff(a, 'hours');
let i = b.diff(a, 'hours');

let html = `<progress style="height:15px;width:90%" value="`+h+`" max="`+i+`"></progress>`

if (r>0 && r<q) {
html += `\n#### `+p+` days left in semester of `+q+` days\n`
html += (h/i*100).toFixed(2)+`% complete`
} else if (r==0) {
html += `\nstars today`
} else if (r==q) {
html += `\nends today`
} else if (r>q) {
html += `\nended `+-p+` days ago`
}else {
html += `\n#### `+-r+` days to go`+`\nFYI: It is a `+q+`-days semester.`
}

dv.paragraph(html)
```

## courses
```dataview
table WITHOUT ID "### [["+file.name+"|"+title+"]]" as course, instructor
where semester = this.file.link
sort created
```