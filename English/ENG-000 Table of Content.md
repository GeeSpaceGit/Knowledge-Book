```dataviewjs
// 想要包含的文件名（不要写扩展名 .md）
let include = ["ENG-001-1 Vocabulary 1"];

let rows = [];
let headersMap = {};
let counter = 1;

for (let page of dv.pages('"English"')) {
    if (!include.includes(page.file.name)) continue;

    let content = await dv.io.load(page.file.path);
    let lines = content.split("\n");

    for (let i = 0; i < lines.length; i++) {
        let line = lines[i];

        if (/^#+\s.+/.test(line)) {
            let title = line.replace(/^#+\s*/, "");

            // 下一行 = Chinese Meaning
            let chineseMeaning = (i + 1 < lines.length && lines[i + 1].trim() !== "")
                ? lines[i + 1].trim()
                : "—";

            // 再下一行 = Definition
            let definition = (i + 2 < lines.length && lines[i + 2].trim() !== "")
                ? lines[i + 2].trim()
                : "—";

            // 加入总表
            rows.push([
                counter,
                `[[${page.file.name}#${title}|${title}]]`, // Vocabulary
                chineseMeaning,
                definition
            ]);
            counter++;

            // 用来检查冲突
            if (!headersMap[title]) headersMap[title] = [];
            headersMap[title].push({ file: page.file.name, chineseMeaning, definition });
        }
    }
}

// --- 输出部分 ---

// 📋 总表
dv.header(2, "📋 All Vocabulary");
dv.table(["No.", "Vocabulary", "Chinese Meaning", "Definition"], rows);

// ⚠️ 冲突检查
let conflictRows = [];
let conflictCounter = 1;

for (let title in headersMap) {
    let entries = headersMap[title];
    if (entries.length > 1) {
        let defs = entries.map(e =>
            `**${e.file}**<br>Chinese: ${e.chineseMeaning}<br>Definition: ${e.definition}`
        ).join("<br><br>");
        conflictRows.push([
            conflictCounter,
            title,
            defs,
            entries.map(e => `[[${e.file}#${title}]]`).join(", ")
        ]);
        conflictCounter++;
    }
}

if (conflictRows.length > 0) {
    dv.header(2, "⚠️ Conflicts");
    dv.table(["No.", "Vocabulary", "Details", "Files"], conflictRows);
} else {
    dv.paragraph("✅ 没有发现重复的Vocabulary");
}

```


A1 to C2 Vocabulary
https://englishprofile.org/?menu=evp-online&dict=uk