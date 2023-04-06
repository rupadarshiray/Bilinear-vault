---
created: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>
modified: <% tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ss") %>
<%*
	let title = tp.file.title;
    const name = await tp.system.prompt("Problem Name");
	if (name) {
	title = "PROBLEM "+tp.file.creation_date("YYYY-MM-DD-")+name
	} else {
	title = "PROBLEM "+tp.file.creation_date("YYYY-MM-DD-HHmmss")
	}
	await tp.file.rename(title);
	const sbjo = ["math", "physics", "chemistry",  "biology", "cs", "programming", "astronomy", "earth-sci"];
	const subject = await tp.system.suggester(sbjo, sbjo)
%>tags: [problem, <%* tR += `${subject}` %>]
title: <%* tR += `${name}` %>
alias: [<%* tR += `${name}` %>]
---
# <%* tR += `${name}` %>
[resolved:: ]
<% tp.file.cursor() %>