```dataview
TABLE WITHOUT ID
  file.link AS "File",
  split(file.tags[0], "/")[1] AS "Status"
FROM #status
WHERE file.tags
  AND any(file.tags, (t) => startswith(t, "#status/"))
SORT split(file.tags[0], "/")[1] ASC
```




