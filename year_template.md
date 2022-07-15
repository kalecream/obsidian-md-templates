---
title: [[{{date:YYYY}} Review]]
status:
priority:
cssclass: cards
category: journal
aliases: 
tags: 
banner: "![[header.gif]]"
banner_icon: 🌲
---

# Year

 Year::[[{{date:YYYY}}]]
Month:: [[{{date:YYYY-MM}}]]
Days:: [[{{sunday:gggg-MM-DD}}]], [[{{monday:gggg-MM-DD}}]], [[{{tuesday:gggg-MM-DD}}]], [[{{wednesday:gggg-MM-DD}}]], [[{{thursday:gggg-MM-DD}}]], [[{{friday:gggg-MM-DD}}]], [[{{saturday:gggg-MM-DD}}]]

<center><img src="https://media0.giphy.com/media/h4fim7zVYskrDEqvil/giphy.gif?cid=790b7611f1b8496fe860656a7ff9ea4686d090f2f80a1b2b&rid=giphy.gif&ct=s"></center>

## Year in Review

*Arrive. Prepare your tools and the space around you. Close your eyes and take five deep breaths. Let go of your expectations. Start when you feel ready*

### The Past Year

#### Going Through Your Calendar

*Go through last year’s calendar week by week. If you see an important event, family gathering, friendly get-together or a significant project, write it down here.*

```dataview
TABLE event as "Event"

FROM #dailyjournal 

WHERE event

```

#### This is What My Last Year Was About

*We live our lives through distinct but interconnected aspects. Take a look at the areas below and ask yourself what the significant events in each of them were. Write down your answers.*

##### Personal Life

##### Career, Studies

##### Friends, Community

##### Relaxation, Hobbies, Creativity

##### Physical Health, Fitness

```dataviewjs
const calendarData = { 
	entries: [], // Populated in the DataviewJS loop below
	year: 2022,  // (optional) Defaults to current year
	colors: {    // (optional) Defaults to green
	  blue:        ["#8cb9ff","#69a3ff","#428bff","#1872ff","#0058e2"], // first entry is considered default if supplied
	  green:       ["#c6e48b","#7bc96f","#49af5d","#2e8840","#196127"],
	  red:         ["#ff9e82","#ff7b55","#ff4d1a","#e73400","#bd2a00"],
	  orange:      ["#ffa244","#fd7f00","#dd6f00","#bf6000","#9b4e00"],
	  pink:        ["#ff96cb","#ff70b8","#ff3a9d","#ee0077","#c30062"],
	  orangeToRed: ["#ffdf04","#ffbe04","#ff9a03","#ff6d02","#ff2c01"]
	},
	showCurrentDayBorder: true // (optional) Defaults to true
}

//DataviewJS loop
for(let page of dv.pages('"#dailyjournal"').where(p=>p.sunsalutation).sort(p=>p.file.name)){ 

	calendarData.entries.push({
		date: page.file.name, // (required) Format YYYY-MM-DD
		intensity: page.exercise, // (required) Color intensity for entry, will map intensities automatically
		content: "🏋️", // (optional) Add text to the date cell
		color: "orange", // (optional) Reference from *calendarData.colors*. If no color is supplied; colors[0] is used
	})

}

/**
* param1  HTMLElement   DOM reference for calendar rendering
* param2  CalendarData  Calendar data object from above
*/
renderHeatmapCalendar(this.container, calendarData)
```

##### Mental Health, Self-knowledge

```tracker
searchType: dvField
searchTarget: mood
folder: /
startDate: 2022-01-01
endDate: 2022-12-31
textValueMap:
    😀: 5
    🙂: 4
    😐: 3
    🙁: 2
    😞: 1
line:
    title: "Mood"
    lineColor: red
    pointColor: black
    pointSize: 2
    yAxisLabel: Mood
    yAxisTickInterval: 1
    yAxisTickLabelFormat: i
    yMin: 0
    yMax: 10
    lineWidth: 2.5
    fillGap: true
```
##### Finance

``` tracker
searchType: dvField
searchTarget: money
folder: /
startDate: 2022-01-01
endDate: 2022-12-31
accum: true
line:
    title: ""
    xAxisLabel: Date
    yAxisLabel: JMD
    fillGap: true
```

##### Habits That Define You

##### A Better tomorrow*

*What did you do this year to leave the world in a better shape than you found it?*

### Six Sentences About My Past Year

#### The Wisest Decision I made…

#### The Biggest Lesson I learned…

#### The Biggest Risk I took…

#### The Biggest Surprise of the year…

#### The Most Important Thing I Did for others…

#### The Biggest Thing I completed…

#### What Are You Most Proud Of?

#### Who Are the Three People Who Influenced You the Most?

#### Who Are the Three People Who Influenced You the Most?

#### What Were You Not Able to Accomplish?

#### What Are You Most Grateful For?

### The Best Moments

*Describe the greatest and most memorable, joyful moments from last year. Draw them on this sheet. How did you feel? Who was there with you? What were you doing? What kind of smells, sounds or tastes do you remember?*

### Three of My Biggest Accomplishments

#### List Your Three Greatest Accomplishments From Last Year Here.

#### What Did You Do to Achieve These?

#### Who Helped You Achieve These Successes? How?

### Three of My Biggest Challenges

#### List Your Three Biggest Challenges From Last Year Here

#### Who or What Helped You Overcome These Challenges?

#### What Have You Learned About Yourself by Overcoming These Challenges?

### Forgiveness

*Did anything happen during the past year that still needs to be forgiven? Deeds or words that made you feel bad? Or are you angry with yourself? Write it down here. Do yourself good by forgiving.*
* If you don’t feel ready to forgive yet, jot it down anyway. It can work wonders

### Letting Go

*Is there anything else you need to say? Is there anything you have to let go of before you can start your next year? Draw or write, then think about it and let it all go.*

### The Past Year in Three Words

*Choose three words to define your past year*

### The Book of My Past Year

*A book or a movie was made about your past year. What title would you give it?*

```dataview
TABLE WITHOUT ID cover, file.link
FROM #book 
WHERE cover != null and file.name != "Book Template"
sort rating desc
LIMIT 4
```
```dataview
TABLE WITHOUT ID cover, file.link
FROM #movie
WHERE cover != null
sort rating desc
LIMIT 4
```

### Goodbye to Your Last Year

*If there is anything else left that you would like to write down, or there is anybody you would like to say goodbye to, do it now.*

<center>
You’re done with the past year.

You have just finished the first part. Take a deep breath.

Get some rest.

</center>

## The Year Ahead

### Dare to Dream Big

What does the year ahead of you look like? Why will it be great? What would happen in an ideal world? Write, draw, let go of your expectations and dare to dream.

### This is What My Next Year Will Be About

Take a look at the areas of your life and decide your goals for each of them for the next year. Put those goals on the page—this is the first step towards realizing them.

#### Personal Life

#### Career, Studies

#### Friends, Community

#### Relaxation, Hobbies, Creativity

#### Physical Health, Fitness

#### Mental Health, Self-knowledge

#### Habits That Define You

#### A Better tomorrow*

*What did you do this year to leave the world in a better shape than you found it?*

## Magical Triplets for the Year Ahead

### I Will Love These Three Things About Myself.

### I Am Ready to Let Go of These Three Things

### I Want to Achieve These Three Things the Most

### These Three People Will Be My Pillars During Rough Times.

### I Will Dare to Discover These Three Things.

### I Will Have the Power to Say No to These Three Things.

### I Will Make My Surroundings Cozy with These Three Things.

### I Will Do These Three Things Every Morning.

### I Will Pamper Myself with These Three Things Regularly

### I Will Visit These Three Places

### I Will Visit These Three Places

### I Will Connect with My Loved Ones in These Three Ways.

### I Will Reward My Successes with These Three Presents

## Six Sentences About My Next Year

### This Year I Will Not Procrastinate Any More over..

### This Year I Will Draw the Most Energy from…

### This Year, I Will Be Bravest when…

### This Year I Will Say Yes when…

### This Year I Advise Myself to…

### This Year Will Be Special for Me because…

## My Word for the Year Ahead

Pick a word to symbolise and define the year ahead. You can look at this word if you need some extra energy, so you remember not to give up your dreams.

## Secret Wish

Unleash your mind. What is your secret wish for the next year?


# Emotional

- [ ] Develop a Personal Brand
- [ ] Handle negative emotions maturely

# Financial

- [ ] Make an emergency fund of US$1,500. US$ 3,500 would be ideal.1,500$ for real emergencies only! 1,500$ saved in 1 year is 30$ a week. 60$ a week for 6 months. 107$ a week for 14 weeks.
- [ ] Have 100,000 in my investment portfolio.
- [ ] Get a Credit Card
- [x] Move out

# **Intellectual**

- [ ] Complete WebDev Track
- [ ] Smart Contract Certification
- [ ] AWS Certification
- [ ] Read 12 Books

**Occupational**

- [x] 2x Income [ 250000 ]

**Physical**

- [ ] Health Insurance
- [ ] Life Insurance
- [ ] Run a 5K
- [ ] Learn proper food group & have meals accordingly
- [ ] Plank for 1 minute

# Recreational

- [ ] Cook every meal in a cookbook
- [ ] Belize or Cuba vacation

# Spiritual

- Breathe properly
- 8-Fold Path
- Meditate uninterrupted for 15 minutes
