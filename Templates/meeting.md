<%*
let title = tp.date.now("YYYY-MM-DD") 
await tp.file.move("Meetings/" + tp.file.title)
await tp.file.rename(title)
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

const index = fileNames.indexOf(currentFile);

let previousLink = index > 0 ? `[[Meetings/${fileNames[index - 1]}|Previous Meeting]]` : "_No previous meeting_";
let nextLink = index < fileNames.length - 1 ? `[[Meetings/${fileNames[index + 1]}|Next Meeting]]` : "_No next meeting_";
_%>
---
attendees:
<%*
for (let i = 0; i < attendees.length; i++) {
	tR += " " + "-" + " " + attendees[i] + "\n";
}
-%>
---

◀️ <% previousLink %>

▶️ <% nextLink %>

> [!summary] 
>  - 

## Notes


