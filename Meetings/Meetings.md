```dataview
TABLE WITHOUT ID
file.link AS "",
file.frontmatter.attendees as "Attendees"
FROM "Meetings"
WHERE file.name != this.file.name
SORT file.name desc
```

