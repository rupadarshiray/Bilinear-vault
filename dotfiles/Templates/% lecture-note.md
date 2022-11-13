---
created: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>
modified: <% tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ss") %>
tags: [lecture]
topics:
 - <% tp.file.cursor(2) %>
---
<%*
  let title = tp.file.title;
  var course = title.slice(0,-4);
  var lecture = title.slice(-2);
  lecture = Number(lecture);
%><%* app.commands.executeCommandById("markdown:toggle-preview") %> 
> [!info]- ###### <%* tR += `${course}` %> <br> Lecture <%* tR += `${lecture}` %>
> - course:: [[<%* tR += `${course}` %>]]
> - [date:: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>]
> - [lecture:: <%* tR += `${lecture}]` %><%* if (lecture > 1) {tR += `\n> - prev:: [[${course}.L${('0' + (lecture-1).toString()).slice(-2)}]]`} %>
> - rec:: 
> - CourseNotes:: 

# <% tp.file.cursor(1) %>
