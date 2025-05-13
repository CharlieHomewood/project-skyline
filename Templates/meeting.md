<%*
let title = tp.date.now("YYYY-MM-DD");
let existingFile = app.vault.getFiles().find(f => f.path === "Meetings/" + title + ".md");

if (!existingFile) {
  await tp.file.move("Meetings/" + tp.file.title); 
  await tp.file.rename(title);
} else {
  title = title + "-New"; 
  await tp.file.rename(title);
}

let people = ["Bronwen", "Charlie", "Ethan", "Harvey", "Jamie", "Louis", "Mark"];
const attendees = [];
while (true) {
  const selectedPerson = await tp.system.suggester(person => person, people);
  if (!selectedPerson) {
    break;
  }
  attendees.push(selectedPerson);
  people = people.filter(person => person !== selectedPerson);
}
attendees.sort();
_%>
---
attendees:
<%*
for (let i = 0; i < attendees.length; i++) {
	tR += " " + "-" + " " + attendees[i] + "\n";
}
-%>
date: <% tp.file.creation_date("YYYY-MM-DD") %>
---

```dataviewjs
const folder = "Meetings";
let pages = dv.pages(`"${folder}"`)
    .where(p => p.file.name.match(/^\d{4}-\d{2}-\d{2}$/))
    .sort(p => p.file.name);

let currentIndex = pages.findIndex(p => p.file.name === dv.current().file.name);

if (currentIndex > 0) {
  let prev = pages[currentIndex - 1];
  dv.paragraph(`◀️ [[${prev.file.path}|Previous Meeting]]`);
} else {
  dv.paragraph("◀️ No previous meeting");
}

if (currentIndex >= 0 && currentIndex < pages.length - 1) {
  let next = pages[currentIndex + 1];
  dv.paragraph(`▶️ [[${next.file.path}|Next Meeting]]`);
} else {
  dv.paragraph("▶️ No next meeting");
}
```

> [!summary] 
>  - 

## Notes


