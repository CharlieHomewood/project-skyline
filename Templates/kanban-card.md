<%
let people = ["Alice", "Bob", "Charlie", "Dana"];
let selected = await tp.system.suggester(people, people, true);
%>
---
date: <% tp.file.creation_date("YYYY-MM-DD") %>
assignees: <% selected %>
---
