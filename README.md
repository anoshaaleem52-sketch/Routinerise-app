# RoutineRise 🚀

> **Dynamic, Client-Side Daily Planner**  
> *Engineered to handle real-world schedule volatility through zero-latency automatic day rebuilds, natural language task parsing, and forgiving streak tracking.*

---

## 📌 Executive Summary
Standard productivity tools rely on deterministic, static scheduling—assuming non-disrupted execution. When tasks inevitably slip, rigid systems create scheduling debt and user friction. **RoutineRise** addresses schedule deviation as expected operational variance. Built with a local-first architecture, it dynamically recalculates task queues, redistributes remaining time blocks, and preserves behavioral momentum using a custom recovery-state habit engine.

---

## ⚙️ Key Technical Architecture & Features

### 🔄 Dynamic Schedule Rebuilding Engine
* **Algorithmic Time Realignment:** Uses native Date object arithmetic to continuously project task completion paths based on real-time execution pace.
* **Temporal Edge-Case Handling:** Computes accurate schedules across midnight transitions ($00:00$ UTC offset boundaries) without relying on external time libraries.

### 🧠 Lightweight Natural Language Parser (NLP)
* **Regex-Based String Interpretation:** Built-in pattern-matching engine that evaluates raw user input into structured JSON task schemas.
* **Automated Extraction:** Instantaneously identifies date anchors, duration values (e.g., `90m`, `1.5h`), and execution priority flags without API call latency.

### 🛡️ Privacy-First & Local-Storage Data Model
* **Client-Side Data Persistence:** Direct state synchronization via the browser's native `localStorage` API.
* **Zero Cloud Overhead:** Complete system functionality without external database infrastructure or data tracking.
* **Data Portability:** Native JSON serialization engine supporting dynamic import, export, and complete user state resets.

### 📈 Resilience-Focused Habit Metrics
* **Non-Binary Streak Logic:** Replaces failure-heavy binary resets with partial-credit recovery curves to maximize long-term behavioral consistency.
* **Progressive Analytics Rollups:** Calculates daily velocity metrics and category completion distributions client-side.

---

## 🛠️ Tech Stack & Systems

| Layer | Technology | Engineering Design Rationale |
| :--- | :--- | :--- |
| **Frontend Core** | **Vanilla HTML5 & ES6+ JavaScript** | Zero external dependencies; optimized DOM manipulation without Virtual DOM overhead. |
| **Styling & UI** | **CSS3 Custom Properties (Variables)** | Dynamic CSS variable token replacement for instant light/dark theme switching and zero-layout-shift UI states. |
| **State Management** | **Native Window Event Pipeline** | Pub/Sub state system managing modal instances, task execution timers, and active views. |
| **Deployment** | **GitHub Pages Edge Engine** | Static edge delivery with native asset optimization and zero build step dependencies. |

---

## 📊 System Architecture & Task Lifecycle

```text
[ Raw User Input ] 
       │
       ▼
[ Regex NLP Engine ] ──► (Parses Title, Duration, Priority)
       │
       ▼
[ Task Queue State ] ──► (Performs Free/Busy Time-Slot Analysis)
       │
       ▼
[ Schedule Rebuilder ] ──► (Recalculates Offsets & Midnight Boundaries)
       │
       ▼
[ LocalStorage API ] ──► (Persists State & Renders Dynamic UI)
