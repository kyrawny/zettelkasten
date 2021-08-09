---
title: Personal Home
aliases:
  - Home
tags:
  - context-note
---

# Welcome to Kyra's second brain.

* [Home](Home.md)
  * [Chess](0Context/Chess.md)

## Planner

````dataview
TASK
FROM "4 Planner"
WHERE file.day = date(today) OR file.name = date(today).year + "W" + date(today).weekyear
````

## To Process

### [Fleeting Notes](Fleeting-Notes.md)

### Projects

````dataview
TASK
FROM #project-note
WHERE !contains(file.name, "Template") and !contains(tags, "#done")
SORT file.mtime DESC
````

### Literature Notes

````dataview
TASK
FROM #literature-note
WHERE !contains(file.name, "Template") and !contains(tags, "#done")
SORT file.mtime DESC
SORT type ASC
````

## Permanent Notes

````dataview
LIST
FROM #permanent-note
WHERE !contains(file.name, "Template")
SORT file.ctime DESC
````
