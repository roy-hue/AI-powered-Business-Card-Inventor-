# # 🎨✨ AI Business Card Creator

> **Transform credential URLs into stunning, print-ready business cards — powered by dual AI agents**

&nbsp;

[![Platform](https://img.shields.io/badge/Platform-Base44-6366f1?style=for-the-badge)](https://base44.com)
[![React](https://img.shields.io/badge/React-18.2-61dafb?style=for-the-badge&logo=react)](https://reactjs.org)
[![AI](https://img.shields.io/badge/AI-Multi--Agent-22c55e?style=for-the-badge)](https://base44.com)
[![PDF](https://img.shields.io/badge/Export-Print--Ready%20PDF-f97316?style=for-the-badge)](https://base44.com)
[![Stripe](https://img.shields.io/badge/Payments-Stripe-635bff?style=for-the-badge&logo=stripe)](https://stripe.com)

---

## 🗺️ Table of Contents

- [Overview](#overview)
- [Live Workflow](#live-workflow)
- [Core Features](#core-features)
- [Tech Stack](#tech-stack)
- [AI & Prompt Engineering](#ai--prompt-engineering)
- [Business Intelligence](#business-intelligence)
- [Data Architecture](#data-architecture)
- [Skills Demonstrated](#skills-demonstrated)

---

## 🌟 Overview

An intelligent, full-stack SaaS web application that automates the creation of professional business cards from certification and credential URLs.

&nbsp;

Paste up to **8 credential links** → two AI agents analyze, design, and export a **UPS print-ready PDF** with vibrant QR-coded business cards in under a minute.

&nbsp;

> Built for professionals who want to physically showcase digital certifications, credentials, and achievements — beautifully.

---

## 🔄 Live Workflow

╔══════════════╗ ╔══════════════╗ ╔══════════════╗ ╔══════════════╗ ║ 1. 📥 INPUT ║ ──▶ ║ 2. 🧠 ANALYZE║ ──▶ ║ 3. 🎨 DESIGN ║ ──▶ ║ 4. 📄 EXPORT ║ ║ ║ ║ ║ ║ ║ ║ ║ ║ Paste URLs ║ ║ AI extracts ║ ║ AI generates ║ ║ PDF download ║ ║ or .docx ║ ║ titles & ║ ║ cards with ║ ║ UPS-ready ║ ║ upload ║ ║ metadata ║ ║ gradients ║ ║ 3.5" x 2" ║ ╚══════════════╝ ╚══════════════╝ ╚══════════════╝ ╚══════════════╝


---

## 🚀 Core Features

### 📥 Input Layer

&nbsp;

- **URL Batch Processing** — Paste up to 8 credential URLs (one per line) for simultaneous processing

&nbsp;

- **DOCX Upload Support** — Upload `.docx` files; the system auto-extracts all embedded hyperlinks

&nbsp;

- **Smart URL Resolution** — Follows redirects and resolves canonical URLs automatically

&nbsp;

- **Batch ID System** — Every session is tagged with a unique batch ID for history tracking

---

### 🧠 AI Analysis Layer

&nbsp;

- **Real-Time Chat Interface** — Conversational AI chat for URL analysis with live status updates

&nbsp;

- **Program Title Extraction** — LLM identifies certification/program names from any URL format

&nbsp;

- **Status Polling** — Live progress indicators (pending → analyzing → completed → error)

&nbsp;

- **Fast Mode** — One-click batch processing for all URLs simultaneously

---

### 🎨 Design & Customization Layer

&nbsp;

- **5 Design Templates** — `Modern` · `Professional` · `Creative` · `Minimal` · `Bold`

&nbsp;

- **AI-Generated Gradients** — Vibrant 2–3 color gradient combinations unique to each card

&nbsp;

- **Custom Color Palettes** — Override AI colors with brand-specific hex values (primary, secondary, accent)

&nbsp;

- **Editable Card Fields:**

  &nbsp;

  - 🏷️ Card Title — Program or credential name

  - 📝 Card Description — Short description (max ~10 words) of the application/credential

  - 💬 Custom Message — Personalized tagline or note

  - 🔗 QR Data URL — The URL encoded into the QR code

&nbsp;

- **Drag-and-Drop QR Codes** — Reposition and resize QR codes directly on the card canvas

&nbsp;

- **Live Preview** — Real-time rendering of every change before export

&nbsp;

- **Approval Workflow** — Cards cycle through `draft` → `approved` → `exported` states

---

### 📄 Export Layer

&nbsp;

- **UPS-Ready PDF** — Standard 3.5" × 2" business card dimensions, 8 per page

&nbsp;

- **Cutting Guides** — Printer-friendly crop marks on the PDF

&nbsp;

- **Approved Cards Only** — Only cards marked `approved` are included in the export

&nbsp;

- **Batch History** — Full archive of every processed batch with re-downloadable PDFs

---

## 🛠️ Tech Stack

### 🖥️ Frontend

&nbsp;

| Technology | Purpose |
|---|---|
| **React 18.2** | Component-based UI architecture |
| **TailwindCSS** | Utility-first responsive styling |
| **Framer Motion** | Smooth card animations and transitions |
| **TanStack React Query** | Server state, caching & real-time polling |
| **React Router v6** | Client-side routing and navigation |
| **QRCode.js** | Canvas-based QR code generation |
| **jsPDF** | Client-side PDF generation |
| **Lucide React** | Icon system |
| **Sonner** | Toast notifications |

&nbsp;

### ⚙️ Backend

&nbsp;

| Technology | Purpose |
|---|---|
| **Deno Runtime** | Serverless backend function execution |
| **Base44 SDK** | Entity CRUD, auth, and integrations |
| **Base44 Agents** | Multi-agent AI orchestration layer |
| **LLM Integration** | GPT-powered analysis and design generation |
| **Web Search Context** | Internet-augmented LLM for URL metadata |

&nbsp;

### 💳 Payments (In Progress)

&nbsp;

| Technology | Purpose |
|---|---|
| **Stripe** | Monthly subscriptions + one-time payments |
| **Stripe Webhooks** | Real-time payment event handling |
| **Stripe Customer Portal** | Self-serve subscription management |

---

## 🧠 AI & Prompt Engineering

### 🔍 Agent 1: `url_analyzer`

&nbsp;

**Role:** Analyzes credential URLs and extracts structured program information

&nbsp;

**Prompt Engineering Techniques Used:**

&nbsp;

- 🔗 **Context Injection** — Web search results are injected into the prompt to give the LLM real page content

&nbsp;

- 📐 **Structured Output Enforcement** — JSON schema is mandated in the response for consistent entity creation

&nbsp;

- 🧩 **Chain-of-Thought Reasoning** — Step-by-step URL breakdown guided by system instructions

&nbsp;

- 🎯 **Task Decomposition** — Splits multi-URL batches into individual analysis tasks

&nbsp;

**Entity Operations Permitted:**

- `URLRecord` → read, update
- `BusinessCard` → create, read

---

### 🎨 Agent 2: `card_designer`

&nbsp;

**Role:** Generates vibrant, visually unique business cards from analyzed URL data

&nbsp;

**Prompt Engineering Techniques Used:**

&nbsp;

- 🎭 **Role-Based Prompting** — Agent is instructed to act as a professional card designer

&nbsp;

- 🚦 **Hard Constraints** — Mandatory use of `creative` template + vibrant multi-color gradients enforced in system prompt

&nbsp;

- 📏 **Length Control** — Card description capped at 10 words via explicit instruction

&nbsp;

- 🌈 **Palette Diversity Rules** — Agent is instructed to avoid repeating gradient combinations across pairs

&nbsp;

- 🔁 **Iterative Refinement Loop** — Conversational chat interface allows users to request redesigns mid-session

&nbsp;

**Entity Operations Permitted:**

- `URLRecord` → read
- `BusinessCard` → create, read, update, delete

---

## 📊 Business Intelligence

### 📈 Trackable Metrics

&nbsp;

- **Batch Volume** — Number of batches processed per user session

&nbsp;

- **URL Resolution Rate** — % of URLs successfully resolved to canonical form

&nbsp;

- **Analysis Success Rate** — % of URLs where AI successfully extracts program title

&nbsp;

- **Card Approval Rate** — % of AI-generated cards approved without editing

&nbsp;

- **Customization Depth** — How often users edit titles, descriptions, messages, or QR position

&nbsp;

- **Export Completion Rate** — % of sessions that reach PDF download

&nbsp;

- **Template Distribution** — Which design templates are most selected

&nbsp;

- **Time-to-Export** — Average time from URL input to PDF download

---

### 💡 Intelligence Design Decisions

&nbsp;

- **Pair-Based Card Organization** — Cards are organized in pairs (1–4) mirroring standard print sheet layouts, reducing cognitive load

&nbsp;

- **Polling Architecture** — 5-second refetch interval gives real-time feel without WebSocket complexity

&nbsp;

- **Batch History** — Enables longitudinal tracking of user card creation behavior

&nbsp;

- **Approval Workflow** — Creates a natural quality gate before export, improving print output quality

---

## 🗄️ Data Architecture

┌─────────────────────────────────────────────────────┐ │ URLRecord │ ├─────────────────────────────────────────────────────┤ │ display_url → Original pasted URL │ │ canonical_url → Resolved final URL │ │ program_title → AI-extracted credential name │ │ batch_id → Groups URLs by session │ │ position → Order in batch (1–9) │ │ analysis_status → pending/analyzing/completed │ └─────────────────────────────────────────────────────┘ │ 1:1 ▼ ┌─────────────────────────────────────────────────────┐ │ BusinessCard │ ├─────────────────────────────────────────────────────┤ │ card_title → Display name on card │ │ card_description → Short app/credential summary │ │ custom_message → Personalized note │ │ qr_data → URL encoded in QR code │ │ design_template → modern/creative/bold/... │ │ color_palette → { primary, secondary, accent } │ │ custom_elements → { qr_size, qr_position } │ │ pair_number → Pair grouping (1–4) │ │ position_in_pair → Slot within pair (1 or 2) │ │ export_status → draft / approved / exported │ └─────────────────────────────────────────────────────┘


---

## 🏆 Skills Demonstrated

### 🤖 AI Engineering

&nbsp;

- Multi-agent orchestration with role isolation and permission scoping

&nbsp;

- Prompt engineering: constraint enforcement, structured outputs, iterative refinement

&nbsp;

- LLM + web search augmentation for real-world URL data extraction

&nbsp;

- Conversational agent UX design with real-time streaming responses

---

### 🧱 Full-Stack Development

&nbsp;

- Serverless backend function design (Deno + Base44)

&nbsp;

- React component architecture with clean separation of concerns

&nbsp;

- Real-time UI with polling, optimistic updates, and state management

&nbsp;

- PDF generation with precise print-layout engineering (jsPDF)

---

### 🎨 UI/UX Design

&nbsp;

- Drag-and-drop canvas interactions for QR code placement

&nbsp;

- Gradient generation system with diversity enforcement

&nbsp;

- Step-by-step wizard UX with persistent state across workflow stages

&nbsp;

- Fully responsive — optimized for mobile and desktop

---

### 💼 Business & Product Thinking

&nbsp;

- End-to-end workflow designed for a real printing use case (UPS stores)

&nbsp;

- Batch history enables returning users and repeat business

&nbsp;

- Approval workflow mirrors real production quality assurance processes

&nbsp;

- Monetization architecture with Stripe (subscriptions + one-time fees)

---

## 👤 Author

**Roy Belovoskey**

&nbsp;

> *Built with ❤️ on the Base44 AI Platform*
