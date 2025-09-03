```dataviewjs
// 想要排除的文件名（不要写扩展名 .md）
let exclude = ["ENG-000 Table of Content"];

let rows = [];
let counter = 1;

for (let page of dv.pages('"English"')) {
    // 如果文件名在排除清单，就跳过
    if (exclude.includes(page.file.name)) continue;

    let content = await dv.io.load(page.file.path);
    let headers = content.match(/^#+\s.+/gm);

    if (headers) {
        for (let h of headers) {
            let title = h.replace(/^#+\s*/, "");
            rows.push([counter, page.file.name, title]);
            counter++;
        }
    }
}

// 生成表格
dv.table(["No.", "File", "Vocabulary"], rows);
```