Here you go, Varsha — the *clean GitHub-ready README.md* with perfect Markdown formatting, headings, spacing, emojis, and code blocks.
Just copy–paste this directly into your GitHub repo. 👇

---

# 🎨 Collaborative Real-Time Drawing Canvas

A multi-user drawing application built with *HTML5 Canvas, **Vanilla JavaScript/TypeScript, and **Node.js WebSockets, allowing multiple users to draw together with **live real-time synchronization*.

---
## 🔗 Important Links

Hosted App: https://bright-sorbet-bf5470.netlify.app/

GitHub Repository:https://github.com/Paddu2003/Flam-Assignemnt


## 🚀 Features

### 🎨 Drawing Tools

* Freehand brush
* Eraser
* Color picker
* Adjustable stroke width

### 🔄 Real-Time Collaboration

* Multiple users draw at the same time
* Live stroke streaming (event-based)
* Other users’ cursor indicators
* Smooth drawing with path optimization

### 👥 User Management

* Online user list
* User-specific assigned colors
* Presence updates on join/leave

### 🧠 Advanced Logic

* Global undo/redo (across all users)
* Conflict resolution for overlapping strokes
* Centralized stroke history stored on server
* Canvas state reconstruction when a new user joins

---

## 🏗 Project Structure


collaborative-canvas/
├── client/
│   ├── index.html
│   ├── style.css
│   ├── canvas.js / canvas.ts
│   ├── websocket.js / websocket.ts
│   └── main.js / main.ts
├── server/
│   ├── server.js / server.ts
│   ├── rooms.js / rooms.ts
│   └── drawing-state.js / drawing-state.ts
├── package.json
├── README.md
└── ARCHITECTURE.md


---

## ⚙ Setup Instructions

### *1. Install Dependencies*

bash
npm install


### *2. Start the Server*

bash
npm start


### *3. Open the Client*

Open client/index.html using:

* VS Code Live Server
  *or*
* Navigate to:


http://localhost:3000


### *4. Test With Multiple Users*

Open the same URL in:

* 2–3 browser tabs
* Multiple devices

Draw in one window → It appears instantly in all others.

---

## 🔌 How Real-Time Sync Works

### *Stroke Event Example*

json
{
  "type": "stroke",
  "userId": "user-abc123",
  "canvasId": "default",
  "payload": {
    "x": 120,
    "y": 340,
    "color": "#ff0000",
    "width": 4,
    "pressure": 0.8,
    "isDrawing": true
  }
}


The server receives this event and broadcasts it to all other connected users.

### *Undo/Redo Events*

json
{ "type": "undo", "userId": "user-abc123" }
{ "type": "redo", "userId": "user-abc123" }


The server updates *global stroke history* and synchronizes the updated canvas state to everyone.

---

## 🧪 Testing Scenarios

* Two users drawing at the same time
* Undo/redo triggered by one user updates all canvases
* High-frequency mouse movement (stress test)
* Network throttling to check latency handling
* New user joins → full canvas reconstructs automatically

---

## 🪲 Known Limitations / Bugs

* Undo/redo may lag slightly with extremely large stroke histories
* Cursor indicators can flicker on slow connections
* No canvas export feature yet
* No persistent storage (server restart clears drawings)

---

## ⏱ Time Spent on Project

| Task                  | Time        |
| --------------------- | ----------- |
| Canvas drawing logic  | 4 hrs       |
| WebSocket integration | 3 hrs       |
| Global undo/redo      | 2 hrs       |
| UI & tools            | 1.5 hrs     |
| Testing & debugging   | 1 hr        |
| Documentation         | 0.5 hr      |
| *Total*             | *~12 hrs* |

---
