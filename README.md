# TaskAI — AI-Powered Task Manager

> A vanilla HTML/CSS/JS task manager with real AI features powered by the Anthropic Claude API.

![HTML](https://img.shields.io/badge/HTML-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Anthropic](https://img.shields.io/badge/Anthropic%20API-Claude-black?style=flat)

---

## What it does

TaskAI is a fully client-side task manager that integrates with the **Anthropic Claude API** to bring four distinct AI capabilities into a single, clean interface — no framework, no build step, no backend.

---

## AI Features

### 1. Natural Language Task Parsing
Type a task the way you'd say it out loud:

> *"Finish the homepage redesign by Friday — it's urgent"*

Claude parses your input and automatically extracts the **title**, **priority level**, and **tags**. No forms, no dropdowns — just plain English.

### 2. AI Field Generation
Open the task modal, type a title, and click **✦ AI fill fields**. Claude generates:
- A concise task description
- A suggested priority (high / medium / low)
- Relevant tags

### 3. Smart AI Assist
Click the **✦** button on any task card to get a specific, actionable next step or productivity tip tailored to that task.

### 4. Web Search Enrichment
Click the **⌕** button to trigger a live web search. Claude fetches real-time, relevant information or useful resources directly related to your task — powered by Anthropic's web search tool.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, Vanilla JavaScript (ES6+) |
| AI | Anthropic Claude API (`claude-sonnet-4`) |
| Web Search | Anthropic Web Search Tool (`web_search_20250305`) |
| Storage | `localStorage` (no backend needed) |
| Fonts | Google Fonts — DM Serif Display + DM Sans |

---

## Getting Started

### 1. Clone the repo
```bash
git clone https://github.com/your-username/task-ai.git
cd task-ai
```

### 2. Open in browser
```bash
open index.html
# or just double-click the file — no server needed
```

### 3. Add your API key
Enter your [Anthropic API key](https://console.anthropic.com/) in the top bar and click **Save**. It's stored locally in your browser and never sent anywhere except the Anthropic API.

---

## Project Structure

```
task-ai/
├── index.html      # Everything — markup, styles, and logic in one file
└── README.md
```

The entire project is intentionally a **single file**. This was a deliberate choice to demonstrate clean, well-organized vanilla JS without any build tooling or dependencies.

---

## How the API is used

All AI calls go through `https://api.anthropic.com/v1/messages` directly from the browser.

```js
// Standard AI call
const response = await fetch('https://api.anthropic.com/v1/messages', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'x-api-key': API_KEY,
    'anthropic-version': '2023-06-01'
  },
  body: JSON.stringify({
    model: 'claude-sonnet-4-20250514',
    max_tokens: 400,
    messages: [{ role: 'user', content: prompt }]
  })
});

// Web search call (adds beta header + search tool)
headers['anthropic-beta'] = 'web-search-2025-03-05';
body.tools = [{ type: 'web_search_20250305', name: 'web_search' }];
```

Responses are parsed from `data.content` — a mixed array of `text` and `tool_use` blocks depending on the feature.

---

## Key Concepts Demonstrated

- **Prompt engineering** — structured JSON extraction from natural language
- **Tool use / function calling** — web search integration via Anthropic's tool API
- **Async JS** — non-blocking API calls with loading states and error handling
- **localStorage** — client-side persistence without a database
- **Component-based thinking** — modular render/state pattern without a framework

---

## Screenshots

> *(Add screenshots here once deployed)*

---

## Future Improvements

- [ ] Split into `index.html`, `style.css`, `app.js` for cleaner repo structure
- [ ] Due dates with overdue highlighting
- [ ] Drag-and-drop task reordering
- [ ] Export tasks as PDF or CSV
- [ ] Dark / light theme toggle
- [ ] Deploy to GitHub Pages

---

## License

MIT — feel free to use, fork, and build on this.


