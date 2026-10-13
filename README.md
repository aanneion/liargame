<div align="center">

# 🎭 LIAR

**Everyone knows the secret word — except one.**

A pass-and-play social deduction party game for **3–20 players** on a single phone.
Available in **English & বাংলা**.

[**▶ Play the Live Demo**](https://itsliar.netlify.app/)

![Status](https://img.shields.io/badge/status-live-22e6a5?style=flat-square)
![Made with](https://img.shields.io/badge/made%20with-HTML%20%2B%20CSS%20%2B%20JS-4D6EFF?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-C8FF4D?style=flat-square)
![Players](https://img.shields.io/badge/players-3%20to%2020-FF5BA7?style=flat-square)

</div>

---

| Setup | Peek | Discuss | Result |

---

## 🎮 What is LIAR?

**LIAR** is a party game for one phone that gets passed around. Everyone sees the same secret word — except one player, who is the **liar**. Through casual conversation and clever bluffing, the group tries to figure out who doesn't actually know the word.

No accounts. No internet needed during play. No app install. Just open the link and hand the phone to the next person.

---

## ✨ Features

- 🎭 **Social deduction on one device** — pass-and-play, no extra hardware
- 👥 **3–20 players** — works for a small hangout or a big party
- 🌍 **30 topic categories** — countries, food, jobs, animals, movies, brands, and more
- 📖 **900+ words** in both English and Bengali
- 🔐 **Hold-to-peek fingerprint scan** — 1.1-second press reveals your role privately
- 📲 **Auto-advance between players** — no tapping "next" needed
- 🌐 **IP-based language detection** — Bangladeshi users get বাংলা, everyone else gets English
- 🔁 **Manual language toggle** — 🌐 button in the header, preference saved locally
- 🎨 **Neo-brutalist app-shell UI** — chunky borders, hard shadows, native-app feel
- 📴 **Zero dependencies** — single HTML file, no build step, no frameworks

---

## 🕹️ How to Play

1. **Choose a category** on the setup screen.
2. **Set the number of players** (3–20).
3. **Pass the phone around.** Each player holds their finger on the big button for ~1 second.
   - Most players see the **secret word**.
   - One player sees **"You're the Liar!"**
4. **Discuss.** Talk about the word without giving it away completely. The liar has to bluff.
5. **Reveal.** Tap *Who is the Liar?* to see who was fooling everyone and what the real word was.

> 💡 **Tip for the liar:** Listen carefully to how others describe the word — mirror their tone, don't overcommit, and don't be the first to speak.

---

## 🛠️ Tech Stack

| Layer | Choice |
|---|---|
| **Markup** | Single `index.html` — no bundler, no framework |
| **Styling** | Vanilla CSS with custom properties (CSS variables) |
| **Logic** | Vanilla JavaScript (ES2017+, no transpile) |
| **Fonts** | Google Fonts — *Hind Siliguri* (Bengali) + *Space Grotesk* (Latin) |
| **Language detection** | IP lookup via [`api.country.is`](https://country.is) + [`get.geojs.io`](https://get.geojs.io) (parallel, timeout-protected) |
| **Hosting** | [Netlify](https://netlify.com) (static) |

No npm install. No webpack. No node_modules. Just one file.

---

## 🌐 How Language Detection Works

The game picks a language in this priority order:

1. **Saved preference** — if the user previously picked a language, that choice wins instantly.
2. **IP country lookup** — two free IP APIs are queried in parallel (`Promise.any`). `BD` → Bengali, anything else → English.
3. **Browser language fallback** — if both APIs fail or time out, fall back to `navigator.languages`.

The detection runs behind a splash screen, so there is no flash of the wrong language. Once the user taps the 🌐 button, their choice is saved in `localStorage` and IP lookup is skipped on all future visits.

---

## 🚀 Run Locally

No build step required. Just open the file:

```bash
# Option 1: double-click index.html

# Option 2: any static server
python3 -m http.server 8000
# then visit http://localhost:8000
```

---

## 📦 Deploy

**Netlify Drop** (what I use):
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag the folder containing `index.html` and `og-image.png`
3. Done — you get a live URL in seconds

**GitHub Pages** also works: push to a repo and enable Pages in Settings.

---

## 🗂️ Project Structure

```
.
├── index.html      # the entire game — HTML, CSS, JS in one file
├── og-image.png    # 1200×630 social preview card
└── README.md       # this file
```

That's it. Truly.

---

## 🗺️ Roadmap

- [ ] Custom word packs (users can add their own categories)

---

## 🤝 Contributing

This started as a personal project but PRs are welcome. If you'd like to add a category, fix a translation, or improve the UI:

1. Fork the repo
2. Create a branch (`git checkout -b feature/amazing-idea`)
3. Commit your changes (`git commit -m 'Add amazing idea'`)
4. Push and open a Pull Request

For large changes, open an issue first so we can discuss it.

---

## 📄 License

Released under the **MIT License** — free to use, modify, and distribute.

---

<div align="center">

**Made with ❤️ by [Neion](https://fb.com/aanNEION)**

If you enjoyed the game, drop a ⭐ on the repo — it really helps!

</div>
