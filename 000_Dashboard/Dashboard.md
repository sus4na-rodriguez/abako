
# 🗂 ABAKO Dashboard

Welcome! This is your control panel for the vault.  
Use it to jump quickly to active work, research, and tasks.

---

## 📥 Inbox

- [[00_Inbox]]
    

---

## ✍️ Active Articles

```dataview
table Status, file.mtime as "Last Modified"
from "01_Articles"
where Status != "Final" or !exists(Status)
sort file.mtime desc
limit 5
```

---

## 🔍 Research in Progress

```dataview
table Source, file.mtime as "Last Modified"
from "02_Research"
sort file.mtime desc
limit 5
```

---

## ✅ Tasks

```dataview
task from "01_Articles" or "02_Research"
where !completed
group by file.folder
```

---

## 🧰 Shortcuts

- [[01_Articles]]
    
- [[02_Research]]
    
- [[03_Files]]
    
- [[99_Templates]]