<%*
let people = ["Bronwyn", "Charlie", "Ethan", "Harvey", "Jamie", "Louis", "Mark"];
const assignees = [];
while (true) {
  const selectedPerson = await tp.system.suggester(person => person, people);
  if (!selectedPerson) {
    break;
  }
  assignees.push(selectedPerson);
  people = people.filter(person => person !== selectedPerson);
}
_%>
---
assignees: <% assignees %>
date created: <% tp.file.creation_date("YYYY-MM-DD") %>
date completed: 
---
