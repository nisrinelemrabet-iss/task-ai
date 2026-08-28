# TaskAI — AI-Powered Task Manager

> A vanilla HTML/CSS/JS task manager with real AI features powered by the Anthropic Claude API — usable for free in Demo Mode, or unlocked fully with your own API key.

![HTML](https://img.shields.io/badge/HTML-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Anthropic](https://img.shields.io/badge/Anthropic%20API-Claude-black?style=flat)

---

## What it does

TaskAI is a fully client-side task manager that integrates with the **Anthropic Claude API** to bring AI-assisted planning into a single, clean interface — no framework, no build step, no backend.

It works in two tiers, so anyone can try it without needing to pay for anything:

| | **Free (Demo Mode)** | **Premium (your API key)** |
|---|---|---|
| Cost | $0, no account needed | Pay-as-you-go via your Anthropic account |
| Setup | Toggle one checkbox | Paste your own API key |
| Natural language task parsing | ✅ Simulated (keyword-based) | ✅ Real Claude parsing |
| AI field fill (title → description/priority/tags) | ✅ Simulated | ✅ Real Claude generation |
| AI Smart Assist (next-step tips) | ✅ Canned tip library | ✅ Tailored to your exact task |
| Task decomposition into subtasks | ✅ Generic subtask template | ✅ Task-specific breakdown |
| AI Daily Planner | ✅ Simulated schedule | ✅ Real prioritized, context-aware plan |
| Web search enrichment | ⚠️ Placeholder message | ✅ Live web search via Claude's search tool |
| Productivity dashboard | ✅ Full access | ✅ Full access |
| Due dates & subtask tracking | ✅ Full access | ✅ Full access |

Demo Mode exists so you can explore the whole UI and workflow — grading, demoing, or just poking around — without creating an account or spending anything. The **quality and accuracy** of the AI responses is the main thing that's limited; the interface and core task-management features are the same either way.

---

## Free vs Premium — how it works

- Check the **"Demo mode (no key needed)"** box in the top banner.
- All AI buttons (✦ AI Parse, ✦ AI fill fields, ✦ assist, ⌕ web search, ⊞ decompose, 📅 Plan my day) still work — they return realistic simulated results instantly instead of calling the real API.
- No account, no key, no cost.
- Great for testing, demos, or grading.

- Get your own key from the [Anthropic Console](https://console.anthropic.com/) (new accounts get a small one-time trial credit — see [Getting an API key](#getting-an-api-key) below).
- Paste it into the "Anthropic API Key" field and click Save. It's stored only in your browser's `localStorage` and sent directly to `api.anthropic.com` — never anywhere else.
- Every AI feature now uses real Claude responses: accurate parsing of your specific wording, task-aware subtasks, a planner that reasons over your actual workload, and live web search results.

---

## AI Features

### 1. Natural Language Task Parsing
Type a task the way you'd say it out loud:
> *"Finish the homepage redesign by Friday — it's urgent"*

Extracts **title**, **priority**, **tags**, **due date**, and an **estimated duration**.

### 2. AI Field Generation
Open the task modal, type a title, click **✦ AI fill fields** — generates a description, priority, and tags.

### 3. Smart AI Assist
Click **✦** on any task card for one specific, actionable next step or tip.

### 4. Web Search Enrichment
Click **⌕** to pull a live, relevant resource for that task from the web (Premium only — Demo Mode shows a placeholder explaining what this would do).

### 5. AI Task Decomposition
Click **⊞** to break a task into 3–5 checkable subtasks, with progress tracking.

### 6. AI Daily Planner
Click **📅 Plan my day** to get a realistic time-blocked schedule built from your open tasks, respecting priority and due dates.

### 7. Productivity Dashboard
Switch to the **Dashboard** tab for a completion-rate ring, priority breakdown, a 7-day activity chart, and quick stats — works identically in both tiers since it's calculated from your local task data, not the AI.

---

## Tech Stack

| Layer      | Technology                                        |
| ---------- | -------------------------------------------------- |
| Frontend   | HTML5, CSS3, Vanilla JavaScript (ES6+)             |
| AI         | Anthropic Claude API (`claude-sonnet-4`)           |
| Web Search | Anthropic Web Search Tool (`web_search_20250305`)  |
| Storage    | `localStorage` (no backend needed)                 |
| Fonts      | Google Fonts — DM Serif Display + DM Sans          |

---

## Getting Started

### 1. Clone the repo
```
git clone https://github.com/nisrinelemrabet-iss/task-ai.git
cd task-ai
```

### 2. Open in browser
```
open index.html
# or just double-click the file — no server needed
```

### 3. Choose your tier
- **Free:** check "Demo mode" and start using it immediately.
- **Premium:** follow the steps below to get and add your own key.

---

## Getting an API key

1. Go to [console.anthropic.com](https://console.anthropic.com/) and create an account.
2. New accounts typically receive a small one-time trial credit (no permanent free tier — after that it's pay-as-you-go).
3. Go to **API Keys** → **Create Key**, copy it (starts with `sk-ant-`).
4. Paste it into TaskAI's API key field and click Save.

Your key is only ever stored in your own browser and sent directly to Anthropic — it is never written into this repository or shared with anyone. Don't share your key with others or paste it anywhere public.

---

## Project Structure

```
task-ai/
├── index.html      # Everything — markup, styles, and logic in one file
└── README.md
```

The entire project is intentionally a **single file** — a deliberate choice to demonstrate clean, well-organized vanilla JS without any build tooling or dependencies.

---

## Key Concepts Demonstrated

- **Prompt engineering** — structured JSON extraction from natural language
- **Tool use / function calling** — web search integration via Anthropic's tool API
- **Async JS** — non-blocking API calls with loading states and centralized error handling
- **Graceful degradation** — a fully functional free tier (Demo Mode) alongside a premium API-backed tier
- **localStorage** — client-side persistence without a database
- **Component-based thinking** — modular render/state pattern without a framework

---

## Future Improvements

- [ ] Split into `index.html`, `style.css`, `app.js`
- [ ] Drag-and-drop task reordering
- [ ] Export tasks as PDF or CSV
- [ ] Dark / light theme toggle

---

## License

MIT — feel free to use, fork, and build on this.
