
```dataviewjs
dv.table(
  ["File", "Attendees"],
  dv.pages('"Meetings"')
    .where(p => p.file.path !== dv.current().file.path)
    .sort(p => p.file.name, 'desc')
    .map(p => [
      p.file.link,
      Array.isArray(p.attendees) ? p.attendees.join(", ") : (p.attendees ?? "")
    ])
);
```

