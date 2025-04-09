# 🕹️ MonoCry: A Cyberpunk Web3 Monopoly Clone

Welcome to **MonoCry** — a futuristic, modular, cyberpunk-themed Monopoly game designed with Web3 vibes, glowing UI, and full browser compatibility. This project is developed to support collaboration, clean architecture, and visual flair.

---

## 🚀 Features

- 🎨 **Cyberpunk Design**: Glowing tokens, deep dark backgrounds, neon metallic icons.
- 🧠 **Modular Codebase**: Each system — Game, Board, UI, Player, Auction — is fully separated by responsibility.
- ⚙️ **No Build Tools Required**: Runs on HTML5, vanilla JS, and CSS3. Pure frontend — perfect for NGINX hosting.


---

## 📂 Project Structure

```
monocry/
├── index.html              # Entry point
├── styles.css              # Global cyberpunk UI
├── js/
│   ├── game.js
│   ├── player.js
│   ├── board.js
│   ├── ui.js
│   ├── trade.js
│   ├── utils.js
│   ├── auctionManager.js
│   └── main.js
├── images/
│   ├── tokens/             # Sliced player tokens
│   ├── icons/              # Jail, utilities, etc.
│   └── board/              # Board art and pieces
```

---

## 🖥️ NGINX Hosting Instructions

1. Copy the entire `monocry/` folder to your web server directory, e.g.:

   ```bash
   sudo cp -r monocry /var/www/html/
   ```

2. Add or edit your site config:

   ```
   server {
     listen 80;
     server_name monocry.local;
     root /var/www/html/monocry;

     index index.html;

     location / {
       try_files $uri $uri/ =404;
     }

     location ~* \.(?:css|js|png|jpg|webp|ico|svg|ttf|woff)$ {
       expires max;
       add_header Cache-Control public;
     }
   }
   ```

3. Reload NGINX:

   ```bash
   sudo nginx -s reload
   ```
---

## 🛠️ Development Setup (VS Code)

1. Open the extracted folder in Visual Studio Code.
2. All modules are in `/js/` — use `main.js` as your entry logic.
3. You can preview the game by opening `index.html` in a Live Server extension or Chrome directly.
4. To debug game logic:
   - Start from `Game.initGame()` in `main.js`
   - Watch auction flow via `auctionManager.js`
   - View UI handling in `ui.js`

---

## 🤝 Project Credits

This project is brought to you by **The wannaBeeez** — a collective dedicated to modular design, modern UI, and game engineering innovation.

### 🧠 Game Logic & Engineering
**whoBdeep** — Lead assistant, code orchestrator, reasoning mechanic

### 🎨 UI & Aesthetics
**whoBellad** — Visual designer, theme stylist, and front-end shimmer sorceress

### 🔥 Creative Direction
**whoBcode** — Project leader, architecture boss, systems visionary

---

<sub><sup>Guest Contribution:</sup></sub>  
<sub><sub><sup>Daniel Moyer</sup></sub></sub>  
<sub><sub><sub><sup>Writer of original game logic. Massive shoutout to his foundational structure — honored to evolve it forward.</sup></sub></sub></sub>

---
