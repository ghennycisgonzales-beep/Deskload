# Deskload — Student Task Tracker & Weekly Workload Planner

A web-based student task manager that helps students organize their academic workload: tasks, deadlines, subjects, and priorities in one dashboard.

**Live demo:** https://YOUR-USERNAME.github.io/deskload/
**Members:** [names] | **Course:** [course code] | **Instructor:** [name] | BSIT, 2026

---

## Purpose
Students often juggle many assignments, projects, and readings at once. Deskload gives them a centralized dashboard to organize tasks, monitor deadlines, and manage their weekly workload.

## Features
- Add tasks with title, due date, subject, and priority
- Mark tasks as completed / delete tasks
- Overdue and due-today detection
- Dashboard statistics (Open, Due Today, Overdue, Completed)
- Workload-by-subject bar chart
- Data persists in the browser (LocalStorage)
- Responsive layout and automatic dark mode

## How to run
**Option 1 (online):** open the live demo link above.
**Option 2 (local):**
```bash
git clone https://github.com/YOUR-USERNAME/deskload.git
cd deskload
# open index.html in your browser (double-click it)
```
No server, build step, or installation needed.

## Technologies used
| Technology | Used for |
|---|---|
| HTML5 | Page structure, forms, task table |
| CSS3 (Custom Properties, Flexbox, Grid, media queries, `prefers-color-scheme`) | Styling, theming, responsive layout, dark mode |
| JavaScript (ES6+) | App logic, task CRUD, rendering |
| LocalStorage (Web Storage API) + `JSON.stringify/parse` | Saving tasks in the browser |
| Google Fonts (Source Serif 4, IBM Plex Sans) | Typography |

## How the system works
1. **Initialization:** `loadTasks()` checks LocalStorage; if empty, `seedTasks()` creates sample tasks.
2. **Adding a task:** user fills the form, `addTask()` runs.
3. **Saving:** a task object (id, title, subject, due, priority, done) is created, and `saveTasks()` stores it as JSON.
4. **Updating the dashboard:** `render()` refreshes the task list, statistics, and workload bars.
5. **Complete / delete:** `toggleDone(id)` and `deleteTask(id)` update the data, save, then re-render.
6. **Deadline monitoring:** each due date is compared with today's date (JS `Date`) to mark Overdue / Due Today.
7. **Workload by subject:** open tasks are grouped by subject using array methods (`.map()`, `.filter()`, `.sort()`).

`try...catch` wraps all LocalStorage access so the app does not crash if storage is unavailable (e.g. private browsing).

## Current vs. future system
- **Current:** front-end prototype (HTML + CSS + JavaScript + LocalStorage).
- **Planned:** connect to a REST API (TaskService), a backend server, and a database for accounts, online storage, sync, and multi-device access.

## References (MDN Web Docs)
- HTML: https://developer.mozilla.org/en-US/docs/Web/HTML
- CSS: https://developer.mozilla.org/en-US/docs/Web/CSS
- JavaScript: https://developer.mozilla.org/en-US/docs/Web/JavaScript
- CSS custom properties: https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties
- prefers-color-scheme: https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme
- Flexbox: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexbox
- CSS Grid: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout
- Media queries: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries
- Web Storage API: https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API
- JSON: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON
- Array methods: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array
- Template literals: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals
- Date: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date
- DOM: https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model
- try...catch: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch
- Google Fonts: https://fonts.google.com/
