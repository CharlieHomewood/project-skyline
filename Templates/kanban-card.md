<%*
let people = ["Bronwen", "Charlie", "Ethan", "Harvey", "Jamie", "Louis", "Mark"];
const assignees = [];
while (true) {
  const selectedPerson = await tp.system.suggester(person => person, people);
  if (!selectedPerson) {
    break;
  }
  assignees.push(selectedPerson);
  people = people.filter(person => person !== selectedPerson);
}
assignees.sort();
_%>
---
assignees:
<%*
for (let i = 0; i < assignees.length; i++) {
	tR += " " + "-" + " " + assignees[i] + "\n";
}
-%>
date created: <% tp.file.creation_date("YYYY-MM-DD") %>
date completed:
date due: 
tags: 
 - task
---

description::<br>

## Sub-tasks

 - [ ] 
 - [ ] 
 - [ ] 

## Relevant Notes

