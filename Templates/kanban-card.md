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
date: {{Date:YYYY-MM-DD}}
assignees: <% assignees %>
---
