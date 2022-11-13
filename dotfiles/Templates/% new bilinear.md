<%*
	function createBlockHash() {
	    let result = '';
	    var characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
	    var charactersLength = characters.length;
	    for ( var i = 0; i < 22; i++ ) {
	        result += characters.charAt(Math.floor(Math.random() * charactersLength));
	    }
	    return result;
	}
  let name = tp.file.title
  if (name.startsWith("Untitled")) {
    name = await tp.system.prompt("File name");
	if (name) {
	name = name
	} else {
	name = tp.file.creation_date("YYYYMMDDHHmmss")
	}
    await tp.file.rename(name);
  }
	    title = await tp.system.prompt("Title");
	if (title) {
	title = title
	} else {
	title = name
	}
%>---
id: <%* tR += createBlockHash() %>
title: "<%* tR += `${title}` %>"
desc: ''
created: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>
modified: <% tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ss") %>
alias: ["<%* tR += `${title}` %>"]
tags: []
---

# <%* tR += `${title}` %>
<% tp.file.cursor() %>