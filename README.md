# 🎮 LegacyMods

> A Modrinth-style mod sharing platform for **Minecraft Legacy Console Edition** mods.

[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![GitHub Pages](https://img.shields.io/badge/hosted-GitHub%20Pages-blue)](https://legacymods.org)

---

## 🗺️ What is LegacyMods?

LegacyMods is an open-source mod hosting platform for the Minecraft Legacy Console Edition community. It allows modders to upload, share, and discover mods in a clean, searchable interface — think Modrinth, but for Legacy Console.

The site is hosted at **[legacymods.org](https://legacymods.org)**.

---

## ✨ Features (Planned & In Progress)

- [ ] Mod browsing & search
- [ ] Mod upload with metadata (name, description, version, tags)
- [ ] User accounts & profiles
- [ ] Download tracking
- [ ] Mod ratings & comments
- [ ] Admin/moderation panel
- [ ] DMCA takedown support

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React (hosted on GitHub Pages) |
| Backend / Database | [Supabase](https://supabase.com) |
| File Storage | [Cloudflare R2](https://cloudflare.com/r2) |

---

## 🚀 Getting Started (Local Development)

### Prerequisites

- Node.js 18+
- A free [Supabase](https://supabase.com) account
- Git

### Setup

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/legacymods.git
cd legacymods

# 2. Install dependencies
cd frontend
npm install

# 3. Set up environment variables
cp .env.example .env
# Fill in your Supabase URL and anon key

# 4. Start the dev server
npm run dev
```

The site will be available at `http://localhost:5173`.

---

## 🤝 Contributing

Contributions are very welcome! Whether it's fixing a bug, improving the UI, or adding a feature — all help is appreciated.

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request.

---

## 📋 Project Structure

```
legacymods/
├── frontend/          # React frontend (GitHub Pages)
│   ├── src/           # Source files
│   └── public/        # Static assets
├── docs/              # Documentation
└── .github/           # Issue templates & GitHub Actions
```

---

## ⚖️ Legal

LegacyMods hosts **user-submitted mods only** and does not distribute or host any leaked source code. We comply with DMCA takedown requests. To submit a takedown, open an issue with the `dmca` label or email the maintainer.

---

## 📄 License

MIT © [Your Name](https://github.com/YOUR_USERNAME)
