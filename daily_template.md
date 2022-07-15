---
title:
aliases: 
status:
priority:
rating:
next_step:
cssclass: daily
tags: [dailyjournal,periodic/daily]
category: journal
react-components-namespace: projects.test
banner: "![[anime-flower.gif]]"
banner_y: 0.2
banner_icon: 
banner_x: 0
---

```jsx:
<Clock />
```

…

[[<% tp.date.yesterday("YYYY-MM-DD") %>|↶ Previous Day]]  |  [[{{date:YYYY}}-W{{date:ww}}]]  | [[<% tp.date.tomorrow("YYYY-MM-DD") %>|Following Day ↷]]

%%Year::[[{{date:YYYY}}]].  

Quarter:: [[{{date:YYYY}}-Q{{date:Q}}]].  

Month:: [[{{date:YYYY-MM}}]].%%  

%%Week:: [[{{date:YYYY}}-W{{date:ww}}]]%%

…

*I am grateful for the abundance in my life.*

```dataviewjs
// List of messages
let messages = [];

// Extract messages from pages that have them
dv.pages("#gratitude")
	.where(page => page.message)
	.forEach(page => {
		dv.array(page.message).forEach(message => {
			messages.push(message); })});

let greeting = messages[Math.floor(Math.random()*messages.length)]

dv.paragraph("*I am grateful for "+greeting+"*");
```

…

# Productivity

*I will focus as much as I can daily on my goals to complete my professional and personal tasks.*

All Poms | `$=dv.pages("#dailyjournal").pomoduro.array().reduce((a,b)=>a+b)`,  

Today's Poms | `$=dv.current().pomoduro`

![[{{date:YYYY-MM}}#Goal]]

- [ ] Check calendar for today and tomorrow.
- [ ] Clear email for
	- [ ] today
	- [ ] 1 other day

## Habits

- [ ] Green tea
- [ ] Sun salutation
- [ ] 16 pomoduro for work
- [ ] 4 pomoduros for studying
- [ ] 2 pomoduro obsidian
- [ ] Youtube -> Script writing, research, filming, editing, thumbnails, vlogging.

## Cleaning

### Kitchen

- [ ] Wipe up spills in the fridge
- [ ] Throw out old food
- [ ] Clean outside of appliances
- [ ] Scrub and shine sink
- [ ] Shake or vaccum rugs
- [ ] Mop

### Bathroom

- [ ] Mop
- [ ] Clean sink
- [ ] Wipe doorknobs
- [ ] Clean outside of toliet
- [ ] Empty trash
- [ ] Shake or vacuum rug

### Bedroom

- [ ] Change sheets
- [ ] Dust
- [ ] Vaccuum

### Living Room

- [ ] Dust
- [ ] Vacuum
- [ ] Straighten books

### ETC

- [ ] File loose papers
- [ ] Organise a draw
- [ ] wipe washer
- [ ] Clean laundry sink
- [ ] Remove lint from washing machine
- [ ] Wash bedding and towels
- [ ] Sweep entry and stairs

# Body

*I will try to get adequate amounts of sleep.*

- sleepHours::  
- sleepComments::  
- dreamJournal::  

- water::  
- exercise::
- food::
- sick::
- energy::
- mood::

- win::
- loss::
- stressors:
- memories::
- feeling::

# Recreation

# Read

*I have several things to read in my inbox.

- book_log::
- book_recommendation::  
- media::

- [ ] Clear 1 bookmark
	- [ ] Twitter
	- [ ] Tumblr
	- [ ] Reddit
	- [ ] Bookmark

	 ```dataview
	 TABLE file.cday, tags
	 from [[ReadItLater]] or [[55 ReadItLater]]
	 sort file.ctime asc
	 LIMIT 5
	 ```
# Knowledge

- learnt::

```dataview
TABLE tags
from #course
```

# Finance

*I must keep aware of my finances to keep my accounts safe and to prevent overspending.*

``` tracker
searchType: dvField
searchTarget: money
folder: /
startDate: 2022-07-01
endDate: 2022-07-31
accum: true
line:
    title: ""
    xAxisLabel: Date
    yAxisLabel: JMD
    fillGap: true
```

- money::
- money-memo::

# Occupation

# Log

- 

# Unclosed Days

```dataview
 TABLE
 	"<progress value='" + (length(filter(file.tasks.completed, (t) => t = true)) / length(file.tasks.text)) * 100 + "' max='100'></progress> (" + length(filter(file.tasks.completed, (t) => t = true)) + "/" + length(file.tasks.text) + ") " + round((length(filter(file.tasks.completed, (t) => t = true)) / length(file.tasks.text))* 100,2)  + "%"   AS Progress
 	
 FROM #dailyjournal or #journal
 WHERE round((length(filter(file.tasks.completed, (t) => t = true)) / length(file.tasks.text))* 100,2) < 100
 SORT round((length(filter(file.tasks.completed, (t) => t = true)) / length(file.tasks.text))* 100,2) desc
 LIMIT 14
 ```

# Todoist | Today or Overdue

```todoist
{
 "name": "",
 "filter": "(today | overdue)",
 "sorting": ["priority"],
 "group": true
}
```

# Project

*I will see my projects through and reward myself justly according to my accomplishments.*

```dataview
TABLE
 	due_date as "Deadline",
	"<progress value='" + (length(filter(file.tasks.completed, (t) => t = true)) / length(file.tasks.text)) * 100 + "' max='100'></progress> (" + length(filter(file.tasks.completed, (t) => t = true)) + "/" + length(file.tasks.text) + ") " + round((length(filter(file.tasks.completed, (t) => t = true)) / length(file.tasks.text))* 100,2)  + "%"   AS Progress
 	
FROM #project/active

WHERE file.name != "Project Template" AND file.tasks
```
