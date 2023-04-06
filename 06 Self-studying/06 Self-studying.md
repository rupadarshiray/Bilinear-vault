---
tags: []
alias: []
---

# Self-studying

> [!abstract]- `$= dv.table([""], dv.pages('#study and "06 Self-studying"').sort(b => b.file.ctime).map(b => [b.file.link+" "+b.desc]))`
> ```dataviewjs
> function checkparent(pt,ff) {  
> if (Array.isArray( pt ))  {   for (let k = 0; k < pt.length; k++){  if (pt[k]== (ff.toString())){return true; break}; } }
> else { return pt == ff.toString(); }
> } 
>  let studypages = dv.pages('#study and "06 Self-studying"').sort(b => b.file.ctime)
>  for (let step = 0; step < studypages.length; step++)
>  {
>      var ff = studypages[step].file.link;
>      var listn = [];
>  	dv.paragraph("#### "+ff+": "+studypages[step].desc);
>  
>    var pdown = dv.pages('"06 Self-studying"').filter(p => checkparent(p.parent,ff));
>    for (let j = 0; j < pdown.length; j++){
>       if(pdown[j]){
>       var filen = pdown[j].file.link
>       if (pdown[j].progress){filen+="  "+pdown[j].progress}
>       if(pdown[j].banner_icon){filen = pdown[j].banner_icon + filen}
>       listn.push(filen);
>       }};
>       dv.list(listn)
>  }
> ```