---
tags: []
alias: [Bilinear notes]
cssclass: [WikiCardView, cards, cards-cover]
banner_icon: 📘
---

# Bilinear notes

> [!tip] 
> This is a wiki, or "evergreen notes", or simply *long-term notes*.

---
## *latest pages*
```dataviewjs
dv.table(["Node","Created"], dv.pages('"00 Bilinear notes"')
	.where(b => b.id)
    .sort(b => b.file.mtime, 'desc')
	.limit(21)
    .map(b => [
    	"#### [["+b.file.name+"|"+b.title+"]]",
	"- **"+b.file.folder.replace("00 Bilinear notes/","")+"**: "+b.file.link+
	"\n- **created**: "+moment(b.created).format("D MMM yyyy hh:ss a") 
	//+"<li>Last modified: "+moment(b.updated).format("D MMM yyyy hh:ss a")
	//+"<li>Size: "+b.file.size+"<li>ID: "+b.id
	//+"<li>"+b.desc
			]))
```