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
const folder = "Meetings"; 
const currentFile = tp.file.title; 

const files = app.vault.getFiles()
    .filter(f => f.path.startsWith(folder + "/") && /^\d{4}-\d{2}-\d{2}\.md$/.test(f.name))
    .sort((a, b) => a.name.localeCompare(b.name));

const fileNames = files.map(f => f.name.replace(".md", ""));

const index = fileNames.indexOf(title);

let previousLink = index > 0 ? `[[Meetings/${fileNames[index - 1]}|Previous Meeting]]` : "No previous meeting";
let nextLink = index >= 0 && index < fileNames.length - 1 ? `[[Meetings/${fileNames[index + 1]}|Next Meeting]]` : "No next meeting";
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

◀️ <% previousLink %>

▶️ <% nextLink %>

> [!summary] 
>  - 

## Notes


