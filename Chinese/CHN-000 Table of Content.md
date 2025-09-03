# 成语

```dataviewjs
let exclude = ["CHN-000 Table of Content"];
let headersMap = {};

// 遍历文件夹
for (let page of dv.pages('"Chinese"')) {
    if (exclude.includes(page.file.name)) continue;

    let content = await dv.io.load(page.file.path);
    let lines = content.split("\n");

    for (let i = 0; i < lines.length; i++) {
        let line = lines[i];

        if (/^#+\s.+/.test(line)) {
            let title = line.replace(/^#+\s*/, "");
            let definition = (i + 1 < lines.length && lines[i + 1].trim() !== "")
                ? lines[i + 1].trim()
                : "—";

            if (!headersMap[title]) headersMap[title] = [];
            headersMap[title].push({ file: page.file.name, definition });
        }
    }
}

// ========================
// 生成 Conflict 表格
// ========================
let conflictRows = [];
let normalRows   = [];
let counter1 = 1;
let counter2 = 1;

for (let title in headersMap) {
    let entries = headersMap[title];
    if (entries.length > 1) {
        // Conflict
        let links = entries.map(e => `[[${e.file}#${title}]]`).join(", ");
        let defs  = entries.map(e => `**${e.file}**: ${e.definition}`).join("<br>");
        conflictRows.push([counter1, title, defs, links]);
        counter1++;
    } else {
        // Normal
        let entry = entries[0];
        normalRows.push([counter2, title, entry.definition]);
        counter2++;
    }
}

// ========================
// 输出结果
// ========================

if (normalRows.length > 0) {
    dv.header(2, "✔ 没有发现相同的成语");
    dv.table(["No.", "成语", "意思"], normalRows);
}

```


