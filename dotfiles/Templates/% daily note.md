---
created: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>
modified: <% tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ss") %>
alias: ["<% tp.date.now("DMMMYY") %>"]
tags: [dailynotes]
---

# <% tp.date.now("dddd") %>, <% tp.date.now("D MMMM") %> <% tp.date.now("YYYY") %>

<% tp.file.cursor() %>