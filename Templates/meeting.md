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
_%>
---
attendees:
<%*
for (let i = 0; i < attendees.length; i++) {
	tR += " " + "-" + " " + attendees[i] + "\n";
}
-%>
---

◀️ Last Meeting: [[Meetings/<% tp.date.now("YYYY-MM-DD", -1, tp.file.title, "YYYY-MM-DD") %>|<% tp.date.now("YYYY-MM-DD", -1, tp.file.title, "YYYY-MM-DD") %>]]

▶️ Next Meeting: [[Meetings/<% tp.date.now("YYYY-MM-DD", 1, tp.file.title, "YYYY-MM-DD") %>|<% tp.date.now("YYYY-MM-DD", 1, tp.file.title, "YYYY-MM-DD") %>]]

> [!summary] 
>  - 

## Notes


