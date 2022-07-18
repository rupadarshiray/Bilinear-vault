---
created: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>
modified: <% tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ss") %>
tags: []
alias: []
---
<%*
  let title = tp.file.title
  if (title.startsWith("Untitled")) {
    title = await tp.system.prompt("Title");
	if (title) {
	title = title
	} else {
	title = tp.file.creation_date("YYYYMMDDHHmmss")
	}
    await tp.file.rename(title);
  } 
%>
# <%* tR += `${title}` %>
<% tp.file.cursor() %>