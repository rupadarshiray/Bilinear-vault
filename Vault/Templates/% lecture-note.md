---
created: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>
modified: <% tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ss") %>
<%*
  let title = tp.file.title;
  var course = title.slice(0,-4);
  var lecture = title.slice(-2);
  lecture = Number(lecture);
%><%* app.commands.executeCommandById("markdown:toggle-preview") %> 
tags:
  - lecture
course: "[[<%* tR += `${course}` %>]]"
topics: []
---


# <% tp.file.cursor(1) %>
