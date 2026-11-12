# JARVIS Web — Interactive AI Agent Dashboard & Console

<div align="center">

  [![Live Web Demo](https://img.shields.io/badge/Live_Web_Demo-JARVIS_Online-FFD700?style=for-the-badge&logo=vercel&logoColor=black)](https://jarvis-web-gold.vercel.app)
  [![Vue 3](https://img.shields.io/badge/Vue_3-3.2.x-42B883?style=for-the-badge&logo=vue.js&logoColor=white)](https://vuejs.org/)
  [![Vite](https://img.shields.io/badge/Vite-3.2.x-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
  [![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.2-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
  [![Core Engine](https://img.shields.io/badge/Core_Agent-JARVIS_%2F_HuggingGPT-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com/temp-pie1207/JARVIS)
  [![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

  <p align="center">
    <strong>A modern, responsive web client and desktop dashboard for the JARVIS / HuggingGPT autonomous agent system. Connects LLMs as orchestrators with 100+ HuggingFace multimodal models through real-time task decomposition and visual telemetry.</strong>
  </p>

  <p align="center">
    <a href="https://jarvis-web-gold.vercel.app"><strong>⚡ Explore Live Web App (Vercel) ↗</strong></a> •
    <a href="https://github.com/temp-pie1207/JARVIS">Core AI Agent Engine</a> •
    <a href="https://github.com/temp-pie1207/Portfolio_Naman">Author Portfolio</a>
  </p>

</div>

---

## ✦ System Architecture & Workflow

JARVIS Web connects to the HuggingGPT controller daemon and translates natural language multimodal prompts into a 4-stage pipeline visualized live in the UI:

```
+--------------------------------------------------------------------------------+
|                             USER MULTIMODAL PROMPT                             |
|          "Generate an image of a cybernetic tiger, then describe it"           |
+--------------------------------------------------------------------------------+
                                       │
                                       ▼
                     STAGE 1: TASK DECOMPOSITION & PLANNING
            LLM parses user intent into a Directed Acyclic Graph (DAG)
         [Task 1: text-to-image]  ───►  [Task 2: image-to-text / captioning]
                                       │
                                       ▼
                          STAGE 2: MODEL SELECTION
            Selects best HuggingFace Hub expert models based on metadata
     Task 1: "stabilityai/stable-diffusion-2-1" | Task 2: "nlpconnect/vit-gpt2"
                                       │
                                       ▼
                          STAGE 3: TASK EXECUTION
          Hybrid inference (Local GPU workers + HuggingFace Inference API)
                                       │
                                       ▼
                        STAGE 4: RESPONSE GENERATION
          Synthesizes image outputs, captions, and generated audio response
+--------------------------------------------------------------------------------+
|                        JARVIS WEB CHAT & TELEMETRY UI                         |
+--------------------------------------------------------------------------------+
```

---

## ✦ Key Features

- **⚡ Interactive Agent Console**: Real-time streaming conversation view displaying intermediate sub-tasks, chosen models, confidence scores, and outputs.
- **🎙️ Multimodal Input**: Supports text prompts, microphone voice capture, image attachments, and media file uploads.
- **🧠 Transparent Reasoning Logs**: Expandable telemetry trays showcasing intermediate JSON task plans and model execution benchmarks.
- **⚙️ Dynamic Configuration Drawer**: Configure custom backend URLs (`/tasks`, `/results`), OpenAI API keys, HuggingFace Hub tokens, and audio voice synthesis settings on the fly.
- **🖥️ Cross-Platform Desktop Support**: Pre-configured with Electron wrappers for native desktop execution on Windows, macOS, and Linux.
- **🌐 Responsive Design**: Mobile-friendly, glassmorphic cyberpunk dark UI built with Tailwind CSS.

---

## ✦ Tech Stack

| Domain | Technology | Description |
|:---|:---|:---|
| **Framework** | [Vue 3](https://vuejs.org/) (Composition API) | Reactive single-page application framework |
| **Bundler** | [Vite 3](https://vitejs.dev/) | Ultra-fast HMR and production bundle compilation |
| **Styling** | [Tailwind CSS 3](https://tailwindcss.com/) + PostCSS | Utility-first responsive design system |
| **Language** | [TypeScript](https://www.typescriptlang.org/) | Type-safe state management and API types |
| **HTTP Client** | [Axios](https://axios-http.com/) | RESTful communication with backend daemon |
| **Desktop Wrapper** | [Electron](https://www.electronjs.org/) | Cross-platform desktop packaging |
| **Cloud Hosting** | [Vercel](https://vercel.com/) | Edge CDN static distribution |

---

## ✦ Getting Started Locally

### Prerequisites
- Node.js 18+ (Node 20+ recommended)
- npm or yarn

### 1. Clone & Install

```bash
git clone https://github.com/temp-pie1207/jarvis-web.git
cd jarvis-web
npm install
```

### 2. Run Local Development Server

```bash
npm run dev
```

Navigate to `http://localhost:5173` to access the interface.

### 3. Connect to JARVIS Backend Daemon

To connect the web interface to a running JARVIS Python server:
1. Start the JARVIS engine:
   ```bash
   cd ../JARVIS
   python awesome_chat.py --config configs/config.default.yaml --mode server
   ```
2. In the JARVIS Web UI, open the **Settings** gear icon (⚙️).
3. Set the server endpoint to `http://localhost:8004` (or your remote daemon address).

### 4. Build for Production

```bash
npm run build-only
```

The compiled assets will be placed in `dist/`.

### 5. Run as Desktop App (Electron)

```bash
npm run e:dev
```

---

## ✦ Deployment

This project is deployed live on **Vercel**:

```bash
npx --yes vercel --prod --yes
```

- **Production URL**: [https://jarvis-web-gold.vercel.app](https://jarvis-web-gold.vercel.app)

---

## ✦ Author & Contact

**Naman Kashyap**
- 🐙 GitHub: [@temp-pie1207](https://github.com/temp-pie1207)
- 🌐 Echo Portfolio: [naman-portfolio-theta.vercel.app](https://naman-portfolio-theta.vercel.app)
- 💼 Davies Portfolio: [davies-ten.vercel.app](https://davies-ten.vercel.app)
- 💻 LeetCode: [Naman_1207](https://leetcode.com/u/Naman_1207/)
- 📧 Email: [namankashyap484@gmail.com](mailto:namankashyap484@gmail.com)

---

## ✦ License

This project is licensed under the [MIT License](LICENSE).
