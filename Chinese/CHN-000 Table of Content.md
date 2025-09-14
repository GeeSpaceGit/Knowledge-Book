# 成语

```dataviewjs
// 想要包含的文件名（不要写扩展名 .md）
let include = ["CHN-001 成语 1", "CHN-002 Sample"];

let rows = [];
let headersMap = {};
let counter = 1;

// 遍历文件
for (let page of dv.pages('"Chinese"')) {
    if (!include.includes(page.file.name)) continue;

    let content = await dv.io.load(page.file.path);
    let lines = content.split("\n");

    for (let i = 0; i < lines.length; i++) {
        let line = lines[i];

        if (/^#+\s.+/.test(line)) {
            let title = line.replace(/^#+\s*/, "");
            let definition = (i + 1 < lines.length && lines[i + 1].trim() !== "")
                ? lines[i + 1].trim()
                : "—";

            // 记录总表
            rows.push([
                counter,
                `[[${page.file.name}#${title}|${title}]]`,
                definition,
            ]);
            counter++;

            // 记录冲突检查
            if (!headersMap[title]) headersMap[title] = [];
            headersMap[title].push({ file: page.file.name, definition });
        }
    }
}

// --- 输出部分 ---

// 1️⃣ 总表
dv.header(2, "📋 All Headers");
dv.table(["No.", "成语", "含义"], rows);

// 2️⃣ 冲突检查
let conflictRows = [];
let conflictCounter = 1;

for (let title in headersMap) {
    let entries = headersMap[title];
    if (entries.length > 1) {
        let links = entries.map(e => `[[${e.file}#${title}]]`).join(", ");
        let defs  = entries.map(e => `**${e.file}**: ${e.definition}`).join("<br>");
        conflictRows.push([conflictCounter, title, defs]);
        conflictCounter++;
    }
}

if (conflictRows.length > 0) {
    dv.table(["No.", "成语", "含义"], conflictRows);
} else {
    dv.paragraph("✅ 没有发现重复的成语");
}

```




