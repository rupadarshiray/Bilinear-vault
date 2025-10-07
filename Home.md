

```dataviewjs
const currentHour = moment().format('HH');
console.log(currentHour)
let greeting;
if (currentHour >= 18 || currentHour < 5) {
 greeting = '🌙Good evening'
} else if (currentHour >= 5 && currentHour < 12) {
greeting = '🌞Good morning'
} else {
greeting = '🌞Good afternoon'
}
  
dv.header(1, greeting)
```

> [!info] 
> ```dataviewjs
> let ftMd = dv.pages("").file.sort(t => t.cday)[0]
> let total = parseInt([new Date() - ftMd.ctime] / (60*60*24*1000))
> let totalDays = "You have been using *Obsidian* for "+total+" days,"
> let nofold = '!"misc/templates"'
> let allFile = dv.pages(nofold).file
> let totalMd = " with "+
> 	allFile.length+" notes, "
> let totalTag = allFile.etags.distinct().length+" tags, "
> let totalTask = allFile.tasks.length+" tasks created. "
> dv.paragraph(
> 	totalDays+totalMd+""+""+totalTag+""+totalTask
> )
> 
> ```

```dataviewjs

const today = DateTime.now()
const endOfYear = {
    year: today.year,
    month: 12,
    day: 31
}

const lifespan = { year: 99 } 
const birthday = DateTime.fromObject({
    year: 2003,
    month: 4,
    day: 26
});
const deathday = birthday.plus(lifespan)

function progress(type) {
    let value;
    
    switch(type) {
        case "lifespan": 
            value = (today.year - birthday.year) / lifespan.year * 100;
            break;
        case "year":
            value = today.month / 12 * 100
            break;
        case "month":
            value = today.day / today.daysInMonth * 100
            break;
        case "day":
            value = today.hour / 24 * 100
            break;
    }
    return `<progress value="${parseInt(value)}" max="100" style="height:10px;width:60%"></progress>   ${parseInt(value)}%`
}


dv.span(`
**Life**  ${progress("lifespan")}
**Year** ${progress("year")}
**Month** ${progress("month")}
**Day** ${progress("day")}
`)


```


Some todos:

- [ ] Look at [this tutorial video](https://youtu.be/XZDpq-3ozBI) and try to repeat the same, maybe?
- [ ] Check [[Guide to markdown and beyond]] and pretty much every other note in this vault. There is a list here [[List of files]]
- [ ] Update the community plugins.

Always refer to:

![[readme#More resources]]