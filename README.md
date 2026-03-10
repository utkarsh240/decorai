<div align="center">

# 🏛️ DecorAI

### AI-Powered Architectural Visualization SaaS

**Transform 2D floor plans into photorealistic 3D renders — powered by Claude & Gemini, hosted forever.**

[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Puter](https://img.shields.io/badge/Puter.js-FF6B35?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyem0wIDE4Yy00LjQxIDAtOC0zLjU5LTgtOHMzLjU5LTggOC04IDggMy41OSA4IDgtMy41OSA4LTggOHoiLz48L3N2Zz4=&logoColor=white)](https://puter.com/)

[Live Demo](#) · [Documentation](#) · [Report Bug](../../issues) · [Request Feature](../../issues)

---

![DecorAI Banner](https://via.placeholder.com/1200x400/1a1a2e/00d4ff?text=DecorAI+%7C+2D+Floor+Plans+%E2%86%92+Photorealistic+3D+Renders)

</div>

---

## 📋 Table of Contents

- [About the Project](#-about-the-project)
- [Key Features](#-key-features)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [Architecture Overview](#-architecture-overview)
- [How It Works](#-how-it-works)
- [Community Feed](#-community-feed)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🏗️ About the Project

**DecorAI** is a full-stack AI-powered architectural visualization SaaS that lets architects, interior designers, and homeowners upload 2D floor plans and instantly receive photorealistic 3D renders — with zero backend infrastructure to manage.

Built on top of [Puter.js](https://puter.com/), DecorAI leverages serverless cloud workers, permanent file hosting, and persistent KV storage — all from the frontend. AI rendering is powered by a dual-model pipeline using **Anthropic Claude** for spatial reasoning and **Google Gemini** for image synthesis.

> 💡 *No servers. No DevOps. Just upload, transform, and share.*

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 🖼️ **2D → 3D Transformation** | Upload a floor plan image and receive a photorealistic architectural render |
| 🤖 **Dual AI Pipeline** | Claude handles spatial analysis; Gemini drives image generation |
| ☁️ **Permanent Hosting** | Renders are stored forever via Puter's distributed file system |
| 🗄️ **Persistent Metadata** | Project names, tags, timestamps, and settings saved in Puter KV storage |
| ⚡ **Serverless Workers** | Heavy transformations run in Puter's edge workers — no cold starts |
| 🌍 **Global Community Feed** | Browse, discover, and like renders from the worldwide DecorAI community |
| 🔐 **Auth-free by Default** | Puter handles identity — no passwords, no OAuth flows to configure |

---

## ⚙️ Tech Stack

### Frontend

| Technology | Purpose |
|---|---|
| [**React**](https://reactjs.org/) | Component-based UI architecture for a fast, reactive single-page application |
| [**TypeScript**](https://www.typescriptlang.org/) | Static typing for safer, more maintainable frontend code |
| [**Vite**](https://vitejs.dev/) | Lightning-fast HMR dev server and optimized production bundler |
| [**TailwindCSS**](https://tailwindcss.com/) | Utility-first CSS framework for rapid, consistent UI styling |

### Cloud & AI Infrastructure

| Technology | Purpose |
|---|---|
| [**Puter**](https://puter.com/) | Internet OS providing serverless workers, permanent storage, and KV database |
| [**Puter.js SDK**](https://docs.puter.com/) | Frontend SDK to interact with all Puter cloud services without a backend |
| [**Anthropic Claude**](https://anthropic.com/) | Spatial understanding, floor plan analysis, and architectural reasoning |
| [**Google Gemini**](https://deepmind.google/technologies/gemini/) | High-fidelity photorealistic image generation from structured prompts |

### Developer Tooling

| Technology | Purpose |
|---|---|
| [**CodeRabbit**](https://coderabbit.ai/) | AI-powered code review with automated security and quality suggestions |
| [**Junie by JetBrains**](https://www.jetbrains.com/junie/) | In-IDE AI assistant for complex logic, refactoring, and prompt engineering |

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** v18+
- **npm** or **yarn**
- A [Puter account](https://puter.com/) (free)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/your-username/decorai.git
cd decorai

# 2. Install dependencies
npm install

# 3. Start the development server
npm run dev
```

> No `.env` file needed! Puter.js handles authentication and all cloud services directly in the browser.

### Build for Production

```bash
npm run build
```

The output is a fully static site — deploy it anywhere (Netlify, Vercel, Puter Static Hosting, GitHub Pages).

---

## 🏛️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                        DecorAI Client                        │
│                   React + TypeScript + Vite                  │
└────────────────────────┬────────────────────────────────────┘
                         │  Puter.js SDK
          ┌──────────────┼──────────────────┐
          │              │                  │
   ┌──────▼──────┐ ┌─────▼─────┐ ┌─────────▼────────┐
   │  Puter File  │ │  Puter KV │ │  Puter Serverless │
   │   Storage    │ │  Database │ │     Workers       │
   │ (Permanent   │ │(Metadata, │ │ (AI Orchestration)│
   │   Renders)   │ │ Settings) │ │                   │
   └─────────────┘ └───────────┘ └────────┬──────────┘
                                          │
                          ┌───────────────┼──────────────┐
                          │                              │
                   ┌──────▼──────┐              ┌────────▼──────┐
                   │   Claude    │              │    Gemini     │
                   │  (Spatial   │              │   (Image      │
                   │  Analysis)  │              │  Generation)  │
                   └─────────────┘              └───────────────┘
```

---

## 🔄 How It Works

1. **Upload** — User uploads a 2D floor plan (PNG, JPG, PDF)
2. **Analyze** — Claude processes the floor plan, extracting room dimensions, layouts, and spatial relationships
3. **Prompt Engineering** — A structured architectural render prompt is generated from Claude's analysis
4. **Generate** — Gemini receives the prompt and produces a photorealistic 3D visualization
5. **Store** — The render is permanently stored in Puter's file system; metadata (project name, style, timestamp) is saved to Puter KV
6. **Share** — The result is published to the global community feed with a permanent shareable URL

---

## 🌍 Community Feed

DecorAI features a **live global community feed** where all public renders are discoverable. Powered by Puter KV's high-performance storage, the feed supports:

- 📄 Infinite scroll with KV-backed pagination
- ❤️ Like and save renders from other users
- 🔍 Filter by style (Modern, Industrial, Scandinavian, etc.)
- 🔗 Permanent, shareable render URLs

---

## 🗺️ Roadmap

- [ ] Style presets (Modern, Brutalist, Art Deco, Biophilic)
- [ ] Multi-room floor plan support
- [ ] Real-time collaborative editing
- [ ] Video walkthrough generation from renders
- [ ] Furnishing and material overlays
- [ ] Export to CAD-compatible formats
- [ ] Pro tier with private projects and team workspaces

---

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

> All PRs are reviewed using **CodeRabbit** for automated quality and security analysis.

---

## 📄 License

Distributed under the MIT License. See [`LICENSE`](LICENSE) for more information.

---

<div align="center">

Built with ❤️ using [Puter.js](https://puter.com/), [Claude](https://anthropic.com/), and [Gemini](https://deepmind.google/technologies/gemini/)

⭐ Star this repo if you find it useful!

</div>