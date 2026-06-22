<%*
let title = await tp.system.prompt("Keycap Set Name (e.g., GMK Laser):") || tp.file.title;
await tp.file.rename(title);

let status = await tp.system.suggester(
  ["Mounted ⌨️", "Stored in Tray 📦", "On the Way ✈️"], 
  ["Mounted", "Stored", "Ordered"], 
  false, 
  "Where are they?"
);

let rating = await tp.system.suggester(
  ["⭐⭐⭐⭐⭐", "⭐⭐⭐⭐", "⭐⭐⭐", "⭐⭐", "⭐"], 
 ["⭐⭐⭐⭐⭐", "⭐⭐⭐⭐", "⭐⭐⭐", "⭐⭐", "⭐"], 
  false, 
  "Aesthetics Rating (1-5)?"
);
-%>
---
type: keycaps
designer:
status: <% status %>
rating: <% rating %>
profile: 
material:
kits:
mounted_on: 
cover: <% title %>_photo.png
tags:
  - keycaps-log
---

# 🎨 <% title %>

![[<% title %>_photo.jpg|600]]
*(📸 Drag your photo here and rename it to "<% title %>_photo.png")*

---

### 📝 Quick Details
- **Profile:** `= this.profile`
- **Material:** `= this.material`
- **Mounted On:** `= this.mounted_on`
- Kits: `= this.kits`
