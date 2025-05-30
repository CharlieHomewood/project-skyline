---
date created: 2025-05-19
tags:
  - tutorial-obsidian
---

## Internal Links

Internal links are a way to create hyperlink between notes inside an Obsidian vault.

To create a link, use: \[\[]]
 - This will automatically open a dropdown menu where you can select or type the name of the note you wish to link to

You can customise the text of a link by using the `|` separator. 
 - The syntax would be: `[[Note name|Display text]]` which would result in a link which just appears as \[\[Display text]] but actually links to the note called `My note name`

 > [!example]
 >  - Let's say we have a note called `Double jump mechanic` and you wanted to refer to that note when talking about a level design
 >  - You might write: 
 > 	 - "We give players access to a mid-air boost early to support vertical exploration".
 > 	 - The "mid-air boost" is the `Double jump mechanic`
 > 	 - So you could link to `Double jump mechanic` by writing: \[\[Double jump mechanic|mid-air boost]]

These links are more specifically called **outgoing links**, as they link **outwards** to another note. If a note is linked to by some other note, it will have an implicit **backlink**. 

 > [!tip]
 > You can access a note's outgoing and backward links in the right-hand sidebar:
 >  - The outgoing links are under the ![|25](https://i.imgur.com/vxRVdfa.png) tab
 >  - The backward links are under the ![|25](https://i.imgur.com/wSD0rSm.png) tab

Holding CTRL whilst hovering over a link will open that link's content inside a pop-out window. This can be useful for quickly seeing its content. You can even edit the note inside this pop-out window to some extent, such as checking or unchecking tasks.

 > [!example] Example
 >  - Press `CTRL` and hover over [[My Dashboard|this link]]
 >  - You should be able to see the contents of your `My Dashboard` note
 >  - Bonus: inside that pop-out window, `CTRL` and hover over one of your task links

### Linking to Subsections

Rather than linking to an entire note, you can more specifically target your link to a subsection of a note. To do this, you can reference the heading in the note you wish to link to.

To do this, just add "#" to the end of the note's name inside the link and then type the name of the header you want to link to. 

 > [!example] Example
 >  - Typing \[\[Hello#World]] will link to the `# World` header inside the `Hello` note

### Internal Links in Excalidraw

1. Right click on drawing and select "insert link to file"
2. Select the note you want to link to
3. Double click on the link to rename how it appears on the drawing
4. To edit the actual note link, click on the edit button and change the link text
	 - For example, you might want to add a link to a header inside a note, so you would just edit the note link as per the instructions in this tutorial