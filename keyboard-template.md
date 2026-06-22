<%*
// 1. Prompt for keyboard name and rename file
let title = await tp.system.prompt("Keyboard Name (e.g., Mode Sonnet):") || tp.file.title;
await tp.file.rename(title);

// 2. Select status
let status = await tp.system.suggester(
  ["Daily Driver 🏎️", "On the Shelf 📦", "Work in Progress 🛠️"], 
  ["Daily Driver", "On the Shelf", "WIP"], 
  false, 
  "What is the status?"
);

// 3. Select rating
let rating = await tp.system.suggester(
  ["⭐⭐⭐⭐⭐", "⭐⭐⭐⭐", "⭐⭐⭐", "⭐⭐", "⭐"], 
   ["⭐⭐⭐⭐⭐", "⭐⭐⭐⭐", "⭐⭐⭐", "⭐⭐", "⭐"],
  false, 
  "Vibe Rating (1-5)?"
);

// 4. Select sound profile
let sound = await tp.system.suggester(
  ["Thocky 🟫", "Clacky 🟦", "Creamy ⬜", "Silent 🟩", "Skip / Other ➡️"], 
  ["Thocky", "Clacky", "Creamy", "Silent", ""], 
  false, 
  "Sound Profile?"
);
-%>
---
type: keyboard
designer:
status: <% status %>
rating: <% rating %>
sound: <% sound %>
switches: 
keycaps: 
cover: <% title %>_photo.jpg
tags:
  - keyboard-log
---

# ⌨️ <% title %>

![[<% title %>_photo.jpg|600]]
*(📸 Drag your photo here and rename the image file to "<% title %>_photo.jpg")*

---

### 🧩 The Recipe
- **Switches:** `= this.switches`
- **Keycaps:** `= this.keycaps`

---

### 💭 The Story
*Write any fun build notes, modifications, or typing experiences here.*

-