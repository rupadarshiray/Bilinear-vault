---
created: 2022-09-25T14:04:51
modified: 2022-09-25T14:04:51
tags: []
aliases:
  - University
---

# University


## university life progress bar

```dataviewjs
var a = moment("2022-01-03");
var b = moment("2026-06-14");

var n = moment()

let h = n.diff(a, 'hours');
let i = b.diff(a, 'hours');

dv.span(`
<progress value="`+h+`" style="height:10px;width:80%" max="`+i+`"></progress> `+(h*100/i)+`%
`)
```