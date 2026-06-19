# GamU
PJK-GM083 | AI for Smart Recommendation Systems
## Tim Kami

| Nama | Cohort ID |
| :--- | :--- |
| Hildan Kusto Utomo | APC702D6Y0009 |
| Nurrizky Arum Jatmiko | APC283D6Y0038 |
| Firda Azzahra | APC222D6X0154 |
| Karima Ulya Hermawan | APC222D6X0156 |

## Latar Belakang

Tim kami mengembangkan **GamU**, sebuah sistem rekomendasi *game* yang dirancang untuk mengatasi masalah pencarian *game* yang kaku di *platform* konvensional. Berbeda dengan sistem pencarian biasa yang sangat bergantung pada *filter tag* manual dan rentan terhadap bias popularitas, GamU memungkinkan pengguna untuk mencari *game* menggunakan *prompt* judul game.

Dengan *Content-Based Filtering* (TF-IDF & Cosine Similarity) terhadap lebih dari 40.000 *dataset* *game* Steam, GamU dapat memberikan rekomendasi yang sangat personal, akurat, dan bebas halusinasi. Aplikasi ini akan membantu pengguna menemukan *hidden gems* murni berdasarkan judul game.

### Key Features

| # | Fitur | Deskripsi |
| :--- | :--- | :--- |
| 1 | **Natural Language Game Search** | Pengguna menulis preferensi dalam bahasa biasa (e.g. *"game santai buat dimainkan bareng teman"*), sistem memahami konteks & niat pengguna via LLM |
| 2 | **Title-Based Similarity Lookup** | Pencarian berdasarkan judul *game* spesifik, menggunakan *precomputed similarity data* dari 40.000+ *dataset* Steam |
| 3 | **LLM-Powered Structured Explanations** | Setiap rekomendasi disertai penjelasan terstruktur (intro, highlights, conclusion) yang di-*generate* oleh Gemini; OpenRouter sebagai *fallback* |
| 4 | **TF-IDF Content-Based Filtering** | Algoritma TF-IDF & Cosine Similarity untuk menemukan *game* yang mirip secara cerita & *vibe*, menghindari *bias popularitas* |
| 5 | **Steam Cover Images** | Header *image* *game* diambil dari Steam Store API dan di-*cache* di SQLite untuk mengurangi *API call* berulang |
| 6 | **Prompt Injection Defense** | *Input sanitization* yang mem-strip *structural attack* (control chars, injection patterns) dan memperkuat *prompt delimiter* |
| 7 | **Dark Theme Gaming UI** | Antarmuka dark-first dengan gradient, glow effect, dan typography gaming (Chakra Petch + Russo One) di atas shadcn/ui & Radix UI |
| 8 | **Responsive & SSR** | Frontend berbasis TanStack Start + Nitro (React SSR), responsif di semua *device* |

### Tech Stack

| Layer | Teknologi |
| :--- | :--- |
| **Frontend** | React 19 · TanStack Start (SSR + Nitro) · TanStack Query · shadcn/ui · TailwindCSS v4 · Bun |
| **Backend** | Effect.ts · @effect/platform · @effect/ai-google (Gemini) · @effect/ai-openai (OpenRouter fallback) · Bun |
| **ML Inference** | Flask · Gunicorn · TF-IDF + Cosine Similarity · Python 3.12 |
| **Data** | SQLite (Steam image cache) · JSON (game data + similarity lookup) · TF-IDF pickle files |
| **Infrastructure** | DigitalOcean · Docker Compose · Nginx + Let's Encrypt · OpenTofu (terraform) · GitHub Actions CI/CD · GHCR · Cloudflare DNS |

## Infrastruktur

<img width="916" height="611" alt="cloud drawio" src="https://github.com/user-attachments/assets/86eb1b3a-c2d6-47cc-bd1d-a8e7f78bbd2f" />
