---
aliases:
  - QuickAdd
date created: 2025-05-14
tags:
  - tutorial-obsidian
---

> [!question] How to set-up QuickAdd hotkey
> 1. Go to `Settings > Options > Hotkeys`
> 2. Search `quickadd`
> 3. Press the ➕ icon on the `QuickAdd: Run QuickAdd` option
> 4. Assign any hotkey you like (e.g. `CTRL+Q`)

## What is QuickAdd?

QuickAdd is a [[Community Plugins|community plugin]] which allows you to automate certain tasks inside an Obsidian vault. There are four types of automation tasks that QuickAdd provides, referred to as `choices`.

## QuickAdd Choices
### Template

Templates will create a new note with a specified template. 

> [!example] An example...
> We have a QuickAdd choice for a `Meeting` template
> 
> When this is selected, this choice will create a new meeting note for the current day (assuming one does not already exist).

### Capture

Captures allow you to quickly add content to a note without actually opening that note and writing anything down/clicking anything on the note.

> [!example] An example...
> We have an `Add Task to Backlog` capture choice. 
> 
> Selecting this choice opens a text box where you can name a new task. 
> 
> Upon clicking `ok`, this will automatically be added to the `Backlog` column in the `Task Progress Review` Kanban board - no need to open it and add the task manually!

### Macro

Macros allow you to execute any sequence of Obsidian commands and/or custom user scripts. 

This choice is both extremely powerful and difficult to use, most often requiring some knowledge of JavaScript.

### Multi

This choice simply functions as a folder to store other choices inside of, making it easier to organise and navigate the QuickAdd menu.

> [!example] An example...
> We have a multi choice called `📋 Create a New Note`.
> 
> This simply stores different categories of note templates to choose from in the QuickAdd menu.

## QuickAdd Documentation

https://quickadd.obsidian.guide/docs/