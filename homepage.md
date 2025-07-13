
### unpublished
```dataviewjs
const pages = dv.pages("").where(p => p.file.path.includes("content/") && p.draft === true);
const grouped = pages.groupBy(p => p.file.folder);

for (let group of grouped) {
  dv.header(6, group.key);
  dv.list(group.rows.map(p => p.file.link));
}
```
### unedited
```dataviewjs
const pages = dv.pages("")
  .where(p => p.file.path.includes("content/") && p.draft === undefined);

const grouped = pages.groupBy(p => p.file.folder);

for (let group of grouped) {
  dv.header(6, group.key);
  dv.list(group.rows.map(p => p.file.link));
}
```

### published
```dataviewjs
const pages = dv.pages("").where(p => p.file.path.includes("content/") && p.draft === false);
const grouped = pages.groupBy(p => p.file.folder);

for (let group of grouped) {
  dv.header(6, group.key);
  dv.list(group.rows.map(p => p.file.link));
}
```




