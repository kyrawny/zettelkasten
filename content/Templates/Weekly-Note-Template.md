---
title:
  ? title: ~
  : ~
aliases:
  - "{{title}}"
tags:
  - "#weekly-note"
  - "#planner"
---

*{{date:YYYYMM}}* | {{title}}

# {{title}}

## *{{monday:GGGGMMDD}}*

* 

## *{{tuesday:GGGGMMDD}}*

* 

## *{{wednesday:GGGGMMDD}}*

* 

## *{{thursday:GGGGMMDD}}*

* 

## *{{friday:GGGGMMDD}}*

* 

## *{{saturday:GGGGMMDD}}*

* 

## *{{sunday:GGGGMMDD}}*

* 

## Habits ✓

* [ ] Weekly Habits::
  * [ ] Laundry
  * [ ] Vacuum
  * [ ] Mop

## Habit Tracker

````dataview
TABLE Sleep, Food, Dental, Water, Paper, Chess
FROM "4 Planner/0 Daily Notes"
WHERE contains(this.file.outlinks, file.link)
SORT file.day
````
