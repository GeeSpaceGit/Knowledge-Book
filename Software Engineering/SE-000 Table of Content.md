```dataview
TABLE 
    choice(done, "✅", "❌") AS "任务完成"
FROM "Software Engineering"
WHERE !contains(file.name, "SE-000 Table of Content")
SORT file.name ASC
```
